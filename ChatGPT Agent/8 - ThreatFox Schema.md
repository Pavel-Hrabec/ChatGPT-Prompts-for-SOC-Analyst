openapi: 3.1.0
info:
  title: ThreatFox IP Checker
  description: Check if an IP address appears in the Abuse.ch ThreatFox threat intelligence database. Requires an API key in the Auth-Key header.
  version: 1.1.3
servers:
  - url: https://threatfox-api.abuse.ch
    description: ThreatFox API v1
paths:
  /api/v1/:
    post:
      operationId: checkIpAddress
      summary: Check an IP address against ThreatFox
      description: Queries ThreatFox to check if a given IP address is listed as an IOC. Requires an API key in the Auth-Key header.
      security:
        - ThreatFoxAuth: []
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                query:
                  type: string
                  enum: [search_ioc]
                  example: search_ioc
                search_term:
                  type: string
                  format: ipv4
                  example: 157.20.182.60
                exact_match:
                  type: boolean
                  example: false
              required:
                - query
                - search_term
      responses:
        '200':
          description: IOC results for the IP address
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ThreatFoxResponse'
        '401':
          description: Unauthorized - Missing or invalid API key
components:
  securitySchemes:
    ThreatFoxAuth:
      type: apiKey
      in: header
      name: Auth-Key
  schemas:
    ThreatFoxResponse:
      type: object
      properties:
        query_status:
          type: string
          description: Status of the query (e.g., "ok", "error")
        data:
          type: array
          items:
            type: object
            properties:
              id:
                type: string
              ioc:
                type: string
              ioc_type:
                type: string
              threat_type:
                type: string
              threat_type_desc:
                type: string
              malware:
                type: string
              confidence_level:
                type: integer
              reporter:
                type: string
              first_seen:
                type: string
                format: date-time
              last_seen:
                type: string
                format: date-time
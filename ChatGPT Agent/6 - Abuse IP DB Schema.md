openapi: 3.1.0
info:
  title: AbuseIPDB IP Lookup API
  description: Query abuse reports for an IP address using the AbuseIPDB API.
  version: 1.0.3
servers:
  - url: https://api.abuseipdb.com/api/v2
    description: AbuseIPDB API server
paths:
  /check:
    get:
      operationId: checkIpAddress
      summary: Check an IP address for abuse reports
      description: Returns abuse report data for a given IP address from AbuseIPDB.
      parameters:
        - name: ipAddress
          in: query
          required: true
          schema:
            type: string
          description: The IP address to check
        - name: maxAgeInDays
          in: query
          required: false
          schema:
            type: integer
          description: Only consider reports within the last X days (max 365)
        - name: verbose
          in: query
          required: false
          schema:
            type: boolean
          description: Whether to include full report details
      responses:
        '200':
          description: Abuse report found for the IP address
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/IpAbuseCheckResponse'
        '401':
          description: Unauthorized – API key is missing or invalid
        '429':
          description: Rate limit exceeded
      security:
        - ApiKeyAuth: []
components:
  securitySchemes:
    ApiKeyAuth:
      type: apiKey
      in: header
      name: Key
  schemas:
    IpAbuseCheckResponse:
      type: object
      properties:
        data:
          type: object
          properties:
            ipAddress:
              type: string
            isPublic:
              type: boolean
            abuseConfidenceScore:
              type: integer
              description: Score from 0 to 100 indicating likelihood of abuse
            countryCode:
              type: string
            domain:
              type: string
            totalReports:
              type: integer
            lastReportedAt:
              type: string
              format: date-time

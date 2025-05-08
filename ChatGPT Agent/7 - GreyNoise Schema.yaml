openapi: 3.1.0
info:
  title: GreyNoise Community API
  description: Access GreyNoise data to determine if an IP address is noisy or benign using the free community API.
  version: 1.0.0
servers:
  - url: https://api.greynoise.io
    description: GreyNoise Community API server
paths:
  /v3/community/{ip}:
    get:
      operationId: getIpInfo
      summary: Get community noise information for a given IP address.
      parameters:
        - name: ip
          in: path
          required: true
          description: The IP address to query.
          schema:
            type: string
      responses:
        '200':
          description: IP information from the community API
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/CommunityIpResponse'
        '404':
          description: IP not found
        '429':
          description: Rate limit exceeded
        '500':
          description: Internal server error
      security:
        - apiKeyAuth: []
components:
  securitySchemes:
    apiKeyAuth:
      type: apiKey
      in: header
      name: key
  schemas:
    CommunityIpResponse:
      type: object
      properties:
        ip:
          type: string
        noise:
          type: boolean
        riot:
          type: boolean
        classification:
          type: string
          description: Classification of the IP (e.g., benign, malicious, unknown)
        name:
          type: string
          description: Name or label associated with the IP
        link:
          type: string
          format: uri
          description: URL to view more information about the IP
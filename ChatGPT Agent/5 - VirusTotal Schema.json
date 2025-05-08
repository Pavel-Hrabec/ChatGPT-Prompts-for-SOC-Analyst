{
  "openapi": "3.1.0",
  "info": {
    "title": "VirusTotal API",
    "version": "1.0.0",
    "description": "Check file hash and IP address reputation using VirusTotal."
  },
  "servers": [
    {
      "url": "https://www.virustotal.com/api/v3"
    }
  ],
  "paths": {
    "/ip_addresses/{ip}": {
      "get": {
        "operationId": "getIpReport",
        "summary": "Get IP address report",
        "parameters": [
          {
            "name": "ip",
            "in": "path",
            "required": true,
            "description": "The IP address to query",
            "schema": {
              "type": "string",
              "format": "ipv4"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "Successful IP address report response",
            "content": {
              "application/json": {
                "schema": {}
              }
            }
          }
        },
        "security": [
          {
            "ApiKeyAuth": []
          }
        ]
      }
    }
  },
  "components": {
    "securitySchemes": {
      "ApiKeyAuth": {
        "type": "apiKey",
        "in": "header",
        "name": "Key"
      }
    },
    "schemas": {}
  }
}

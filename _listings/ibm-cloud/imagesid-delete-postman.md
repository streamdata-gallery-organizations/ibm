{
  "info": {
    "name": "IBM Containers Remove a Docker image.",
    "_postman_id": "6c5f8039-eb11-4e97-8da6-414f7f95041e",
    "description": "Remove a Docker image from the private Bluemix registry that is identified by the image ID (corresponding IBM Containers command: `cf ic rmi <image>`).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Images",
      "item": [
        {
          "id": "d4813bfd-20ce-4f4b-bff8-850d1bdc04df",
          "name": "this-endpoint-returns-a-list-of-all-available-docker-images-in-a-private-bluemix-registry-correspond",
          "request": {
            "url": "http://containers-api.ng.bluemix.net/v3/images/json",
            "method": "GET",
            "header": [
              {
                "key": "X-Auth-Project-Id",
                "value": "{}",
                "description": "The unique ID of your organization space where you want to create or work with your containers",
                "disabled": false
              },
              {
                "key": "X-Auth-Token",
                "value": "{}",
                "description": "The Bluemix JSON web token that you receive when logging into Bluemix",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "This endpoint returns a list of all available Docker images in a private Bluemix registry (corresponding IBM Containers command: `cf ic images`."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "386fc479-7dad-4c85-98a8-ab60216a612e"
            }
          ]
        },
        {
          "id": "2942d10b-b6ec-4b51-af69-4bb7814d7fbf",
          "name": "remove-a-docker-image-from-the-private-bluemix-registry-that-is-identified-by-the-image-id-correspon",
          "request": {
            "url": {
              "protocol": "http",
              "host": "containers-api.ng.bluemix.net",
              "path": [
                "v3",
                "images/:id"
              ],
              "variable": [
                {
                  "id": "id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "DELETE",
            "header": [
              {
                "key": "X-Auth-Project-Id",
                "value": "{}",
                "description": "The unique ID of your organization space where you want to create or work with your containers",
                "disabled": false
              },
              {
                "key": "X-Auth-Token",
                "value": "{}",
                "description": "The Bluemix JSON web token that you receive when logging into Bluemix",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Remove a Docker image from the private Bluemix registry that is identified by the image ID (corresponding IBM Containers command: `cf ic rmi <image>`)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "76341178-4390-41e2-b38a-7f10968e6e71"
            }
          ]
        }
      ]
    }
  ]
}
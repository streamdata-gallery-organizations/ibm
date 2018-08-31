{
  "info": {
    "name": "IBM Containers Inspect a Docker image in private Bluemix registry",
    "_postman_id": "48dd7cf9-fbf1-4354-9d9d-688aed073465",
    "description": "This endpoint returns detailed information about a Docker image that is stored in the private Bluemix registry of an organization (corresponding IBM Containers command: `cf ic inspect <image_name_or_id>`).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Images",
      "item": [
        {
          "id": "0074e08d-cb85-459b-b5aa-3d74f705ee9f",
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
              "id": "3121770f-d833-4cc6-bcb0-ac3d0ce12f12"
            }
          ]
        },
        {
          "id": "65c8f403-5f71-4f1a-95ac-a799a2fa27a3",
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
              "id": "44c5b488-7751-41fe-bc5f-8971587c4a7d"
            }
          ]
        },
        {
          "id": "9f9b7518-e95f-4a99-8977-170aae9f8ad4",
          "name": "this-endpoint-returns-detailed-information-about-a-docker-image-that-is-stored-in-the-private-bluemi",
          "request": {
            "url": {
              "protocol": "http",
              "host": "containers-api.ng.bluemix.net",
              "path": [
                "v3",
                "images/:name_or_id/json"
              ],
              "variable": [
                {
                  "id": "name_or_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
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
            "description": "This endpoint returns detailed information about a Docker image that is stored in the private Bluemix registry of an organization (corresponding IBM Containers command: `cf ic inspect <image_name_or_id>`)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3a2d927d-b6b4-43f8-9d9f-7c2de111aaf2"
            }
          ]
        }
      ]
    }
  ]
}
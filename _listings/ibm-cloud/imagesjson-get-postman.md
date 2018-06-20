{
  "info": {
    "name": "IBM Containers List all Docker images that are available in your private Bluemix registry.",
    "_postman_id": "b28ffc53-7613-4d9a-89dd-7b4e1f131a5f",
    "description": "This endpoint returns a list of all available Docker images in a private Bluemix registry (corresponding IBM Containers command: `cf ic images`.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Images",
      "item": [
        {
          "id": "51591282-6082-4b79-91a4-cfa631dd4b98",
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
              "id": "647bcc0f-536b-4f48-9a59-9ac76d5d6307"
            }
          ]
        }
      ]
    }
  ]
}
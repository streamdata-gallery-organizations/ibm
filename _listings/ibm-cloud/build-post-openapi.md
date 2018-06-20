---
swagger: "2.0"
x-collection-name: IBM Cloud
x-complete: 0
info:
  title: IBM Containers Build a Docker image from a Dockerfile
  description: |-
    This API builds a new container image from a Dockerfile that is stored on your local machine and pushes the image to the private Bluemix registry (corresponding IBM Containers command: `cf ic build`).

     To push an image to your Bluemix registry, a namespace must be set for the organization. Run `cf ic namespace get` or call the `GET /registry/namespaces` API to check if a namespace is already set. If not, run `cf ic namespace set NAMESPACE` or call the `PUT /registry/namespaces/{namespace}` API to set a namespace for your organization.
  version: 3.0.0
host: containers-api.ng.bluemix.net
basePath: /v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /build:
    post:
      summary: Build a Docker image from a Dockerfile
      description: |-
        This API builds a new container image from a Dockerfile that is stored on your local machine and pushes the image to the private Bluemix registry (corresponding IBM Containers command: `cf ic build`).

         To push an image to your Bluemix registry, a namespace must be set for the organization. Run `cf ic namespace get` or call the `GET /registry/namespaces` API to check if a namespace is already set. If not, run `cf ic namespace set NAMESPACE` or call the `PUT /registry/namespaces/{namespace}` API to set a namespace for your organization.
      operationId: this-api-builds-a-new-container-image-from-a-dockerfile-that-is-stored-on-your-local-machine-and-pus
      x-api-path-slug: build-post
      parameters:
      - in: body
        name: file
        description: Must be the content of a tar archive compressed with gzip
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: nocache
        description: If you set the query parameter to `nocache=true`, `nocache=True`,
          or `nocache=1`, the cache will not be used to build your image
      - in: query
        name: pull
        description: If set to pull=true, pull=True, or pull=1, then a newer version
          of the image is always attempted to be pulled even though an older version
          of the image exists locally
      - in: query
        name: q
        description: You can choose whether or not to show the verbose build output
          to review every step during the container image build
      - in: query
        name: t
        description: 'Tag the image with the full path to your private Bluemix registry
          in the following format: `t=registry'
      - in: header
        name: X-Auth-Project-Id
        description: The unique ID of your organization space where you want to create
          or work with your containers
      - in: header
        name: X-Auth-Token
        description: The Bluemix JSON web token that you receive when logging into
          Bluemix
      responses:
        200:
          description: OK
      tags:
      - Build
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---
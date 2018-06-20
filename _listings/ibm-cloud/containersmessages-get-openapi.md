---
swagger: "2.0"
x-collection-name: IBM Cloud
x-complete: 0
info:
  title: IBM Containers List messages for the user
  description: This endpoint retrieves all IBM Containers system messages for the
    user.
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
  /containers/create:
    post:
      summary: Create and start a single container
      description: "This endpoint creates and starts a single container in your space
        based on the Docker image that is specified in the Image field of the request
        json. A single container in IBM Containers is similar to a container that
        you create in your local Docker environment. Single containers are a good
        way to start with IBM Containers and to learn about how containers work in
        the IBM Cloud and the features that IBM Containers provides. They are also
        recommended when you want to run simple app tests or during the development
        process of an app. \n\n In the Docker API there are two separate APIs to create
        and start a container. However in IBM Containers a container is created and
        started in a single API call. Therefore, this API merges parameters from the
        Docker API to create and start container. \n\n To create a container with
        IBM Containers, you must at least define the image that the container is based
        on.\n\n- Image: You must include the full path to the image in your private
        Bluemix registry in the format: `registry.ng.bluemix.net/<namespace>/<image>`."
      operationId: this-endpoint-creates-and-starts-a-single-container-in-your-space-based-on-the-docker-image-that-is-
      x-api-path-slug: containerscreate-post
      parameters:
      - in: query
        name: name
        description: Choose a name for your container
      - in: body
        name: Param
        description: Summary of input parameter to create a container in IBM Containers
        schema:
          $ref: '#/definitions/holder'
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
      - Containers
      - Create
  /containers/floating-ips:
    get:
      summary: List available public IP addresses in a space
      description: 'This endpoint returns a list of all public IP addresses that are
        allocated to a space and not bound to a container. If you want to list all
        public IP addresses that are allocated to a space, even those that are already
        bound to a container, use the `all` query parameter (corrsponding IBM Containers
        command: `cf ic ip list`).'
      operationId: this-endpoint-returns-a-list-of-all-public-ip-addresses-that-are-allocated-to-a-space-and-not-bound-
      x-api-path-slug: containersfloatingips-get
      parameters:
      - in: query
        name: all
        description: If this option is set to `all=1`, `all=True`, or `all=true`,
          all public IP addresses that are allocated to a space are returned
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
      - Containers
      - Floating-ips
  /containers/floating-ips/request:
    post:
      summary: Request a public IP address for a space
      description: 'This endpoint requests a new public IP address for a space (corresponding
        IBM Containers command: `cf ic ip request`). The number of public IP addresses
        depends on the quota that is assigned to the space. If there is not enough
        quota left to request a new public IP address, you can either contact your
        organization manager to increase the quota, or unbind an existing IP address
        from a container by running `cf ic ip unbind <ip_adress> <container>` command,
        or  calling the `POST /container/{name_or_id}/floating-ips/{ip}/unbind` endpoint.'
      operationId: this-endpoint-requests-a-new-public-ip-address-for-a-space-corresponding-ibm-containers-command-cf-i
      x-api-path-slug: containersfloatingipsrequest-post
      parameters:
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
      - Containers
      - Floating-ips
      - Request
  /containers/floating-ips/{ip}/release:
    post:
      summary: Release public IP address
      description: 'This endpoint releases a public IP address from a space (corresponding
        IBM Containers command: `cf ic ip release <ip_adress>`). The public IP address
        is no longer allocated to the space. If a container was bound to the IP address,
        it is automatically unbound.'
      operationId: this-endpoint-releases-a-public-ip-address-from-a-space-corresponding-ibm-containers-command-cf-ic-i
      x-api-path-slug: containersfloatingipsiprelease-post
      parameters:
      - in: path
        name: ip
        description: The public IP address that you want to release
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
      - Containers
      - Floating-ips
      - Ip
      - Release
  /containers/groups:
    get:
      summary: List all container groups in a space
      description: 'This endpoint returns a list of all container groups in a space
        independent of their current state. (corresponding IBM Containers command:
        `cf ic group list`).'
      operationId: this-endpoint-returns-a-list-of-all-container-groups-in-a-space-independent-of-their-current-state--
      x-api-path-slug: containersgroups-get
      parameters:
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
      - Containers
      - Groups
    post:
      summary: Create and start a container group.
      description: "This endpoint creates and starts a new container group in your
        space. A container group consists of two or more single containers that are
        all created from the same container image and as a consequence are configured
        in the same way. Container groups offer different options at no cost to make
        your app highly available, such as in-built load balancing, auto-recovery
        of unhealthy container instances, and auto-scaling of container instances
        based on CPU and memory usage.\n\nTo create a container group with IBM Containers,
        you must at least define a container group name and the image that the container
        group is based on. Required attributes:\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n-
        Name: The container group name must start with a letter and then can include
        uppercase letters, lowercase letters, numbers, periods (.), underscores (_),
        or hyphens (-). \n- Image: You must include the full path to the image in
        your private Bluemix registry in the format:`registry.ng.bluemix.net/<namespace>/<image>`."
      operationId: this-endpoint-creates-and-starts-a-new-container-group-in-your-space--a-container-group-consists-of-
      x-api-path-slug: containersgroups-post
      parameters:
      - in: body
        name: RequiredAttributes
        description: Attributes that are required to create a container group in your
          space
        schema:
          $ref: '#/definitions/holder'
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
      - Containers
      - Groups
  /containers/groups/{name_or_id}:
    delete:
      summary: Stop and delete all container instances in a container group.
      description: 'Stops and deletes the container instances that run in a container
        group (corresponding IBM Containers command: `cf ic group rm <group_name>`).
        When you delete a container group, all floating private IP addresses are released.'
      operationId: stops-and-deletes-the-container-instances-that-run-in-a-container-group-corresponding-ibm-containers
      x-api-path-slug: containersgroupsname-or-id-delete
      parameters:
      - in: query
        name: force
        description: If you want to force the deletion of a container group that has
          running container instances, use the force option
      - in: path
        name: name_or_id
        description: The name or unique ID of the container group that you want to
          delete
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
      - Containers
      - Groups
      - Name
    get:
      summary: Inspect a container group.
      description: 'This endpoint retrieves detailed information about a container
        group with a given name (corresponding IBM Containers command: `cf ic group
        inspect GROUP`).'
      operationId: this-endpoint-retrieves-detailed-information-about-a-container-group-with-a-given-name-corresponding
      x-api-path-slug: containersgroupsname-or-id-get
      parameters:
      - in: path
        name: name_or_id
        description: The name or unique ID of the container group that you want to
          inspect
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
      - Containers
      - Groups
      - Name
    patch:
      summary: Update a container group.
      description: "Update the number of container instances that run in a container
        group (corresponding IBM Containers command: `cf ic group update <option>
        <group>`). \n\nNote: You can run only one update at a time.  \n\n The desired
        number is the number of container instances that you require. It must be within
        the current limits of Max and Min. To increase the number of desired container
        instances above the Max value, you must first execute an update on the Max
        value. Once this update is completed, you can increase the desired number
        of container instances."
      operationId: update-the-number-of-container-instances-that-run-in-a-container-group-corresponding-ibm-containers-
      x-api-path-slug: containersgroupsname-or-id-patch
      parameters:
      - in: path
        name: name_or_id
        description: The name or unique ID of the container group that you want to
          update
      - in: body
        name: Updates
        description: The container group parameter that you want to update
        schema:
          $ref: '#/definitions/holder'
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
      - Containers
      - Groups
      - Name
  /containers/groups/{name_or_id}/maproute:
    post:
      summary: Map a public route to a container group.
      description: 'If you want your container group to be accessible from the Internet,
        you need to expose a public port and map a public route to it (corresponding
        IBM Containers command: `cf ic route map -n <host> -d <domain> <group>`).
        Every route consists of the host name and domain.'
      operationId: if-you-want-your-container-group-to-be-accessible-from-the-internet-you-need-to-expose-a-public-port
      x-api-path-slug: containersgroupsname-or-idmaproute-post
      parameters:
      - in: path
        name: name_or_id
        description: The name or unique ID of the container group to which you want
          to map a public route
      - in: body
        name: Route
        description: The public route that is mapped to the container group
        schema:
          $ref: '#/definitions/holder'
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
      - Containers
      - Groups
      - Name
      - Maproute
  /containers/groups/{name_or_id}/unmaproute:
    post:
      summary: Unmap a public route from a container group
      description: "This endpoint unmaps a public route from a container group (corresponding
        IBM Containers command: `cf ic route unmap -n <host> -d <domain> <group>`).
        If no other public route is mapped to the container group, then the container
        group is no longer available from the internet. \n\n When you unmap a route
        from a container group, the route is not deleted and can be mapped to other
        container groups."
      operationId: this-endpoint-unmaps-a-public-route-from-a-container-group-corresponding-ibm-containers-command-cf-i
      x-api-path-slug: containersgroupsname-or-idunmaproute-post
      parameters:
      - in: path
        name: name_or_id
        description: The name or unique ID (UUID) of the container group that you
          want to inspect
      - in: body
        name: Route
        description: The public route that is unmapped from the container group
        schema:
          $ref: '#/definitions/holder'
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
      - Containers
      - Groups
      - Name
      - Unmaproute
  /containers/json:
    get:
      summary: List single containers in a space.
      description: 'This endpoint returns a list of all single containers in a space
        that are currently in a running state (corresponding IBM Containers command:
        `cf ic ps`). To list all single containers independent of their current state,
        set the `all` query parameter to true.'
      operationId: this-endpoint-returns-a-list-of-all-single-containers-in-a-space-that-are-currently-in-a-running-sta
      x-api-path-slug: containersjson-get
      parameters:
      - in: query
        name: all
        description: By default, the `GET /containers/json` endpoint returns a list
          of all single containers in a space that are in a running state
      - in: query
        name: filters
        description: You can filter your containers by any environment variable key
          or value that is listed in the `Env` section of your CLI/ API response when
          you run the `cf ic inspect ` command, or call the `GET /containers/{id}/json`
          endpoint
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
      - Containers
      - Json
  /containers/messages:
    get:
      summary: List messages for the user
      description: This endpoint retrieves all IBM Containers system messages for
        the user.
      operationId: this-endpoint-retrieves-all-ibm-containers-system-messages-for-the-user-
      x-api-path-slug: containersmessages-get
      parameters:
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
      - Containers
      - Messages
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
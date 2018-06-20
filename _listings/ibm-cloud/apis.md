---
name: IBM Cloud
x-slug: ibm-cloud
description: The IBM Cloud has been built to help you solve problems and advance opportunities
  in a world flush with data. Whether it&rsquo;s data you possess, data outside your
  firewall, or data that&rsquo;s coming, the IBM Cloud helps you protect it, move
  it, integrate it and unlock intelligence from it &mdash; giving you what it takes
  to prevail in a competitive market.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
x-kinRank: "8"
x-alexaRank: "11207"
tags: IBM Cloud
created: "2018-06-20"
modified: "2018-06-20"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/apis.md
specificationVersion: "0.14"
apis:
- name: IBM Containers Build a Docker image from a Dockerfile
  x-api-slug: ibm-containers
  description: |-
    This API builds a new container image from a Dockerfile that is stored on your local machine and pushes the image to the private Bluemix registry (corresponding IBM Containers command: `cf ic build`).

     To push an image to your Bluemix registry, a namespace must be set for the organization. Run `cf ic namespace get` or call the `GET /registry/namespaces` API to check if a namespace is already set. If not, run `cf ic namespace set NAMESPACE` or call the `PUT /registry/namespaces/{namespace}` API to set a namespace for your organization.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//build
  tags: Build
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/build-post-openapi.md
- name: IBM Containers Create and start a single container
  x-api-slug: ibm-containers
  description: "This endpoint creates and starts a single container in your space
    based on the Docker image that is specified in the Image field of the request
    json. A single container in IBM Containers is similar to a container that you
    create in your local Docker environment. Single containers are a good way to start
    with IBM Containers and to learn about how containers work in the IBM Cloud and
    the features that IBM Containers provides. They are also recommended when you
    want to run simple app tests or during the development process of an app. \n\n
    In the Docker API there are two separate APIs to create and start a container.
    However in IBM Containers a container is created and started in a single API call.
    Therefore, this API merges parameters from the Docker API to create and start
    container. \n\n To create a container with IBM Containers, you must at least define
    the image that the container is based on.\n\n- Image: You must include the full
    path to the image in your private Bluemix registry in the format: `registry.ng.bluemix.net/<namespace>/<image>`."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/create
  tags: Containers,Create
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containerscreate-post-openapi.md
- name: IBM Containers List available public IP addresses in a space
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of all public IP addresses that are allocated
    to a space and not bound to a container. If you want to list all public IP addresses
    that are allocated to a space, even those that are already bound to a container,
    use the `all` query parameter (corrsponding IBM Containers command: `cf ic ip
    list`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/floating-ips
  tags: Containers,Floating-ips
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersfloatingips-get-openapi.md
- name: IBM Containers Request a public IP address for a space
  x-api-slug: ibm-containers
  description: 'This endpoint requests a new public IP address for a space (corresponding
    IBM Containers command: `cf ic ip request`). The number of public IP addresses
    depends on the quota that is assigned to the space. If there is not enough quota
    left to request a new public IP address, you can either contact your organization
    manager to increase the quota, or unbind an existing IP address from a container
    by running `cf ic ip unbind <ip_adress> <container>` command, or  calling the
    `POST /container/{name_or_id}/floating-ips/{ip}/unbind` endpoint.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/floating-ips/request
  tags: Containers,Floating-ips,Request
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersfloatingipsrequest-post-openapi.md
- name: IBM Containers Release public IP address
  x-api-slug: ibm-containers
  description: 'This endpoint releases a public IP address from a space (corresponding
    IBM Containers command: `cf ic ip release <ip_adress>`). The public IP address
    is no longer allocated to the space. If a container was bound to the IP address,
    it is automatically unbound.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/floating-ips/{ip}/release
  tags: Containers,Floating-ips,Ip,Release
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersfloatingipsiprelease-post-openapi.md
- name: IBM Containers List all container groups in a space
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of all container groups in a space independent
    of their current state. (corresponding IBM Containers command: `cf ic group list`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups
  tags: Containers,Groups
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroups-get-openapi.md
- name: IBM Containers Create and start a container group.
  x-api-slug: ibm-containers
  description: "This endpoint creates and starts a new container group in your space.
    A container group consists of two or more single containers that are all created
    from the same container image and as a consequence are configured in the same
    way. Container groups offer different options at no cost to make your app highly
    available, such as in-built load balancing, auto-recovery of unhealthy container
    instances, and auto-scaling of container instances based on CPU and memory usage.\n\nTo
    create a container group with IBM Containers, you must at least define a container
    group name and the image that the container group is based on. Required attributes:\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n-
    Name: The container group name must start with a letter and then can include uppercase
    letters, lowercase letters, numbers, periods (.), underscores (_), or hyphens
    (-). \n- Image: You must include the full path to the image in your private Bluemix
    registry in the format:`registry.ng.bluemix.net/<namespace>/<image>`."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups
  tags: Containers,Groups
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroups-post-openapi.md
- name: IBM Containers Stop and delete all container instances in a container group.
  x-api-slug: ibm-containers
  description: 'Stops and deletes the container instances that run in a container
    group (corresponding IBM Containers command: `cf ic group rm <group_name>`). When
    you delete a container group, all floating private IP addresses are released.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups/{name_or_id}
  tags: Containers,Groups,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroupsname-or-id-delete-openapi.md
- name: IBM Containers Inspect a container group.
  x-api-slug: ibm-containers
  description: 'This endpoint retrieves detailed information about a container group
    with a given name (corresponding IBM Containers command: `cf ic group inspect
    GROUP`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups/{name_or_id}
  tags: Containers,Groups,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroupsname-or-id-get-openapi.md
- name: IBM Containers Update a container group.
  x-api-slug: ibm-containers
  description: "Update the number of container instances that run in a container group
    (corresponding IBM Containers command: `cf ic group update <option> <group>`).
    \n\nNote: You can run only one update at a time.  \n\n The desired number is the
    number of container instances that you require. It must be within the current
    limits of Max and Min. To increase the number of desired container instances above
    the Max value, you must first execute an update on the Max value. Once this update
    is completed, you can increase the desired number of container instances."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups/{name_or_id}
  tags: Containers,Groups,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroupsname-or-id-patch-openapi.md
- name: IBM Containers Map a public route to a container group.
  x-api-slug: ibm-containers
  description: 'If you want your container group to be accessible from the Internet,
    you need to expose a public port and map a public route to it (corresponding IBM
    Containers command: `cf ic route map -n <host> -d <domain> <group>`). Every route
    consists of the host name and domain.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups/{name_or_id}/maproute
  tags: Containers,Groups,Name,Maproute
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroupsname-or-idmaproute-post-openapi.md
- name: IBM Containers Unmap a public route from a container group
  x-api-slug: ibm-containers
  description: "This endpoint unmaps a public route from a container group (corresponding
    IBM Containers command: `cf ic route unmap -n <host> -d <domain> <group>`). If
    no other public route is mapped to the container group, then the container group
    is no longer available from the internet. \n\n When you unmap a route from a container
    group, the route is not deleted and can be mapped to other container groups."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/groups/{name_or_id}/unmaproute
  tags: Containers,Groups,Name,Unmaproute
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersgroupsname-or-idunmaproute-post-openapi.md
- name: IBM Containers List single containers in a space.
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of all single containers in a space that
    are currently in a running state (corresponding IBM Containers command: `cf ic
    ps`). To list all single containers independent of their current state, set the
    `all` query parameter to true.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/json
  tags: Containers,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersjson-get-openapi.md
- name: IBM Containers List messages for the user
  x-api-slug: ibm-containers
  description: This endpoint retrieves all IBM Containers system messages for the
    user.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/messages
  tags: Containers,Messages
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersmessages-get-openapi.md
- name: IBM Containers Retrieve organization and space specific quota
  x-api-slug: ibm-containers
  description: Retrieve the quota that is assigned to the organization and space.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/quota
  tags: Containers,Quota
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersquota-get-openapi.md
- name: IBM Containers Update space quota
  x-api-slug: ibm-containers
  description: "This endpoint updates the quota that is allocated to a Bluemix space.
    \n\n **Note**: Only paid accounts are eligbile to update the space quota. If you
    are using a free-trial account, upgrade to a paid account first."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/quota
  tags: Containers,Quota
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersquota-put-openapi.md
- name: IBM Containers List container sizes and quota limits
  x-api-slug: ibm-containers
  description: "This endpoint returns a list of available container sizes and the
    quota limit and usage for the space. \n\n- Container sizes: A list of available
    container sizes indicating the amount of container memory, disk space and virtual
    CPUs that can be assigned to the container.\n- Quota limit: Lists the number of
    containers, public IP addresses, available container memory, and virtual CPUS
    that are allocated to a space. \n- Quota usage: Lists the current number of containers,
    images, and public IP addresses in a space that is counted towards your quota
    limit."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/usage
  tags: Containers,Usage
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersusage-get-openapi.md
- name: IBM Containers List latest API version
  x-api-slug: ibm-containers
  description: This endpoint retrieves a list of all microservices that are used in
    the IBM Containers service with their current build version. This method does
    not require authentication.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/version
  tags: Containers,Version
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersversion-get-openapi.md
- name: IBM Containers List the current state of a container.
  x-api-slug: ibm-containers
  description: This endpoint returns the current state of a container. This state
    can either be a transient state, such as BUILDING and NETWORKING, or a non-transient
    state, such as RUNNING, SHUTDOWN, CRASHED, or SUSPENDED.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{id}/status
  tags: Containers,Status
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersidstatus-get-openapi.md
- name: IBM Containers Remove a single container
  x-api-slug: ibm-containers
  description: 'Remove a single container that is identified by container ID or name
    from a space (corresponding IBM Containers command: `cf ic delete <container>`).
    The container must be stopped before it can be deleted, unless the `force` query
    parameter is set to true.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}
  tags: Containers,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-id-delete-openapi.md
- name: IBM Containers Bind a public IP address to a single container
  x-api-slug: ibm-containers
  description: 'This endpoint binds an available public IP address to a single container
    (corresponding IBM Containers command: `cf ic ip bind <ip_adress> <container>`).
    After a container is bound to a public IP address, it can be accessed at `https://<public_ip_adress>:<public_port>`.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/floating-ips/{ip}/bind
  tags: Containers,Name,Floating-ips,Ip,Bind
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idfloatingipsipbind-post-openapi.md
- name: IBM Containers Unbind a public IP address from a container
  x-api-slug: ibm-containers
  description: 'This endpoint unbinds a public IP address from a container (corresponding
    IBM Containers command: `cf ic ip unbind <ip_adress> <container>`). The container
    that is unbound from the IP address will not be accessible from the internet anymore.
    The public IP address will be further allocated to the space and can be used to
    be bound to other containers.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/floating-ips/{ip}/unbind
  tags: Containers,Name,Floating-ips,Ip,Unbind
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idfloatingipsipunbind-post-openapi.md
- name: IBM Containers Inspect a single container
  x-api-slug: ibm-containers
  description: 'This endpoint retrieves detailed information about a single container
    (corresponding IBM Containers command: `cf ic inspect <container>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/json
  tags: Containers,Name,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idjson-get-openapi.md
- name: IBM Containers Pause a single container
  x-api-slug: ibm-containers
  description: 'Pause all processes in a running single container with a given container
    ID or name (corresponding IBM Containers command: `cf ic pause <container>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/pause
  tags: Containers,Name,Pause
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idpause-post-openapi.md
- name: IBM Containers Rename a single container
  x-api-slug: ibm-containers
  description: 'Change the current name of an existing single container that is identified
    by the container ID or name (corresponding IBM Containers command: `cf ic rename
    <old_name> <new_name>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/rename
  tags: Containers,Name,Rename
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idrename-post-openapi.md
- name: IBM Containers Restart a single container
  x-api-slug: ibm-containers
  description: 'Restart a container with a given container ID or name (corresponding
    IBM Containers command: `cf ic restart <container>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/restart
  tags: Containers,Name,Restart
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idrestart-post-openapi.md
- name: IBM Containers Start a single container
  x-api-slug: ibm-containers
  description: 'Start a single container with a given container name or ID (corresponding
    IBM Containers command: `cf ic start <container>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/start
  tags: Containers,Name,Start
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idstart-post-openapi.md
- name: IBM Containers Stop a single container
  x-api-slug: ibm-containers
  description: 'Stop a single container with a given container name or ID (corresponding
    IBM Containers command: `cf ic stop <container>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/stop
  tags: Containers,Name,Stop
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idstop-post-openapi.md
- name: IBM Containers Unpause a single container
  x-api-slug: ibm-containers
  description: 'Unpause all processes that are currently stopped inside a single containers
    with a given container ID or name (corresponding IBM Containers command: `cf ic
    unpause <container>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//containers/{name_or_id}/unpause
  tags: Containers,Name,Unpause
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/containersname-or-idunpause-post-openapi.md
- name: IBM Containers List all Docker images that are available in your private Bluemix
    registry.
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of all available Docker images in a private
    Bluemix registry (corresponding IBM Containers command: `cf ic images`.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//images/json
  tags: Images,Json
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/imagesjson-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/imagesjson-get-openapi.md
- name: IBM Containers Remove a Docker image.
  x-api-slug: ibm-containers
  description: 'Remove a Docker image from the private Bluemix registry that is identified
    by the image ID (corresponding IBM Containers command: `cf ic rmi <image>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//images/{id}
  tags: Images
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/imagesid-delete-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/imagesid-delete-openapi.md
- name: IBM Containers Inspect a Docker image in private Bluemix registry
  x-api-slug: ibm-containers
  description: 'This endpoint returns detailed information about a Docker image that
    is stored in the private Bluemix registry of an organization (corresponding IBM
    Containers command: `cf ic inspect <image_name_or_id>`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//images/{name_or_id}/json
  tags: Images,Name,Json
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/imagesname-or-idjson-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/imagesname-or-idjson-get-openapi.md
- name: IBM Containers Retrieve the namespace of an organization.
  x-api-slug: ibm-containers
  description: 'This endpoint retrieves the namespace that was set for the organization
    that owns the current space (corresponding IBM Containers command: `cf ic namespace
    get`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//registry/namespaces
  tags: Registry,Namespaces
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/registrynamespaces-get-openapi.md
- name: IBM Containers Check the availability of a namespace
  x-api-slug: ibm-containers
  description: "This endpoint checks whether a namespace is available in Bluemix and
    can be used to set up the private Docker images registry for an organization.
    When a HTTP code `201 Ok` is returned, the namespace is already assigned to another
    organization in Bluemix and cannot be used. When a HTTP code `404 Not found` is
    returned, the namespace can be used for your organization. \n\n Consider the following
    rules when choosing a namespace for your organization: \n\n- Every organization
    can have one namespace at a time only \n- The namespace must be unique in Bluemix.
    \n- The namespace can be 4-30 characters long. \n- The namespace must start with
    at least one letter or number. \n- The namespace can only contain lowercase letters,
    numbers or underscores (_)."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//registry/namespaces/{namespace}
  tags: Registry,Namespaces,Namespace
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/registrynamespacesnamespace-get-openapi.md
- name: IBM Containers Set a namespace for your private Bluemix registry.
  x-api-slug: ibm-containers
  description: "Set up your own Docker images registry in Bluemix by defining a namespace
    for your organization (corresponding IBM Containers command: `cf ic namespace
    set <namespace>`). The namespace is used to generate a unique URL to your private
    Bluemix registry. In your private registry you store all Docker images that you
    want to share across your organization. To create a container from an image, you
    must first push the image to your registry. \n\n The namespace cannot be changed
    after is has been set. Consider the following rules to choose a namespace for
    your organization: \n\n- Every organization can have one namespace at a time only
    \n- The namespace must be unique in Bluemix. \n- The namespace can be 4-30 characters
    long. \n- The namespace must start with at least one letter or number. \n- The
    namespace can only contain lowercase letters, numbers or underscores (_)."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//registry/namespaces/{namespace}
  tags: Registry,Namespaces,Namespace
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/registrynamespacesnamespace-put-openapi.md
- name: IBM Containers Retrieve the TLS Certificate
  x-api-slug: ibm-containers
  description: 'This endpoint returns the TLS (Transport Layer Security) certificate
    to the user (corresponding IBM Containers command: `cf ic login`). The TLS certificate
    is a SSL certificate that is used to authenticate the user''s CLI with the IBM
    Containers service and to establish a secure communication between the user''s
    local machine and the container in Bluemix.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//tlskey
  tags: Tlskey
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/tlskey-get-openapi.md
- name: IBM Containers Refresh the TLS Certificate
  x-api-slug: ibm-containers
  description: 'This endpoint requests to generate a new TLS (Transport Layer Security)
    certificate on the server and to update the existing user TLS certificate (corresponding
    IBM Containers command: `cf ic init`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//tlskey/refresh
  tags: Tlskey,Refresh
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/tlskeyrefresh-put-openapi.md
- name: IBM Containers Create a volume in a space
  x-api-slug: ibm-containers
  description: "This endpoints creates a new volume in your space (corresponding IBM
    Containers command: `cf ic volume create VOLNAME`). A volume is used to persist
    and access app data between container restarts. Volumes are hosted on file shares
    that define the available actual storage in Bluemix and the number of input and
    output transactions per second (IOPS). \n\n After you have created a volume, you
    must mount it to a container by using the `--volume` option in the `cf ic run`
    (single containers) or `cf ic group create` (container groups) command. You can
    also define the volume as part of the HTTP body and send a request to the `POST
    /containers/create` (single containers) or `POST /containers/groups` (container
    groups) endpoints. \n\n Note: If you mount multiple containers in a space to the
    same volume, they share the data in the volume and can access them anytime. When
    a container is deleted, the associated volume is not removed."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/create
  tags: Volumes,Create
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumescreate-post-openapi.md
- name: IBM Containers Create a file share in a space
  x-api-slug: ibm-containers
  description: "This endpoint creates a new file share in a space (corresponding IBM
    Containers command: `cf ic volume fs-create FSNAME FSSIZE FSIOPS`). \n\n A file
    share is a persistent NFS-based (Network File System) storage system that hosts
    Docker volumes in a Bluemix space and allows a user to store and access container
    and app-related files. To store files in a file share, you must create a container
    volume and save the data into this volume.\n\n As soon as you create your first
    volume in a space with the `cf ic volume create VOLNAME` command or the `POST
    /volumes/create` API endpoint, a default file share with 20 GB at 4 IOPS (Input
    Output operations Per Second) is created at no cost. \n\nThe organization manager
    can create file shares with specific storage size and IOPS to meet the storage
    needs of the space. File shares can be provisioned in sizes from 20 GB to 12 TB
    and at IOPS per GB of 0.25, 2 or 4. Run `cf ic volume fs-flavor-list` or call
    the `GET /volumes/fs/flavors/json` API endpoint to retrieve a list of available
    file share sizes. The file share size in relation to the number of IOPS impacts
    the speed that data can be read and written from and to the container volume."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/fs/create
  tags: Volumes,Create
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesfscreate-post-openapi.md
- name: IBM Containers List available file share sizes
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of available file shares in gigabyte
    (corresponding IBM Containers command: `cf ic volume fs-flavor-list`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/fs/flavors/json
  tags: Volumes,Flavors,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesfsflavorsjson-get-openapi.md
- name: IBM Containers List available file shares in a space
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of all file shares that are availble
    in a space (corresponding IBM Containers command: `cf ic volume fs-list`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/fs/json
  tags: Volumes,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesfsjson-get-openapi.md
- name: IBM Containers Delete a file share
  x-api-slug: ibm-containers
  description: "This endpoint deletes a file share from a space (corresponding IBM
    Containers command: `cf ic volume fs-rm FSNAME`).\n\n Before you can delete a
    file share, all mounted volumes must be deleted first. To delete a volume, run
    `cf ic volume rm VOLNAME` or call the `DELETE /volumes/{name}` API endpoint. \n\n
    **Note:** To delete a file share you must have been granted organization developer
    rights."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/fs/{name}
  tags: Volumes,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesfsname-delete-openapi.md
- name: IBM Containers Inspect a file share
  x-api-slug: ibm-containers
  description: 'This endpoint returns detailed information about a file share (corresponding
    IBM Containers command: `cf ic volume fs-inspect FSNAME`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/fs/{name}/json
  tags: Volumes,Name,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesfsnamejson-get-openapi.md
- name: IBM Containers List all volumes for a space
  x-api-slug: ibm-containers
  description: 'This endpoint returns a list of all volumes that are available in
    the given space (corresponding IBM Containers command: `cf ic volume list`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/json
  tags: Volumes,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesjson-get-openapi.md
- name: IBM Containers Delete a volume
  x-api-slug: ibm-containers
  description: 'Delete a volume with a given name from a space (corresponding IBM
    Containers command: `cf ic volume rm VOLNAME`). To delete a volume, all mounted
    containers must be unmounted first. After the volume is deleted, the data that
    are stored in the volume are lost.'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/{name}
  tags: Volumes,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesname-delete-openapi.md
- name: IBM Containers Share a volume with another space
  x-api-slug: ibm-containers
  description: This endpoint provisions an existing volume that was created in one
    space to another space within the same organization. Single containers and container
    groups in each space can read and write to the shared volume. The volume remains
    owned by the original space it was created in, including management and billing.
    For example, the volume can be deleted from the original space only.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/{name}
  tags: Volumes,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesname-post-openapi.md
- name: IBM Containers Retrieve detailed information about a volume.
  x-api-slug: ibm-containers
  description: 'Retrieve a detailed list of information about a volume that is identified
    by the volume name (corresponding IBM Containers command: `cf ic volume inspect
    VOLNAME`).'
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3//volumes/{name}/json
  tags: Volumes,Name,Json
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/volumesnamejson-get-openapi.md
- name: IBM Containers
  x-api-slug: ibm-containers
  description: The IBM Cloud has been built to help you solve problems and advance
    opportunities in a world flush with data. Whether it&rsquo;s data you possess,
    data outside your firewall, or data that&rsquo;s coming, the IBM Cloud helps you
    protect it, move it, integrate it and unlock intelligence from it &mdash; giving
    you what it takes to prevail in a competitive market.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28560-ibm-containers.jpg
  humanURL: https://www.ibm.com/cloud/
  baseURL: https://containers-api.ng.bluemix.net//v3
  tags: IBM Cloud
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/ibm-cloud/master/_listings/ibm-cloud/openapi.md
x-common:
- type: x-blog
  url: https://www.ibm.com/blogs/bluemix/
- type: x-crunchbase
  url: https://crunchbase.com/organization/product/ibm-bluemix
- type: x-documentation
  url: https://console.bluemix.net/docs/
- type: x-github
  url: https://github.com/IBM-Cloud
- type: x-twitter
  url: https://twitter.com/IBMcloud
- type: x-website
  url: https://www.ibm.com/cloud/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---
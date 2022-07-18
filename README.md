<h1 align="center">Yenno</h1>
Yenno helps ML related lab dynamically try different deployment options on their own kubernetes cluster.

[Work In Progress]

### Prerequisite:

- Code should be placed in Github repository (public / private)
- Need to have specific docker file structure with shell script

    For multiple service inside mono repo), docker file need to be placed like below

    Use docker-compose here ?

    ```
    build/
        Dockerfile_<service_name_1>
        Dockerfile_<service_name_2>
        ...
        Dockerfile_<service_name_3>
    ```

- Verify local k8s service ssh authentication
- Pass local k8s system check

### Frontend functions userflow:

- Login with google
- Create Project in our system
- Input github repo link

👇 After **continuous auto integration (CI)** done ✅ 👇

<aside>
💡 Following configuration will be store as CONFIGURATION ENTITY

</aside>

- User can select “which image should deploy on which node”
    - Get node information
    - Get user service information (ex: How many service)
- User can select number of replicas for each image
- User can configure how much memory and CPU
    - Get local k8s cluster system information first during verification
- User can specify each replicas’ node !! (need research native k8s solution) <pending>

👇 After **continuous auto deployment (CD)** done ✅ 👇

- Provide k8s cluster information (update periodically, like k8s dash board)
    - Get from dash board API ?
- We will store your configuration option !
    - Configuration history
    - Favorite configuration
- Change deployment option dynamically

### Continuous auto integration (CI):

- docker file structure checking
- Generate corresponding shell for docker image building and uploading (using [kosko](https://github.com/tommy351/kosko))
- Publish and store all service images inside our own server storage (as image registry) & show all image

### Continuous auto deployment (CD):

- Support k8s local cluster ✨
    - Automatic SSH authentication for user
    - Check k8s status (ex: node status, control plane status, CNI status) No related work !!
- Support micro services deployment ✨
- Support FL model deployment
- Can specify which node to deploy ✨
- Remember custom configuration option  ✨

**future work (will no be done in this level of work):**

- Draw system graph based on user configuration
- Support online cloud service
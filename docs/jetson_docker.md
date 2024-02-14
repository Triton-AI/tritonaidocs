# Docker Guide for Jetson Xavier NX

## Essential Docker Commands

- To start an existing container which is stopped
  - `docker start <container-name/ID>`
- To stop a running container
  - `docker stop <container-name/ID>`
- Then to login to the interactive shell of a container
  - `docker exec -it <container-name/ID> bash`
- To start an existing container and attach to it in one command
  - `docker start -ai <container-name/ID>`

### Specifications for Docker Commands  

#### `docker run`

The `docker run` command first **creates** a writeable container layer over the specified image, and then **starts** it using the specified command.


```bash
# Create and run a new container from an image with image_name and tag
sudo docker run --runtime nvidia -it --rm --network=host image_name:tag
# OR
# Create and run a new container from an image with image_id
sudo docker run --runtime nvidia -it --rm --network=host image_id 
```


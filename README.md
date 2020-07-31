# Docker General
The general Docker repository.

## Ubuntu
Container image based on Ubuntu 18.04 LTS. 

Contains the following software: 
- Azure CLI (latest)
- Git (latest)
- Terraform (12.28)

### Build Image
`docker build -t ubuntu:v1 -f source/ubuntu/Dockerfile .`

### Create and Run Container
`docker run -it ubuntu:v1`
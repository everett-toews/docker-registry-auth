### Building local image

```
git clone https://github.com/rcbops/docker-registry-auth.git
cd docker_auth/auth_server
docker build -t quay.io/rackspace/registry-auth .
docker push quay.io/rackspace/registry-auth
```

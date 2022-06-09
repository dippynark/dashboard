# Build

```sh
TAG="v0.26.0"
git checkout $TAG
export KO_DOCKER_REPO=hgkeacct/tekton-dashboard
ko build ./cmd/dashboard --bare -t $TAG
```

```sh
TAG="v0.26.0"
git checkout $TAG
# Start Docker daemon
IMAGE=$(ko build ./cmd/dashboard --push=false -L)
docker tag $IMAGE hgkeacct/tekton-dashboard:$TAG
docker push hgkeacct/tekton-dashboard:$TAG
```

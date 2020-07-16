
make docker-image

docker tag quay.io/dexidp/dex:$(shell ./scripts/git-version) akiicat/dex

chmod 777 examples

docker run -v ~/go/src/github.com/akiilab/dex/examples:/examples -p 5556:5556 akiicat/dex serve examples/config-dev.yaml


## Known Issue

### Get Remote IP in Container (Solved)

- [Document how to get real remote client ip for service running in container](https://github.com/moby/moby/issues/15086)
- [Support `--net=host` through kubelet](https://github.com/kubernetes/kubernetes/issues/175)
- [Starting a container with host networking enabled](https://github.com/kubernetes/kubernetes/issues/19171#issuecomment-167956754)

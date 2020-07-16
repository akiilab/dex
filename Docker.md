
make docker-image

docker tag quay.io/dexidp/dex:$(shell ./scripts/git-version) akiicat/dex

chmod 777 examples

docker run -v ~/go/src/github.com/akiilab/dex/examples:/examples -p 5556:5556 akiicat/dex serve examples/config-dev.yaml



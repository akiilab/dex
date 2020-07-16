
make docker-image

docker tag quay.io/dexidp/dex:$(shell ./scripts/git-version) dex:v1

chmod 777 examples

docker run -v ~/go/src/github.com/akiilab/dex/examples:/examples -p 5556:5556 dex:v1 serve examples/config-dex.yaml



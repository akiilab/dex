
make docker-image

docker tag quay.io/dexidp/dex:$(shell ./scripts/git-version) dex:v1

chmod 666 examples/dex.db

docker run -v ~/dex/go/src/github.com/dexidp/dex/examples:/examples -p 5556:5556 dex:v1 serve /config/config-dex.yaml



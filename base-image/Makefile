.PHONY: all
all: build-alpine-edge build-nodejs20-debian12 build-base-debian12 build-static-debian12;$(info $(M)...Begin to test and build all of binary.) @ ## Test and build all of binary.

REPO ?= 2030047311
EDGE_TAG ?= edge

build-alpine-edge:
	docker buildx use my-builder-proxy
	docker buildx build -f ./alpine/Dockerfile --platform linux/amd64,linux/arm64 --push -t ${REPO}/alpine:${EDGE_TAG} ./alpine/
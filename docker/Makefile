#
# Docker image tagging
#
DOCKER_VERSION_TAG ?= "latest"

H2OAI_COMMIT := $(shell git rev-parse HEAD)

.NOTPARALLEL: all

docker-runtime:
	@echo "+--Building Runtime Docker Image--+"
	docker build -t mr-h2o3-runtime:${DOCKER_VERSION_TAG} -f Dockerfile .

build-h2o-3:
	@echo "+--Building H2O-3--+"
	@echo
	@echo "+--Cleaning--+"
	cd ..; ./gradlew clean
	@echo
	@echo "+--Building--+"
	cd ..; ./gradlew build -x test

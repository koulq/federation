# Copyright 2017 The Kubernetes Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Build the fcp image.
#
# Usage:
#   [ARCH=amd64] [REGISTRY="gcr.io/google-containers"] make (build|push) 
# TODO (irfan) figure out a proper release strategy, including version and what all bins
# VERSION={some_released_version_of_kubernetes}

REGISTRY?=gcr.io/google-containers
ARCH?=amd64
FCP_BIN?=_output/dockerized/bin/linux/$(ARCH)/fcp
VERSION?=1.0

# TODO(@irfan) : do we need to rather build our own image from scratch
BASEIMAGE=gcr.io/google-containers/debian-hyperkube-base-$(ARCH):0.7
TEMP_DIR:=$(shell mktemp -d -t fcpXXXXXX)

all: build

build:
	cp -r ./* ${TEMP_DIR}
	cp ../${FCP_BIN} ${TEMP_DIR}

	chmod a+rx ${TEMP_DIR}/fcp

	cd ${TEMP_DIR} && sed -i.back "s|BASEIMAGE|${BASEIMAGE}|g" Dockerfile

	docker build --pull -t ${REGISTRY}/fcp-${ARCH}:${VERSION} ${TEMP_DIR}
	rm -rf "${TEMP_DIR}"

push: build
	docker -- push ${REGISTRY}/fcp-${ARCH}:${VERSION}

.PHONY: build push all

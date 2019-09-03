usage:
	echo 'Usage: make (py27and35|py37)'
.PHONY: usage

../.cache/cupy:
	mkdir -p ../.cache
	git clone https://github.com/cupy/cupy.git ../.cache/cupy

docker.%: cupy.chainer-prep.%.Dockerfile ../.cache/cupy
	cd ../.cache/cupy && \
	docker build -f $(shell pwd)/cupy.chainer-prep.$*.Dockerfile .
.PHONY: docker.%

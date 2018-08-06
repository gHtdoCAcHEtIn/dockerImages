all: cuda_apt_py

## cuda 8.0
cuda80py2:
	docker build -t global/cuda_py:8.0py2 -f Dockerfile --rm --build-arg CUDA_VERSION=8.0 --build-arg PYTHON=python .

## cuda 9.0 python2
cuda90py2:	
	docker build -t global/cuda_py:9.0py2 -f Dockerfile --rm --build-arg CUDA_VERSION=9.0 --build-arg PYTHON=python .

## cuda 9.0 python3
cuda90py3:
	docker build -t global/cuda_py:9.0py3 -f Dockerfile --rm --build-arg CUDA_VERSION=9.0 --build-arg PYTHON=python3 .

## cuda 9.1 python2
cuda91py2:	
	docker build -t global/cuda_py:9.1py2 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.1 --build-arg PYTHON=python

## cuda 9.1 python3
cuda91py3:
	docker build -t global/cuda_py:9.1py3 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.1 --build-arg PYTHON=python3

## cuda 9.2 python2
cuda92py2:	
	docker build -t global/cuda_py:9.2py2 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.2 --build-arg PYTHON=python

## cuda 9.2 python3
cuda92py3:
	docker build -t global/cuda_py:9.2py3 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.2 --build-arg PYTHON=python3

# cuda8
cuda80: cuda80py2
cuda8: cuda80

# cuda9
cuda90:	cuda90py2 cuda90py3
cuda91: cuda91py2 cuda91py3
cuda92: cuda92py2 cuda92py3
cuda9: cuda90

cuda_apt_py: cuda8 cuda9


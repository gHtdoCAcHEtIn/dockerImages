all: cuda80py2 cuda90py2 cuda90py3

## cuda 8.0
cuda80py2:
	docker build -t global/dl:cuda80.py2 -f Dockerfile.gpu.cuda8 --rm --build-arg CUDA_VERSION=8.0 --build-arg PYTHON=python .

## cuda 9.0
cuda90py2:	
	docker build -t global/dl:cuda90.py2 -f Dockerfile.gpu.cuda9.py2 --rm --build-arg CUDA_VERSION=9.0 --build-arg PYTHON=python .
cuda90py3:
	docker build -t global/dl:cuda90.py3 -f Dockerfile.gpu.cuda9.py3 --rm --build-arg CUDA_VERSION=9.0 --build-arg PYTHON=python3 .

## cuda 9.1
cuda91py2:	
	docker build -t global/dl:cuda91.py2 -f Dockerfile.gpu.cuda9.py2 --rm --build-arg CUDA_VERSION=9.1 --build-arg PYTHON=python .
cuda91py3:
	docker build -t global/dl:cuda91.py3 -f Dockerfile.gpu.cuda9.py3 --rm --build-arg CUDA_VERSION=9.1 --build-arg PYTHON=python3 .

## cuda 9.2
cuda92py2:	
	docker build -t global/dl:cuda92.py2 -f Dockerfile.gpu.cuda9.py2 --rm --build-arg CUDA_VERSION=9.2 --build-arg PYTHON=python .
cuda92py3:
	docker build -t global/dl:cuda92.py3 -f Dockerfile.gpu.cuda9.py3 --rm --build-arg CUDA_VERSION=9.2 --build-arg PYTHON=python3 .

# cuda8
cuda8: cuda80py2

# cuda9
cuda90:	cuda90py2 cuda90py3
cuda91: cuda91py2 cuda91py3
cuda9: cuda90

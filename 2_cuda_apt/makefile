all: cuda_apt

cuda80:
	docker build -t global/cuda:8.0 -f Dockerfile --rm . --build-arg CUDA_VERSION=8.0 --build-arg CUDNN_VERSION=6

cuda90:	
	docker build -t global/cuda:9.0 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.0 --build-arg CUDNN_VERSION=7

cuda91:
	docker build -t global/cuda:9.1 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.1 --build-arg CUDNN_VERSION=7

cuda92:
	docker build -t global/cuda:9.2 -f Dockerfile --rm . --build-arg CUDA_VERSION=9.2 --build-arg CUDNN_VERSION=7
	
cuda_apt: cuda80 cuda90

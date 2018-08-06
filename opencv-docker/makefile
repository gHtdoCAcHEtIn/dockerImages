all: opencv_contrib

## cuda 9.0 py2
opencv_contrib:
	docker build -t nrca/opencv_contrib:cuda90py2 -f Dockerfile --rm --build-arg CUDA_VERSION=9.0 --build-arg PYTHON=python .



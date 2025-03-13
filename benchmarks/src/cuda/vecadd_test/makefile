SHELL := /bin/bash

GPGPU_ENV=source ${GPGPU_SIM_ROOT}/setup_environment debug

all:
	${GPGPU_ENV} && echo $$LD_LIBRARY_PATH && nvcc --cudart shared -g -O0 -o test1.out test1.cu
#	${GPGPU_ENV} && nvcc --cudart shared -L/workspaces/gpgpu-sim_distribution/lib/gcc-11.4.0/cuda-12080/release -lcudart test1.cu -o test1
	ldd test1.out | grep libcudart

static:
	nvcc test1.cu -o test1

run:
	./test1.out | tee ./run.log

clean:
	rm -rf test1.out a.out test.out _cuobjdump_list_ptx_* _app_cuda_version_* checkpoint_files/ *.txt *.ptx *.ptxas
# Pytorch/Skynet


python3

python3

python3Packages.pytorch

rocmPackages.rocblas

rocmPackages.miopen

rocmPackages.hipfft

rocmPackages.hipcub

  

rocm-opencl-runtime

git clone --recursive https://github.com/pytorch/pytorch 
cd pytorch

```
export MAX_JOBS=8 
export PYTORCH_ROCM_ARCH= # Set this to your GPU architecture 
export USE_ROCM=1 export USE_LMDB=1 
export USE_OPENCV=1 export ROCM_HOME=/opt/rocm
```
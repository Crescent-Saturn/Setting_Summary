# NVIDIA GPU and CUDA

> **Status:** Deprecated historical notes; current installation guidance is not verified
> **Applies to:** GPU, driver, toolkit, framework, and distribution versions must be selected together
> **Last verified:** Not tested
> **Risk:** High — driver and library changes can break the system or environment

The former Linux setup document contained commands for downloading an old cuDNN archive, copying libraries into `/usr/local/cuda`, and changing library paths. Those commands are intentionally not carried forward: they target specific legacy versions, use an obsolete download location, and do not establish compatibility with the installed driver or framework.

For a new installation:

1. Record the GPU model, operating system/release, driver, Python, and framework version.
2. Check the framework's official installation selector and NVIDIA's current compatibility documentation.
3. Prefer the framework's supported package/environment method unless a system-wide toolkit is specifically required.
4. Test with the framework's documented device query and a representative workload before considering the setup complete.

Do not mark a procedure verified until it has been tested on a stated hardware/software combination. Record a rollback plan before changing drivers or system libraries.

## Sources

- [PyTorch installation selector](https://pytorch.org/get-started/locally/)
- [NVIDIA CUDA Toolkit documentation](https://docs.nvidia.com/cuda/)
- [NVIDIA cuDNN documentation](https://docs.nvidia.com/deeplearning/cudnn/)

# Known Issues and Solutions

This document compiles common installation issues and their solutions for this repository.

## Installation Issues

### 1. GLIBCXX Version Missing

**Error:**
```shell
ImportError: /home/leonardo/miniconda3/envs/unitree-rl/bin/../lib/libstdc++.so.6: version GLIBCXX_3.4.32' not found (required by /home/leonardo/.cache/torch_extensions/py38_cu121/gymtorch/gymtorch.so)
```

**Solution:**
Update the `libstdc++` libraries in your conda environment:
```shell
conda install -c conda-forge libstdcxx-ng
```

### 2. Python Shared Library Not Found

**Error:**
```shell
ImportError: libpython3.8.so.1.0: cannot open shared object file: No such file or directory
```

**Solution:**
Add the Conda environment's library path to `LD_LIBRARY_PATH`:
```shell
export LD_LIBRARY_PATH=$CONDA_PREFIX/lib:$LD_LIBRARY_PATH
```

## Contributing

If you encounter any other issues during installation, please feel free to add them here following the same format:
1. Describe the error (including the exact error message)
2. Provide the solution with clear steps
3. Add any additional context if necessary

---
**Note:** Make sure you're using the correct Python version and have all the prerequisites installed as specified in the main README.
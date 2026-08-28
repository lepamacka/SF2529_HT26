# Labs for Inverse Problems SF2529 HT26

This repository contains Jupyter Notebooks for all labs in the course, as well as the package specifications required to build an appropriate Python environment to run [ODL](https://github.com/odlgroup/odl).

# Operator Discretization Library (ODL)

ODL is a Python library that enables the user to study and solve inverse problems by discretizing operators on function spaces and handling them in a mathematically consistent way. By working through the labs in this repository, you will learn how to make use of ODL to solve some of the standard inverse problems.

# Setting up the environment

These instructions assume that you are on a Linux system with some experience in the terminal. It may be possible to follow along on Windows, especially with WSL, but this is untested. Mac is not supported for labs 2-4. If you want help, come to the scheduled lab sessions.

The preferred way to set up the Python environment is to use [uv](https://docs.astral.sh/uv). After downloading this repository and opening it in the terminal, run ``uv sync`` to automatically download the package requirements specified in pyproject.toml and build a virtual environment, which should then be accessible in a top-level folder called ``.venv``. You can then open the Jupyter notebooks in the labs folder in an appropriate editor, e.g., VS Code, and choose as kernel the virtual environment in ``.venv``. Alternatively, you can host the notebooks locally with the command ``uv run --with jupyter jupyter lab``, which should allow you to open them in your browser.

If you prefer to build the environment yourself, the top-level package requirements are listed in pyproject.toml. Note that the instructions assume that version 1.0.0 of ODL is installed.

# Labs

The labs are in the ``labs`` folder, and should be possible to follow with the help of the linked ODL documentation. For lab 2 you must add an additional package by running ``uv sync --group astra``. For labs 3 and 4 you need GPU acceleration, unless you restrict the problem to 2D-tomography.

# GPU acceleration

The first two labs can be completed without access to an Nvidia GPU. However, labs 3 and 4 involve 3D-tomography, which ODL only allows when GPU acceleration is available. In addition, to make use of GPU resources, the optional dependencies in pyproject.toml must be installed. If you use uv this simply involves running ``uv sync --group astra``.

The plan is to provide you with access to a server with a GPU. If you wish to run labs 3 and 4 on your own, you can either restrict the problem to 2D-tomography, or you can try to set up an environment on a computer with a CUDA-capable Nvidia GPU. In the latter case, you need to ensure that [ASTRA Toolbox](https://github.com/astra-toolbox/astra-toolbox) can make use of your GPU, either by following the instructions on their Github page, or by updating your Nvidia drivers and installing a recent version of [CUDA Toolkit](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/).

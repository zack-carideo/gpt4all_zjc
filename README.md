<h1 align="center">GPT4All</h1>

<p align="center">Open-source assistant-style large language models that run locally on your CPU</p>

<p align="center">
<a href="https://gpt4all.io">GPT4All Website</a>
</p>

<p align="center">
<a href="https://docs.gpt4all.io">GPT4All Documentation</a>
</p>

<p align="center">
<a href="https://discord.gg/mGZE39AS3e">Discord</a>
</p>

<p align="center">
<a href="https://python.langchain.com/en/latest/modules/models/llms/integrations/gpt4all.html">🦜️🔗 Official Langchain Backend</a> 
</p>

<p align="center">
GPT4All is made possible by our compute partner <a href="https://www.paperspace.com/">Paperspace</a>.
</p>

<p align="center">
  <img width="600" height="365" src="https://user-images.githubusercontent.com/13879686/231876409-e3de1934-93bb-4b4b-9013-b491a969ebbc.gif">
</p>
<p align="center">
Run on an M1 macOS Device (not sped up!)
</p>

## GPT4All: An ecosystem of open-source on-edge large language models.
GPT4All is an ecosystem to train and deploy **powerful** and **customized** large language models that run locally on consumer grade CPUs. Note that your CPU needs to support [AVX or AVX2 instructions](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions).

Learn more in the [documentation](https://docs.gpt4all.io).

The goal is simple - be the best instruction tuned assistant-style language model that any person or enterprise can freely use, distribute and build on.

A GPT4All model is a 3GB - 8GB file that you can download and plug into the GPT4All open-source ecosystem software. **Nomic AI** supports and maintains this software ecosystem to enforce quality and security alongside spearheading the effort to allow any person or enterprise to easily train and deploy their own on-edge large language models. 


### Chat Client
Run any GPT4All model natively on your home desktop with the auto-updating desktop chat client. See <a href="https://gpt4all.io">GPT4All Website</a> for a full list of open-source models you can run with this powerful desktop application.

Direct Installer Links:

* [macOS](https://gpt4all.io/installers/gpt4all-installer-darwin.dmg)

* [Windows](https://gpt4all.io/installers/gpt4all-installer-win64.exe)

* [Ubuntu](https://gpt4all.io/installers/gpt4all-installer-linux.run)

Find the most up-to-date information on the [GPT4All Website](https://gpt4all.io/)

### Chat Client building and running

* Follow the visual instructions on the chat client [build_and_run](gpt4all-chat/build_and_run.md) page

### Bindings

* <a href="https://github.com/nomic-ai/gpt4all/tree/main/gpt4all-bindings/python/README.md">:snake: Official Python Bindings</a> [![Downloads](https://static.pepy.tech/badge/gpt4all/week)](https://pepy.tech/project/gpt4all)
* <a href="https://github.com/nomic-ai/gpt4all/tree/main/gpt4all-bindings/typescript">:computer: Official Typescript Bindings</a>
* <a href="https://github.com/nomic-ai/gpt4all/tree/main/gpt4all-bindings/golang">:computer: Official GoLang Bindings</a>
* <a href="https://github.com/nomic-ai/gpt4all/tree/main/gpt4all-bindings/csharp">:computer: Official C# Bindings</a>
* <a href="https://github.com/nomic-ai/gpt4all/tree/main/gpt4all-bindings/java">:computer: Official Java Bindings</a>

# Python GPT4All
 (https://gpt4all.io/index.html) is an open-source project containing a number of pre-trained Large Language Models (LLMs) that you can use to run locally using consumer grade CPUs. GPT4All contains a number of models that ranges from 3GB to 8GB. What’s more exciting? It is free!

While the performance of GPT4All may not be on par with the current ChatGPT, with contributions from the open source community it has significant potentials for further development and enhancements. It may eventually be able to compete on the same level with commercial models like ChatGPT from OpenAI.

#### zjc local info 
- **venv:** C:\Users\zjc10\Desktop\Projects\envs\gpt_all\Scripts\activate.ps1
- **cmake local:** C:\Program Files\CMake\
- **mingw64:** c:\msys64\mingw64\bin
- **project folder:** C:\Users\zjc10\Desktop\Projects\code\gpt4_all

# Installation Instructions
This package contains a set of Python bindings around the `llmodel` C-API.
- Package on PyPI: https://pypi.org/project/gpt4all/
- Documentation: https://docs.gpt4all.io/gpt4all_python.html

## Pre-build Requirments 

#### 0. Install MinGW64 
- download exe to install mingw64
    ```powershell
    wget https://github.com/msys2/msys2-installer/releases/download/2023-05-26/msys2-x86_64-20230526.exe
    ```
- run installer and save MinGW64 to below default location (c:\msys64)
    ```terminal 
    c:\msys64
    ```
- When complete, ensure the Run MSYS2 now box is checked and select Finish. This will open a MSYS2 terminal window for you.

    - In this terminal, install the MinGW-w64 toolchain by running the following command and enter Y when prompted to proceed:
        ```powershell
        pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
        ```

- Add the path of your MinGW-w64 bin folder to the Windows PATH environment variable by following the below steps (https://code.visualstudio.com/docs/cpp/config-mingw)
    1. In the Windows search bar, type Settings to open your Windows Settings.
    2. Search for Edit environment variables for your account.
    3. In your User variables, select the Path variable and then select Edit.
    4. Select New and add the MinGW-w64 destination folder you recorded during the installation process to the list. If you used the default settings above, then this will be the path: C:\msys64\ucrt64\bin.
    5. Select OK to save the updated PATH. You will need to reopen any console windows for the new PATH location to be available

- verify updated path variable correctly retains references to mingw utils
    ```powershell
    gcc --version
    g++ --version
    gdb --version
    ```

#### 1. Install cmake (https://github.com/Kitware/CMake/releases/download/v3.27.4/cmake-3.27.4-windows-x86_64.msi)
- run the msi installer 
- select 'add cmake to the system path for ALL users'
- install CMake to: C:\Program Files\CMake\
- restart terminal and test path variable assignment ```>cmake```


## Local Build Instructions

**NOTE**: If you are doing this on a Windows machine, you must build the GPT4All backend using [MinGW64](https://www.mingw-w64.org/) compiler.

### non windows install 
```
pip install gpt4all
```
### windows Installation



#### 1. Setup `llmodel` (navigate to folder you want to save project at)

```
git clone --recurse-submodules git@github.com:nomic-ai/gpt4all.git
cd gpt4all/gpt4all-backend/
mkdir build
cd build
cmake ..
cmake --build . --parallel  # optionally append: --config Release
```
**WARNING**: Confirm that `libllmodel.*` exists in `gpt4all-backend/build` before proceeding

#### 2. Setup Python package

```
cd ../../gpt4all-bindings/python
pip3 install -e .
```

## Usage

Test it out! In a Python script or console:

```python
from gpt4all import GPT4All
model = GPT4All("orca-mini-3b.ggmlv3.q4_0.bin")
output = model.generate("The capital of France is ", max_tokens=3)
print(output)
```


GPU Usage
```python
from gpt4all import GPT4All
model = GPT4All("orca-mini-3b.ggmlv3.q4_0.bin", device='gpu') # device='amd', device='intel'
output = model.generate("The capital of France is ", max_tokens=3)
print(output)
```

## Troubleshooting a Local Build
- If you're on Windows and have compiled with a MinGW toolchain, you might run into an error like:
  ```
  FileNotFoundError: Could not find module '<...>\gpt4all-bindings\python\gpt4all\llmodel_DO_NOT_MODIFY\build\libllmodel.dll'
  (or one of its dependencies). Try using the full path with constructor syntax.
  ```
  The key phrase in this case is _"or one of its dependencies"_. The Python interpreter you're using
  probably doesn't see the MinGW runtime dependencies. At the moment, the following three are required:
  `libgcc_s_seh-1.dll`, `libstdc++-6.dll` and `libwinpthread-1.dll`. You should copy them from MinGW
  into a folder where Python will see them, preferably next to `libllmodel.dll`.

- Note regarding the Microsoft toolchain: Compiling with MSVC is possible, but not the official way to
  go about it at the moment. MSVC doesn't produce DLLs with a `lib` prefix, which the bindings expect.
  You'd have to amend that yourself.
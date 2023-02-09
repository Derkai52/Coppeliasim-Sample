# Simer

Tethered coppeliasim (using coppeliasim as a remote controlled multi-body simulator) in Python.

Python 绑定调用 (`sim.py` and `simConst.py`) 和驱动程序库 (`remoteApi.dll`, `remoteApi.dylib`, and `remoteApi.so`) 从 Coppeliasim 安装目录复制到你需要的项目目录中去

这里提供了Coppeliasim V4.3版本的示例,注意版本以实际为准

Thanks to Florian Golemo (https://github.com/fgolemo/vrepper) for help on the Linux side :)

## Usage

Add the path to your Coppeliasim installation to your `PATH`:

- (Windows) might be something like `C:/Program Files/Coppeliasim/Coppeliasim_PRO_EDU/`

  ```bash
  $ set PATH=%PATH%;C:/Program Files/Coppeliasim/Coppeliasim_PRO_EDU/
  ```

- (Mac OS X) might be something like `/Users/USERNAME/Coppeliasim_PRO_EDU/Coppeliasim.app/Contents/MacOS/`

  ```bash
  $ export PATH=$PATH:"/Users/USERNAME/Coppeliasim_PRO_EDU/vrep.app/Contents/MacOS/"
  ```

- (Linux) might be something like `/home/USERNAME/tools/Coppeliasim_PRO_EDU_V3_4_0_Linux`

  ```bash
  $ export PATH="/home/USERNAME/tools/Coppeliasim_PRO_EDU_V3_4_0_Linux":$PATH
  ```

Then run the following:

```bash
$ git clone https://gitee.com/Derkai52/simer_python.git
$ cd sim_python/sample
$ pip install -e . #(install the Simer package in edit mode)
$ python3 simpleTest.py #(run the example)
```

The last command will start Coppeliasim in headless mode (no GUI) and run a simple simulation step-by-step. Then it will shut itself down and exit.

## Why should you use Coppeliasim

- build your model with its GUI tools
- simulate your model with whatever programming language you like

## Why should you use Simer

If you are looking for:

- remote controlled simulation
- low overhead communication
- ability to start/stop simulation repeatedly to perform all kinds of experiment

Then vrepper has already paved the way for you. You should at least take a look at vrepper's source code.

## Known Issues

- On Linux after the end of the script the Coppeliasim process isn't killed properly. Workaround: run "killall vrep" manually after the script finishes.

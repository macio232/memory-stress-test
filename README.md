# MEMORY STRESS TEST

## Description
A Python script to reserve, simulate and stress system memory resources on Linux machines using Linux Kernel cgroups: 
```
https://en.wikipedia.org/wiki/Cgroups
http://man7.org/linux/man-pages/man7/cgroups.7.html
```
It uses a convenience python module called cgroups to simplify the operations of 
having to walk through and manipulate the /proc directory files directly.

It prints memory stats and profiling with psutils and memory_profilers python packages.

Last but not least simulates memory allocation through a dummy buffer implemented as a python list.

## Requirements
Linux and basic Python installation with included pip for install required modules.

it works in local and virtual environments, tested over Python 2.7 and Python 3.6 branches.

## Installation
Steps as usual:
```
git clone this repository
pip install -r requirements.txt
```

**Root and non-root usage**  ( from cgroups package README.md ):

To use cgroups the current user has to have root privileges OR existing cgroups sub-directories.

In order to create those cgroups sub-directories you use the user_cgroups command as root.
```
sudo user_cgroups USER
```
N.B.: This will only give the user permissions to manage cgroups in his or her own sub-directories and process. It will not give the user permissions on other cgroups, process, or system commands.

N.B.: You only need to execute this script once.

### Usage
```
python ./memory-test.py -m [% of the reserved memory to be consumed ]
```

### Useful references
```
CGROUPS Python Module
https://github.com/francisbouvier/cgroups>

CGROUPS-UTILS Python Module and Library
https://github.com/peo3/cgroup-utils

PSUTILS
https://psutil.readthedocs.io/en/latest/

MEMORY-PROFILER
https://pypi.org/project/memory-profiler/
```

### To do's
- Research Python types, objects and runtime sizes to a more accurate simulation on the amount of memory simulated.

- PSUtils looks like the go to Python module for OS resources statistics. Do more test and understant where the measurements come from, and the measures align with other tools like top or htop.

- More readings on cgroups API to understand the correlation with the Linux OS memory management sub system for better fine tuning and granularity of the simulation.

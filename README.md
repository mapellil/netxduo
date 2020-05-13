# Azure RTOS NetxDuo

This advanced, industrial-grade TCP/IP network stack is designed specifically for deeply embedded real-time and IoT applications. Azure RTOS NetX Duo is a dual IPv4 and IPv6 network stack, while Azure RTOS NetX is the original IPv4 network stack, essentially a subset of Azure RTOS NetX Duo.

## Documentation

Documentation for this library can be found here: http://docs.microsoft.com/azure/rtos/netxduo

# Building and using the library

## Prerequisites

Install the following tools:

* [CMake](https://cmake.org/download/) version 3.0 or later
* [GCC compilers for arm-none-eabi](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)
* [Ninja](https://ninja-build.org/)

## Cloning the repo

```bash
$ git clone https://github.com/azure-rtos/netxduo.git
```

## Building the threadx static library

Each component of Azure RTOS comes with a composible CMake-based build system that supports many different MCUs and host systems. Integrating any of these components into your device app code is as simple as adding a git submodule and then including it in your build using the CMake command `add_subdirectory()`.

While the typical usage pattern is to include threadx into your device code source tree to be built & linked with your code, you can compile threadx as a standalone static library to confirm your build is set up correctly.

```bash
$ cmake -Bbuild -DCMAKE_TOOLCHAIN_FILE=cmake/cortex_m4.cmake -GNinja .

$ cmake --build ./build
```

# Repository Structure and Usage

## Branches & Releases

The master branch has the most recent code with all new features and bug fixes. It does not represent the latest General Availability (GA) release of the library.

## Releases

Each official release (preview or GA) will be tagged to mark the commit and push it into the Github releases tab, e.g. `v6.0-rel`.

## Directory layout

```
- cmake
- common
  - inc
  - src
- crypto_libraries
  - inc
  - src
- nx_secure
  - inc
  - src
- ports
  - cortex_m0/gnu
    - inc
    - src
  - cortex_m3/gnu
    - inc
    - src
  - cortex_m4/gnu
    - inc
    - src
  - cortex_m7/gnu
    - inc
    - src
- protocol_handlers
  - auto_ip, BSD, dhcp, dns, ftp, http, mdns, mqtt, nat, pop3, ppp, pppoe, smtp, sntp, telnet, tftp, web
- samples
```

# Contribution, feedback and issues

If you encounter any bugs, have suggestions for new features or if you would like to become an active contributor to this project please follow the instructions provided in the contribution guideline for the corresponding repo.

For general support, please post a question to [Stack Overflow](http://stackoverflow.com/questions/tagged/azure-rtos+threadx) using the `threadx` and `azure-rtos` tags.
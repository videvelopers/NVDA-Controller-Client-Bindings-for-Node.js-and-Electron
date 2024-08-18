# NVDA Controller Client Bindings for Node.js and Electron

This repository provides Node.js and Electron bindings for the NVDA Controller Client, enabling developers to interact with the NVDA screen reader directly from their applications.

## What is NVDA?

[NonVisual Desktop Access (NVDA)](https://www.nvaccess.org/) is a free and open-source screen reader designed for Windows. It allows blind and visually impaired users to interact with the Windows operating system and many third-party applications through auditory feedback.

## What is NVDA Controller Client?

The NVDA Controller Client is a library that provides a set of functions for communicating with NVDA. Through this library, external applications can send commands to NVDA to speak text, control its behavior, and query its status. Traditionally, this library is used in C++ applications, but with these bindings, you can use it in Node.js and Electron environments.

## What is node-gyp?

[node-gyp](https://github.com/nodejs/node-gyp) is a tool used for compiling native addon modules for Node.js. It's a key part of the process when working with C++ code in Node.js, especially when creating bindings for external libraries like the NVDA Controller Client.

## Features

- **Speak Text:** Send text to NVDA for speech output.
- **Control NVDA:** Perform various actions like stopping speech, querying NVDA's state, etc.
- **Node.js and Electron Support:** Use the NVDA Controller Client in both Node.js server-side applications and Electron-based desktop applications.

## Prerequisites

Ensure you have the following installed on your system:

- **Node.js:** Version 10.x or higher.
- **Python:** Version 2.7.x or 3.x (required by `node-gyp`).
- **Build Tools:**
  - **Windows:** Visual Studio with C++ components.
  - **macOS:** Xcode Command Line Tools.
  - **Linux:** GCC and make.
- **node-gyp:** Can be installed globally using the following command:

  ``` bash
  npm install -g node-gyp
```
## Installation
1. 
Clone the repository to your local machine:
``` bash
git clone https://github.com/yourusername/nvda-controller-client-node.git
cd nvda-controller-client-node
```
2. 
Install the necessary Node.js dependencies:
``` bash
npm install
```
3. 
Use `node-gyp` to configure and build the native bindings:
``` bash
node-gyp configure
node-gyp build
```
This will compile the C++ code and generate the necessary bindings for Node.js.
### Configuring for Electron
When using Electron, the version of Node.js embedded in Electron might differ from the system-installed Node.js. To ensure compatibility, follow these steps:
1. 
If not already installed, add Electron as a development dependency:
``` bash
npm install --save-dev electron
```
2. 
Use `electron-rebuild` to rebuild the native module for the Electron environment:
``` bash
npx electron-rebuild
```
This command will recompile the bindings to be compatible with the specific version of Node.js used by Electron.
### Compiling for Different Environments
For Node.js:
If you are building the module for a Node.js environment, use:
``` bash
node-gyp rebuild
```
For Electron:
To rebuild for Electron, use:
``` bash
npx electron-rebuild
```
This ensures that the native module is compatible with the target environment, whether it’s Node.js or Electron.
## Troubleshooting
### Common Issues
- Node-gyp Errors: Ensure that all prerequisites (Python, C++ build tools) are correctly installed and configured. Double-check the version compatibility between Node.js, Electron, and `node-gyp`.
- Rebuild Needed: If you encounter issues after updating Node.js, Electron, or making changes to the source code, try rebuilding the module.
### Rebuilding the Module
To rebuild the module, simply run:
``` bash
node-gyp rebuild
```
For Electron, use:
``` bash
npx electron-rebuild
```
## Contributing
Contributions to this project are welcome! If you have a feature request, find a bug, or want to improve the documentation, please open an issue or submit a pull request.
 ##License
This project is licensed under the MIT License. See the LICENSE file for more details.
## Contact
For any questions or support, please open an issue in this repository.

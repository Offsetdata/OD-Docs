# Installation

## Offsetdata NPM Installation Guide

### Introduction

This document provides step-by-step instructions on how to install the Offsetdata package via the NPM (Node Package Manager) for seamless integration with your project. The Offsetdata NPM package enables you to securely submit and store your data on the blockchain using Offsetdata's services.

### Prerequisites

Before proceeding with the installation, ensure that you have the following prerequisites:

1. Node.js: Offsetdata requires Node.js to be installed on your system. You can download and install Node.js from the official website: [https://nodejs.org](https://nodejs.org/).
2.  NPM: NPM is bundled with Node.js, so ensure that you have NPM installed. You can verify this by running the following command in your terminal or command prompt:

    ```css
    npm --version
    ```

    If NPM is installed, it will display the version number. If it's not installed, please refer to the Node.js installation instructions.

### Installation Steps

To install the Offsetdata package and integrate it into your project, follow these steps:

1. Open your terminal or command prompt.
2. Navigate to your project directory or the desired location where you want to install the Offsetdata package.
3.  Run the following command to install the Offsetdata package:

    ```
    npm install offsetdata
    ```

    This command will fetch the package from the official NPM registry and install it locally within your project.
4.  Once the installation is complete, you can import and use the Offsetdata package in your project. To do this, include the following line at the top of your JavaScript file:

    {% code fullWidth="true" %}
    ```javascript
    const offsetdata = require('offsetdata');
    const od = new offsetdata("your-api-key");


    //Example to call API Version
    od.version(['status']).then((object) => {
            setService(object.status);
          }).catch((error) => {
          console.error(error);
      });


    ```
    {% endcode %}

This line imports the Offsetdata package, making its functionalities available within your project. 5. You can now use the Offsetdata package in your code to submit and store data securely on the blockchain using Offsetdata's services. Refer to the Offsetdata documentation or the package's API reference for information on how to utilize its features effectively.

### Additional Configuration

Depending on your project requirements, you may need to configure the Offsetdata package with your specific credentials or settings. Consult the Offsetdata documentation or the package's API reference for details on how to set up additional configuration options.

### Congratulations!

You have successfully installed the Offsetdata NPM package, allowing you to securely submit and store your data on the blockchain using Offsetdata's services. Ensure that you refer to the Offsetdata documentation for guidance on how to utilize the package's functionalities effectively and integrate them into your project seamlessly.

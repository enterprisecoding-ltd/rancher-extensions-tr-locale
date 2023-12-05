# 🇹🇷 Turkish Localization Extension for Rancher Manager

## Overview

This extension, developed by [Enterprisecoding](https://enterprisecoding.com), offers a comprehensive Turkish localization for the Rancher Manager, enhancing accessibility and usability for Turkish-speaking users. Our team at Enterprisecoding is committed to providing quality software solutions, and this extension is a testament to our dedication to meeting the diverse needs of our user base.

## Features

* **Full Turkish Translation**: Complete translation of all Rancher Manager elements, including menus, dialogs, and tooltips, into Turkish.

* **Easy Integration**: Designed for straightforward installation, ensuring compatibility with the latest version of the Rancher Manager.

* **Enhanced User Experience**: Tailored specifically to improve the Rancher Manager experience for Turkish speakers.

## Installation

To use these extension in Rancher Manager, add this repository as a Helm Repository - to do this:

- Go to the local cluster, to `Apps` and `Repositories`
- Click `Create` and enter a name, e.g. `enterprisecoding-tr-locale`
- Choose Target `Git repository containing Helm chart or cluster template definitions`
- Enter `https://github.com/enterprisecoding-ltd/rancher-extensions-tr-locale.git` for the `Git Repo URL`
- Enter `main` for the Git Branch
- Click `Create`

## Usage

Select the Turkish language option in the Rancher Manager settings post-installation to switch the interface to the Turkish localization.


## Building and running locally

You can build and run the extensions locally, to do so follow the steps given below.

### Prerequisites

#### Node.js
Node 16 (later versions are currently not supported)

If you already have Node.js installed with different version, it is better to use nvm.

```bash
# Install Node.js v16.20.2 (LTS)
nvm install 16.20.2

# Use Node.js v16.20.2 (LTS)
nvm use 16.20.2
```

#### Yarn
```bash
# Install Yarn
npm install --global yarn
```

#### Rancher

A Running Rancher instance is a must. You can use your existing installation or run a single docker container.

In order to run latest single docker container Rancher installation you can use the following command;

```bash
docker run -d --restart=unless-stopped -p 80:80 -p 443:443 --privileged -e CATTLE_BOOTSTRAP_PASSWORD=YOUR_PASSWORD_HERE rancher/rancher
```

You can also use specific version just in case;

```bash
docker run -d --restart=unless-stopped -p 80:80 -p 443:443 --privileged -e CATTLE_BOOTSTRAP_PASSWORD=YOUR_PASSWORD_HERE rancher/rancher:v2.6-head
```

In both cases you should use https://localhost as API environment variable value while running for development.

You can also consider to use [k3d](https://k3d.io/) for immediately installing a Kubernetes cluster in a Docker container and interact with it with kubectl for development and testing purposes.

#### Visual Studio Code (Recommended)

A recent version of Visual Studio Code is recommend for development.

It is also recommended to use following VS Code extensions;

* [vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)
* [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
* [Turkish - Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker-turkish)

### Running for Development

This is what you probably want to get started.

```bash
# Install dependencies
yarn install

# For development, serve with hot reload at https://localhost:8005
# using the endpoint for your Rancher API
API=https://your-rancher yarn dev
# or put the variable into a .env file
# Goto https://localhost:8005
```

### Updating @shell package
This is about updating the @shell package which is the base from rancher/dashboard

```bash
# Update
yarn create @rancher/update
```

### Building the Extension

To build the extension so you can use it independently, run:

```bash
yarn build-pkg tr-locale
```

### Test built extension by doing a Developer load

serve the built package locally by running the following:

```bash
yarn serve-pkgs
```

To enable Developer load in the UI, you should go to the user avatar in the top-right and go to `Preferences`. Under `Advanced Features`, check the `Enable Extension developer features` checkbox.
Bring in the slide-in menu (click on the hamburger menu in the top-left) and click on `Extensions`. Go to the three dot menu and select `Developer load` - you'll get a dialog allowing you to load the extension into the UI. In the top input box `Extension URL`, enter:

    http://127.0.0.1:4500/tr-locale-0.1.0/tr-locale-0.1.0.umd.min.js

Press `Load` and the extension will be loaded.


### Running the Publish Script

Bump the app version on `package.json` file, then run:

```bash
yarn publish-pkgs -s <YOUR_ORGANIZATION>/rancher-extensions-tr-locale -b "<YOUR_BRANCH>"
```

Example:

```bash
yarn publish-pkgs -s enterprisecoding-ltd/rancher-extensions-tr-locale -b "main"
```

After running the script, push newly created/updated files into a your Github repository

```bash
git add .
git commit -m 'Adding extension charts'
git push origin main
```

## Contributing

Contributions to refine this extension are welcome. Please submit pull requests or report issues on our [GitHub repository](https://github.com/enterprisecoding-ltd/rancher-extensions-tr-locale).

## Support

For any issues or suggestions, kindly open an issue on our GitHub repository or contact Enterprisecoding's support team at info@enterprisecoding.com.

## License

This extension is distributed under the Apache license. Refer to the [LICENSE](LICENSE) file in the repository for more details.
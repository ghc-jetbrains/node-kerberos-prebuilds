# node-kerberos-prebuilds
To build node addons for different platforms for kerberos

## Overview

This repository provides prebuilt binaries for the [kerberos](https://github.com/mongodb-js/kerberos) Node.js package, specifically for platforms that may not have readily available prebuilds.

## Usage

### Building Kerberos Prebuilds

This repository includes a GitHub Action workflow to build kerberos prebuilds on Windows ARM64 machines.

To trigger a build:

1. Go to the "Actions" tab in this repository
2. Select "Build Kerberos Prebuilds" workflow
3. Click "Run workflow"
4. Enter the desired parameters:
   - **Kerberos version**: The version of kerberos to build (e.g., `2.2.0`)
   - **Node.js version**: The Node.js version to use (must be >= 22, e.g., `22`)
5. Click "Run workflow"

The workflow will:
- Install the specified kerberos version using npm
- Extract the `kerberos.node` native addon from node_modules
- Create a GitHub release with the format: `v{version}-win-arm64-node{node_version}`
- Upload the prebuilt binary to the release

### Using Prebuilt Binaries

After the workflow completes, you can download the prebuilt binary from the Releases page and use it in your project to avoid compilation on target machines.

## Requirements

- Node.js >= 22
- Windows ARM64 self-hosted runner (GitHub-hosted runners do not currently support Windows ARM64)
  - To set up a self-hosted runner, see [GitHub's documentation](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/adding-self-hosted-runners)
  - The runner should be tagged with: `self-hosted`, `windows`, `ARM64`

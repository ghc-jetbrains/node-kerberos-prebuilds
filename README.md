# node-kerberos-prebuilds

Prebuilt binaries for the [kerberos](https://github.com/mongodb-js/kerberos) Node.js package on Windows ARM64.

## Building Prebuilds

This repository provides a GitHub Actions workflow to build kerberos prebuilds on Windows ARM64.

### How to Build

1. Go to the **Actions** tab
2. Select **Build Kerberos Prebuilds** workflow
3. Click **Run workflow**
4. Enter the parameters:
   - **Kerberos version** (e.g., `2.2.0`)
   - **Node.js version** (must be >= 22, e.g., `22`)
5. Click **Run workflow**

### What Happens

The workflow will:
- Install the specified kerberos version via npm
- Extract the `kerberos.node` native addon
- Create a GitHub release named `v{version}` (e.g., `v2.2.0`)
- Upload the prebuilt binary as `kerberos-v{version}-win32-arm64.node`

### Example

Running the workflow with kerberos version `2.2.0` and Node.js version `22` creates:
- **Release**: `v2.2.0`
- **Tag**: `v2.2.0-win-arm64-node22`
- **Asset**: `kerberos-v2.2.0-win32-arm64.node`

## Using Prebuilt Binaries

Download the prebuilt binary from the [Releases](../../releases) page and place it in your project to avoid compilation.

## Requirements

- Node.js >= 22
- GitHub-hosted `windows-11-arm` runner (available for public repositories)

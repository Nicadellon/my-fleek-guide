# Fleek Node Setup Guide

This guide will walk you through the process of setting up a Fleek node using the Fleek CLI.

## Prerequisites

**Before you begin, make sure you have the following:**

Operating System: Ubuntu 20.04 or later.

System Requirements: At least 4GB of RAM and 20GB of disk space.

User Permissions: Access to a terminal with sudo privileges.

Dependencies: Docker and Git should be installed.

## Step 1: Install Docker

If Docker is not installed on your machine, you can install it using the following commands:

```
sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker
```

Verify the installation:

```
docker --version
```

## Step 2: Install Fleek CLI

To install the Fleek CLI, you'll first need to download the binary from the official Fleek repository:

```
curl -L https://github.com/FleekHQ/fleek-cli/releases/download/v0.1.0/fleek-cli-linux-x64 -o fleek
chmod +x fleek
sudo mv fleek /usr/local/bin/
```

Verify the installation:

```
fleek --version
```

## Step 3: Initialize Your Fleek Node

With the CLI installed, you can now initialize your Fleek node. The initialization process will set up the necessary configuration files and directories.

```
fleek init --moniker="Nicadellon"
```

In this command, --moniker="Nicadellon" sets the name of your node.

## Step 4: Configure Your Node

After initialization, you may want to review and customize the configuration files. The main configuration file is located at ~/.fleek/config/config.toml.

```
nano ~/.fleek/config/config.toml
```

Here, you can modify various parameters like node_id, chain_id, and more. Ensure that your moniker is set to "Nicadellon".

## Step 5: Start Your Fleek Node

Once configured, you can start your node with the following command:

```
fleek start
```

This command will start your Fleek node and begin participating in the network.

## Step 6: Monitor Your Node

To check the status of your node, use:

```
fleek status
```

This will show information about your node's status, including its sync status, network peers, and block height.

## Step 7: Logs and Troubleshooting

If you encounter any issues, you can view the logs to diagnose problems:

```
fleek logs
```

This command will display the most recent logs from your Fleek node, which can be useful for troubleshooting.

## Step 8: Securing Your Node

To ensure your node is secure, consider the following:

Firewall: Use ufw to allow only necessary ports.

Auto-Restart: Enable Docker auto-restart for your Fleek container.

```
sudo ufw allow 26656/tcp
sudo ufw enable
```

## Step 9: Participating in the Network

Once your node is running, it will start syncing with the Fleek network. You can view the sync progress with:

```
fleek sync-status
```

Your node's moniker, "Nicadellon", will be visible in the network's validator or peer lists once fully synced.

## Step 10: Update and Maintain Your Node

To keep your Fleek node up to date, regularly check for updates to the Fleek CLI and apply them as necessary.

```
fleek update
```

This will check for any updates to the CLI and apply them if available.

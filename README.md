# Evernode setup for Hosts
[Evernode](https://evernode.wordpress.com/) enables Hot Pocket smart contracts to be hosted on a global network of decentralized hosts through [XRP Ledger](https://xrpl.org/).

  - Anyone can become an **Evernode host** by installing the Evernode setup on their compatible Linux server.
  - Hosts register on the **Evernode registry**, a well-known XRPL account published by Evernode foundation.
  - Hosts lease smart contract hosting to **Evernode tenants** in exchange for **Evers (EVR)**.

_All of the above are automated by **Sashimono**, Evernode host management software which gets installed when you run the [Evernode installer](#installation)._

# Evernode beta
We are inviting interested enthusiasts to register as an Evernode host. As an Evernode beta host, your Linux server will be registered on the XRPL NFT Devnet. During the installation, you can choose how much system resources you wish to allocate for smart contract hosting. After everything is setup, your server will start leasing hosting space to Evernode tenants.

> **Devnet warning:** Since Evernode beta uses **XRPL NFT Devnet**, Evernode registry and your registration may get wiped out without prior notice. In such cases we will have to spin up a new registry before you can reinstall Evernode and become part of our beta network again.

## Evernode beta licence
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to use the software for, or in connection, with the Evernode network for the duration of the beta test.

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS IN BETA AND PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Airdrops
Evernode Foundation may, in its absolute discretion, airdrop a portion of its Evers to people who participate in the beta. But the details of any such airdrop are not confirmed. The Foundation reserve the right to, at anytime and without notice, amend the details of any airdrop, include or exclude people or classes of people, or abandon the airdrop entirely. You should participate in the beta because you want to help the Evernode Network succeed, not because you want an airdrop of Evers.

# Installation

## System requirements
To reduce testing and development overhead, during the beta, we require your server to meet following requirements:
  - Operating system: **Ubuntu 20.04** (64 bit)
  - RAM: **2 GB** minimum
  - Swap: **2 GB** minimum
  - Disk space: **4 GB** minimum free disk space for `/home`

## Important tips
  - You can use a phyisical or virtual (VPS) Linux server as your Evernode host. **[WSL](https://docs.microsoft.com/en-us/windows/wsl/about) is not supported**.
  - It's recommended that you use a server which DOES NOT contain other workloads important to you. It's best if you can provision a fresh VPS from a cloud provider which you can dedicate for Evernode beta and dispose of easily when no longer required.
  - Based on the smart contracts that are hosted on your server, you server will accumulate network usage while its operating. During the early days of the beta, this will be minimal (eg. less than 50 GB per month). Even as the beta network grows, we predict that this will be well within the basic data transfer allowances of most cloud VPS providers (eg. 500 - 1000 GB per month). However, we recommend you to monitor the network usage or set upper limits to avoid unpredictable costs.

Run the following command to install Evernode beta on your Linux server. You need root (sudo) access for this.

```
curl -fsSL https://stevernode.blob.core.windows.net/evernode-beta/setup.sh | cat | sudo bash -s install
```

## Maintaining your host
Once Evernode is installed, you don't need to do anything else. Evernode will automatically use your server to fullfil leasing reqeusts from Evernode tenants. You will earn Evers (EVR) as tenants lease hosting.

For monitoring and maintenance, you can use following commands:
  - `evernode status` - Display your current registration status and Ever balance in your account.
  - `evernode list` - Display a list of smart contracts running on your host.
  - `evernode update` - Apply Evernode beta software updates.
  - `sashi` - Sashimono CLI for advanced operations and monitoring. Use `sashi -h` for help.

Note: `sudo` access is required for `status`, `update` and `uninstall` commands.

At any time, you can uninstall and deregister from Evernode with `evernode uninstall`.

## Reporting issues
Please report any issues and error logs [here](https://github.com/HotPocketDev/evernode-host/issues).
## Prerequisites
- **Juju CLI** - Necessary for all deployments
- **MicroK8s** - Necessary for local deployments

> ⚠️ **Windows and MacOS**
>
> The commands below are for an Ubuntu 20.04 machine. You can find instructions for Windows and MacOS in the next session. 

<!---
_asciinema_iframe
<iframe src="https://asciinema.org/a/476954/iframe" width=99% height=600px" scrolling='no' frameborder="0"></iframe>
--->
[![asciicast](https://asciinema.org/a/476954.svg)](https://asciinema.org/a/476954)
                                                                                                          
### References and other operating systems: 
#### Installing Juju
[Project's page](https://juju.is/docs/olm/installing-juju)


<details>
  <summary>Windows</summary>
  
Visit the project’s [downloads](https://launchpad.net/juju/+download) page and select the signed installer for the Juju version you wish to install.
</details>

<details>
  <summary>MacOS</summary>
  
The Juju client is available on [Homebrew](https://brew.sh/) and can be installed as follows:
```
brew install juju
```
</details>

#### Installing MicroK8s
[Project's page](https://microk8s.io/)

<details>
  <summary>Windows</summary>
  
1. **Download the MicroK8s Installer**
[Download the latest installer here](https://microk8s.io/microk8s-installer.exe)

2. **Run the installer**

![alt text](https://aws1.discourse-cdn.com/business6/uploads/kubernetes/original/2X/c/cc39a370d6a9f62bbcfa0b84ba8356da84a4c8c1.png)

The installer checks if Hyper-V is available and switched on. If you don’t have Hyper-v (e.g. on Windows 10 Home edition) it is possible to use VirtualBox as an alternative.

3. **Configure MicroK8s**

![image](https://aws1.discourse-cdn.com/business6/uploads/kubernetes/original/2X/9/98605c2d901d9105441eb3480061b0bb97f2d6e2.png)
   
You can now configure MicroK8s - the minimum recommendations are already provided. For information on changing the ‘Snap Track’, see [this page](https://microk8s.io/docs/setting-snap-channel).

</details>

<details>
  <summary>MacOS</summary>
  
The installer for MicroK8s uses HomeBrew. If you don’t have the `brew` command you can install it from the [Homebrew website](http://brew.sh/).

1. Download the MicroK8s installer
```
brew install ubuntu/microk8s/microk8s
```

2. Run the installer
```
microk8s install
```
</details>


##### Configuring MicroK8s (all systems)
After installing MicroK8s, you can configure it by running

```
microk8s enable dns storage ingress 
microk8s status --wait-ready
```

> ⚠️ **Wait for the services to be enabled**
>
>  Make sure that `dns`, `ingress` and `storage` are listed as `enabled`. This can take a couple of minutes.

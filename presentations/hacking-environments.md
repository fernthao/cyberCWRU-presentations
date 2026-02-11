## Hacking Environments

### A presentation by cyberCWRU

---

## Why use an environment?

- Isolation is good!
    - Especially if you're analyzing malware or other tools
- You can test vulnerabilites on machines you don't have
    - Active Directory (Windows Server)

---

## Virtual Machines (1/3)

- The are emulated systems
    - Virtualbox, VMware, QEMU
- Depends on use case
    - Virtualbox has Hardware Spoofing capabilities
    - QEMU has GPU-passthrough for more intensive tasks
- For your actual hacking system
    - Use whatever you are comfortable with
    - Kali has a lot of preinstalled tools
    - Proxmox can host a ton of VMs if you like self-hosting
- Theres a bunch of resources for hacking tools:
    - [Awesome Hacking](https://github.com/jekil/awesome-hacking)

---


## Virtual Machines (2/3)

- Snapshots are a rollback feature
- Different network modes for testing
    1. NAT
        - Allows the VM to connect to the internet but not see devices on your real network/ talk to other VMs
        - This is usually good for most use cases
    2. Host-Only
        - The VM can only communicate with the host on an emulated virtual network
        - Useful if you don't want your VM to access the internet (black-box malware analysis)
    3. Bridged
        - Typically never used, simply turns your VM into another network device that can be discovered

---

## Virtual Machines (3/3)

- Be careful!! VM to Host attacks are rare but not impossible!
- Guest Additions are useful!

---

## Docker (1/2)

- Docker is a tool to run containerized applications
- This is similar to VMs, but just for applications
- Good for practicing hacking into vulnerable applications
- Reproducable!!
- Very lightweight, don't have to allocate resources

```bash
docker pull vulnerables/web-dvwa
docker run --rm --interactive --tty -p 8080:80 vulnerables/web-dvwa
```
---


## Docker (2/2)

- Setup is really easy!
    1. Install docker
        - [Install Link](https://medium.com/@abhinsubej/dvwa-installation-using-docker-step-by-step-guide-79d3b31e88b5)
    2. (Optional) Enable rootless docker
        - Add your user to the docker group
    3. Change the data root

```nix
virtualisation.docker.enable = true;
virtualisation.docker.daemon.settings;
virtualisation.docker.daemon.settings = {
    data-root = "~/Projects/docker/";
  };
  virtualisation.docker.rootless = {
    enable = true;
    setSocketVariable = true;
  };
};
```

---

## Thank you!

### Any questions?

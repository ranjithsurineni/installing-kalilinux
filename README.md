# Installing Kali Linux on Windows using Vagrant and VirtualBox

This guide provides step-by-step instructions to install Kali Linux on Windows using **Chocolatey, Git, VirtualBox, and Vagrant**.

## Prerequisites
- Windows operating system
- Administrator privileges
- Internet connection

---

## Step 1: Install Chocolatey
Chocolatey is a package manager for Windows that simplifies software installation.

1. Open **PowerShell as Administrator**.
2. Check the execution policy:
   ```powershell
   Get-ExecutionPolicy
   ```
   - If it returns `Restricted`, change it using:
   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force
   ```
3. Run the following command to install Chocolatey:
   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```
4. Verify installation by checking the version:
   ```powershell
   choco --version
   ```
   Example output:
   ```
   Chocolatey v2.2.2
   ```

---

## Step 2: Install Git
Git is required to manage repositories and access Vagrant configurations.

1. Install Git using Chocolatey:
   ```powershell
   choco install git.install -y
   ```
2. Verify installation:
   ```powershell
   git --version
   ```

---

## Step 3: Install VirtualBox
VirtualBox is required to create and run virtual machines.

1. Install VirtualBox using Chocolatey:
   ```powershell
   choco install virtualbox -y
   ```
2. Verify installation by opening VirtualBox.

---

## Step 4: Enable Required Windows Features
Before proceeding, ensure the following Windows features are enabled:

- **Virtual Machine Platform**
- **Windows Subsystem for Linux**
- **Hyper-V**
- **Windows Hypervisor Platform**

To enable them:
1. Open **Control Panel > Programs > Turn Windows features on or off**.
2. Enable the above-mentioned features.
3. Restart your system if any changes were made.

---

## Step 5: Install Vagrant
Vagrant is used to manage virtual machine environments.

1. Install Vagrant using Chocolatey:
   ```powershell
   choco install vagrant -y
   ```
2. Restart your system after installation.
3. Verify installation:
   ```powershell
   vagrant --version
   ```

---

## Step 6: Set Up Kali Linux in Vagrant

1. Open **Git Bash**.
2. Navigate to the `C:` drive:
   ```bash
   cd /c/
   ```
3. Create a directory for Vagrant and Kali Linux:
   ```bash
   mkdir -p vagrant/kalilinux
   ```
4. Navigate to the Kali Linux directory:
   ```bash
   cd vagrant/kalilinux
   ```
5. Initialize Kali Linux with Vagrant:
   ```bash
   vagrant init kalilinux/rolling
   ```
   This creates a `Vagrantfile` in the directory.
6. Start and provision the Kali Linux virtual machine:
   ```bash
   vagrant up
   ```
   - This will download and set up the Kali Linux virtual machine.
   - The first-time setup may take some time.

---

## Running and Stopping Kali Linux
- **To start Kali Linux**, navigate to the `kalilinux` directory and run:
  ```bash
  vagrant up
  ```
- **To stop Kali Linux**, run:
  ```bash
  vagrant halt
  ```

---

## Uninstalling Components
If you need to remove any component, use the following commands:
- **Uninstall Git**:
  ```powershell
  choco uninstall git.install -y
  ```
- **Uninstall VirtualBox**:
  ```powershell
  choco uninstall virtualbox -y
  ```
- **Uninstall Vagrant**:
  ```powershell
  choco uninstall vagrant -y
  ```
- **Uninstall Chocolatey**:
  ```powershell
  choco uninstall chocolatey -y
  ```

---

## Conclusion
You have successfully installed Kali Linux on Windows using **Vagrant and VirtualBox**. You can now use Kali Linux as a virtual machine for penetration testing, ethical hacking, or general usage.

For any issues, refer to the official documentation:
- [Chocolatey Docs](https://docs.chocolatey.org/)
- [Vagrant Docs](https://developer.hashicorp.com/vagrant/docs)
- [VirtualBox Docs](https://www.virtualbox.org/manual/)

---




### Installing Kalilinux Using Vagrant Tool on Windows Device Screenshot:

![kali-1](https://github.com/ranjithsurineni/installing-kalilinux/assets/118590392/b14115e6-085e-435a-bbc1-35ea462b9c45)
![kali-2](https://github.com/ranjithsurineni/installing-kalilinux/assets/118590392/a74ca932-0bb6-4e13-8e78-5198a260285a)
![kali-3](https://github.com/ranjithsurineni/installing-kalilinux/assets/118590392/508d5503-d778-4081-96af-5f6909767d63)

---

### Author
Ranjith Kumar Surineni 💥

---

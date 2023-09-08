## Installing XPPAUT on Windows using the Ubuntu subsystem (WSL2):

XPPAUT is a powerful tool for simulating and analyzing dynamical systems. In this tutorial, we'll set up XPPAUT on Windows system using Ubuntu (WSL2).

**Prerequisites:**
1. Windows 11 installed with WSL2 enabled.
2. Ubuntu installed as a WSL2 distribution.
3. Basic knowledge of using the command line.

**Steps to Install XPPAUT on Windows 11 Using Ubuntu (WSL2):**

**Step 1: Set Up WSL2 and Ubuntu**
If you haven't already set up WSL2 and installed Ubuntu, follow these steps:

1. Open PowerShell as Administrator and run the following command to enable WSL2:
   ```shell
   wsl --install
   ```

2. Restart your computer when prompted.

3. Install Ubuntu from the Microsoft Store or using the following PowerShell command:
   ```shell
   wsl --install -d Ubuntu
   ```

4. Set up your Ubuntu username and password when prompted.

**Step 2: Update Ubuntu**
Open the Ubuntu terminal (WSL2) and update the package list and upgrade installed packages:
```shell
sudo apt update
sudo apt upgrade
```

**Step 3: Install Required Dependencies**
XPPAUT requires some dependencies to be installed on Ubuntu. Install them using the following command:
```shell
sudo apt install build-essential libx11-dev libxt-dev libxmu-dev libxext-dev
```

**Step 4: Download and Compile XPPAUT**
1. Create a directory to download and compile XPPAUT. For example:
   ```shell
   mkdir ~/xppaut_install
   cd ~/xppaut_install
   ```

2. Download the XPPAUT source code from the official website:
   ```shell
   wget http://www.math.pitt.edu/~bard/xpp/xppaut_latest.tar.gz
   ```

3. Extract the downloaded file:
   ```shell
   tar -xzvf xppaut_latest.tar.gz
   ```

4. Navigate to the XPPAUT source directory:
   ```shell
   cd xppaut
   ```

5. Compile XPPAUT:
   ```shell
   make
   ```

**Step 5: Run XPPAUT**
After compiling, you can run XPPAUT by executing the following command in the same terminal:
```shell
./xppaut
```

XPPAUT's graphical user interface should open, allowing you to create, simulate, and analyze dynamical systems.

**Step 6: Optional - Create a Desktop Shortcut**
To make it easier to launch XPPAUT in the future, you can create a desktop shortcut:

1. Open a text editor in Ubuntu (e.g., Nano):
   ```shell
   nano ~/xppaut_desktop.sh
   ```

2. Add the following lines to the file, adjusting the paths if necessary:
   ```shell
   #!/bin/bash
   cd ~/xppaut_install/xppaut
   ./xppaut
   ```

3. Save the file and exit the text editor.

4. Make the script executable:
   ```shell
   chmod +x ~/xppaut_desktop.sh
   ```

5. Create a desktop shortcut on your Windows system pointing to this script, allowing you to launch XPPAUT with a double-click.

That's it! You've successfully installed XPPAUT on your Windows 11 system using Ubuntu (WSL2). You can now use XPPAUT to explore and analyze dynamical systems.

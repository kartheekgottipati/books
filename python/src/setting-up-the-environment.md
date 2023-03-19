# Setting up the Environment

## Windows

1. Download Python: Go to the [Python download page](https://www.python.org/downloads/) and download the latest version of Python for Windows.

2. Install Python: Run the downloaded installer and follow the instructions to install Python on your system.

3. Set the PATH: During the installation process, make sure to check the box that says "Add Python to PATH". This will ensure that Python is added to your system's PATH environment variable, allowing you to run Python from the command prompt.

## Linux

### Debian-based distributions (e.g. Ubuntu)

1. Check if Python is installed: Open a terminal and type `python3 --version`. If Python is already installed, the version number will be displayed. If not, you can install it using the following command:

   ```bash
   sudo apt-get update
   sudo apt-get install python3
   ```

2. Install pip: Pip is a package manager for Python that allows you to easily install and manage Python packages. To install pip, enter the following command:

   ```bash
   sudo apt-get install python3-pip
   ```

3. Verify installation: You can verify that Python and pip are installed correctly by typing python3 --version and pip3 --version in the terminal.

### CentOS-based distributions (e.g. Red Hat, Fedora)

1. Check if Python is installed: Open a terminal and type `python3 --version`. If Python is already installed, the version number will be displayed. If not, you can install it using the following command:

   ```bash
    sudo yum update
    sudo yum install python3
   ```

2. Install pip: Pip is a package manager for Python that allows you to easily install and manage Python packages. To install pip, enter the following command:

   ```bash
   sudo yum install python3-pip
   ```

3. Verify installation: You can verify that Python and pip are installed correctly by typing `python3 --version` and `pip3 --version` in the terminal.

## MacOS

### Homebrew

1. Install Homebrew: Homebrew is a package manager for MacOS that makes it easy to install and manage software packages. To install Homebrew, open a terminal and enter the following command:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install Python: Once you have Homebrew installed, you can use it to install Python. To install Python 3, enter the following command:

   To install the latest version of Python, you can use the following command:

   ```bash
   brew install python3
   ```

   To install a specific version of Python, you can use the following command:

   ```bash
   brew install python@3.9
   ```

3. Verify installation: You can verify that Python is installed correctly by typing `python3 --version` in the terminal.

## Summary

Once you've installed Python on your system, you can verify that it's working by opening a terminal and typing `python` (or `python3` on Linux and MacOS). This will open the Python interactive interpreter, where you can enter Python code and see the results.

{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "44d1601e",
   "metadata": {},
   "source": [
    "# Process to install anaconda, Intellij, and GitHub Desktop on Chromebook (Debian 10)\n",
    "\n",
    "## Anaconda\n",
    "Go to https://www.anaconda.com/products/individual to download the Anaconda installer for Linux.\n",
    "\n",
    "Then Copy the downloaded files into Linux file, navigate to the target directory (usually it just start in Linux file directory already), then type ./Anaconda..., this will then install Anaconda/Jupyter/Python 3.8 automatically\n",
    "\n",
    "## Intellij\n",
    "\n",
    "### Install Java 17 JDK\n",
    "Reference: https://computingforgeeks.com/install-oracle-java-openjdk-on-debian-linux/\n",
    "\n",
    "sudo apt update\n",
    "sudo apt -y install wget curl\n",
    "\n",
    "wget https://download.oracle.com/java/17/latest/jdk-17_linux-x64_bin.deb\n",
    "\n",
    "sudo apt install ./jdk-17_linux-x64_bin.deb\n",
    "\n",
    "cat <<EOF | sudo tee /etc/profile.d/jdk.sh\n",
    "export JAVA_HOME=/usr/lib/jvm/jdk-17/\n",
    "export PATH=\\$PATH:\\$JAVA_HOME/bin\n",
    "EOF\n",
    "\n",
    "source /etc/profile.d/jdk.sh\n",
    "java -version\n",
    "\n",
    "If this returns without error, then Java 17 JDK has been installed succesfully.\n",
    "\n",
    "### Install Intellij\n",
    "sudo apt update \n",
    "\n",
    "sudo apt install libsquashfuse0 squashfuse fuse \n",
    "sudo apt install snapd\n",
    "\n",
    "sudo snap install intellij-idea-community --classic\n",
    "\n",
    "launch it by navigating to cd /snap/intellij-idea-community/323/bin/ and do ./idea.sh\n",
    "\n",
    "\n",
    "## GitHub Desktop\n",
    "wget -qO - https://packagecloud.io/shiftkey/desktop/gpgkey | sudo apt-key add -\n",
    "\n",
    "sudo sh -c 'echo \"deb [arch=amd64] https://packagecloud.io/shiftkey/desktop/any/ any main\" > /etc/apt/sources.list.d/packagecloud-shiftky-desktop.list'\n",
    "\n",
    "sudo apt-get update\n",
    "\n",
    "sudo apt install github-desktop\n",
    "\n",
    "After succesful install, launch it by typing github-desktop.\n"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.8"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
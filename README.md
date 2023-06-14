# archlinux-playbook
This repository contains a playbook for automating the installation and configuration of Arch Linux using Ansible. It provides a streamlined and reproducible method for setting up a fresh Arch Linux system with commonly used packages and configurations.

For more information about Ansible, please visit the [Ansible website](https://www.ansible.com/).

## Table of Contents
- [What is Ansible](#what-is-ansible)
- [What Can I Do With This](#what-can-i-do-with-this)
- [Requirments](#requirments)
- [Installation](#installation)
- [Using a remote system](#using-a-remote-system)
- [GUI appications](#gui-applications)
- [Packages](#packages)
- [Fonts](#fonts)
- [Customizing](#customizing)
- [Contributing](#contributing)
- [Special thanks](#special-thanks)
- [License](#license)

## What is Ansible?
Ansible is an open-source automation tool that allows you to automate the configuration, management, and deployment of systems. It is designed to be simple, agentless, and powerful, making it popular among system administrators, developers, and DevOps teams.

For more information on Ansible and its capabilities, refer to the official [Ansible documentation](https://docs.ansible.com/).

## What Can I Do With This
By using this playbook, you can achieve the following:

1. **Package Installation:** The playbook allows you to automate the installation of essential packages on your Arch Linux system. These packages typically include core utilities, development tools, system libraries, and common applications.
2. **Consistency and Reproducibility:** By using this playbook, you can ensure that your Arch Linux installations are consistent and reproducible across multiple systems. With the same playbook and configurations, you can easily replicate your desired setup on different machines.
4. **Simplification of Setup:** The playbook simplifies the process of setting up a new Arch Linux system. Instead of manually installing packages and configuring the system, you can rely on the playbook to automate these tasks, saving time and effort.
3. **Multi-Host Support:** The playbook supports multiple hosts, allowing you to set up Arch Linux on multiple systems simultaneously. Whether you have a single machine or a fleet of systems, you can efficiently deploy and manage them using the playbook.
4. **Extend and Customize:** The playbook serves as a foundation that you can extend and customize according to your specific requirements. You can add additional tasks, roles, or configurations to suit your needs, making it a flexible tool for system automation.

## Requirments
Before using this playbook, ensure that you have the following prerequisites:
* A working Arch Linux system to use as the control machine.
* Ansible installed on the control machine. You can install Ansible using the package manager of your distribution.
* A basic understanding of Arch Linux and its package management system.

## Installation
1. Clone or download this repository to your local drive.
2. Then edit the `inventory` file. By default it have `127.0.0.1`.
3. Run the following command inside this directory to install required Ansible roles.
```bash
ansible-galaxy install -r requirements.yml
```
4. Run the following command inside the directory.
```bash
ansible-playbook -i inventory main.yml -K
``` 
5. Enter your account password when prompted for the 'BECOME' password.

## Using a remote system
You can use this playbook to manage other Arch Linux machines as well. The playbook doesn't even need to be run from an Arch Linux machine at all! If you want to manage a remote Arch Linux machine, either another Arch Linux machine on your network or a hosted Arch Linux machine, you just need to make sure you can connect to it with SSH.

1. Start the ssh daemon in which machines you want to run.
2. Then edit the inventory file in this repository and change the line that starts with 127.0.0.1 to:
```
[ip address or hostname]  ansible_user=[ssh username]
```
3. Run the following command inside this directory to install required Ansible roles.
```bash
ansible-galaxy install -r requirements.yml
```
4. Run the following command inside the directory.
```bash
ansible-playbook -i inventory main.yml
``` 
If you need to supply an SSH password (if you don't use SSH keys), make sure to pass the --ask-pass parameter to the ansible-playbook command.

## GUI Applications
* Firefox
* Google Chrome
* MPV - media player
* Spotify (with ad blocker)
* Alacritty
* Geary
* Visual Studio Code
* Obsidian

## Packages
- Python
- Nodejs
- Rust
- Yay 
- Neofetch
- Btop
- Tmux
- Cpupower
- Aria2
- yt-dlp
- pass
- stow
- **And More**

## Fonts
- ttf-ubuntu-font-family
- noto-fonts
- noto-fonts-emoji # for emoji
- ttf-dejavu
- ttf-roboto
- adobe-source-han-sans-otc-fonts

## Customizing
The Arch Linux Playbook provides flexibility in customizing the packages that are installed on your Arch Linux system. You can easily modify the list of packages to include or exclude specific ones according to your requirements.

To customize the packages:
1. Open the`config.yml` file.
2. That contains a list of packages to be installed after essential packages are installed.
3. Add or remove package names from the list based on your needs. You can include additional packages by appending them to the list, or remove packages by deleting their entries.

Please ensure that the package names are valid and correspond to the packages available in the Arch Linux repositories/AUR.

## Contributing
Contributions are welcome! If you have any suggestions, improvements, or bug fixes, feel free to open an issue or submit a pull request.

## Special thanks
A special thanks goes to Jeff Geerling [@geerlingguy](https://github.com/geerlingguy), the author of ["Ansible for DevOps"](https://www.ansiblefordevops.com/) book and creator of informative videos.

## License
This repository is licensed under the MIT License. You are free to modify, distribute, and use the scripts in this repository in accordance with the terms of the license.

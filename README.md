## Steps to bootstrap a new Linux machine

1. Install linux's Command Line Tools, which are prerequisites for Git and pip.

```bash
sudo apt install code
```


2. Clone repo into new hidden directory.

```bash
# Use SSH (if set up)...
git clone git@github.com:Brian-Kariu/Dotfiles.git ~/.dotfiles

# ...or use HTTPS and switch remotes later.
git clone git@github.com:Brian-Kariu/Dotfiles.git ~/.dotfiles
```


3. Create symlinks in the Home directory to the real files in the repo.

```bash
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.bashrc ~/.dotfiles/.bashrc 
ln -s ~/.gitconfig ~/.dotfiles/.gitconfig 
```


4. Install pip, followed by the software listed in the Brewfile.

```bash
# These could also be in an install script.

# Install pip
sudo apt install python3-pip

# Then pass in the Brewfile location...
pip install -r ~/.dotfiles/requirements.txt

# ...or move to the directory first.
cd ~/.dotfiles && pip install -r requirements.txt
```


## TODO List

- Learn how to use [`defaults`](https://macos-defaults.com/#%F0%9F%99%8B-what-s-a-defaults-command) to record and restore System Preferences and other macOS configurations.
- Organize these growing steps into multiple script files.
- Automate symlinking and run script files with a bootstrapping tool like [Dotbot](https://github.com/anishathalye/dotbot).
- Revisit the list in [`.bashrc`](.bashrc) to customize the shell.
- Make a checklist of steps to decommission your computer before wiping your hard drive.
- Create a [bootable USB installer for macOS](https://support.apple.com/en-us/HT201372).
- Integrate other cloud services into your Dotfiles process (Dropbox, Google Drive, etc.).
- Find inspiration and examples in other Dotfiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).

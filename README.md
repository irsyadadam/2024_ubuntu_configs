# 2024_ubuntu_configs

This folder contains all current configs for Ubuntu 22.04 LTS, gnome version 42.09. Currently deployed on irsyad@nvidia_desktop.

Installation contains:

- vim
- terminal
- desktop env setup

#

**Install Kitty**

1. Run the following command: <code> curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin </code>

2. For desktop integration (as kitty can only be opened with the command line), run the following command

```
# Create symbolic links to add kitty and kitten to PATH (assuming ~/.local/bin is in
# your system-wide PATH)
ln -sf ~/.local/kitty.app/bin/kitty ~/.local/kitty.app/bin/kitten ~/.local/bin/
# Place the kitty.desktop file somewhere it can be found by the OS
cp ~/.local/kitty.app/share/applications/kitty.desktop ~/.local/share/applications/
# If you want to open text files and images in kitty via your file manager also add the kitty-open.desktop file
cp ~/.local/kitty.app/share/applications/kitty-open.desktop ~/.local/share/applications/
# Update the paths to the kitty and its icon in the kitty desktop file(s)
sed -i "s|Icon=kitty|Icon=$(readlink -f ~)/.local/kitty.app/share/icons/hicolor/256x256/apps/kitty.png|g" ~/.local/share/applications/kitty*.desktop
sed -i "s|Exec=kitty|Exec=$(readlink -f ~)/.local/kitty.app/bin/kitty|g" ~/.local/share/applications/kitty*.desktop
# Make xdg-terminal-exec (and hence desktop environments that support it use kitty)
echo 'kitty.desktop' > ~/.config/xdg-terminals.list
```

3. Move the kitty folder from this repos to ~/.config/ directory. 


# 


**Vim Customization**

1. Vim version >= 9.0. Install the latest version of vim here: https://www.vim.org/download.php 

2. Install plug.vim in ~/.vim/autoload directory. Instructions found here: https://github.com/junegunn/vim-plug?tab=readme-ov-file 

3. Create a ~/.vim/plugged directory. 

4. Move .vimrc file to home dir ~/.vimrc

5. Reload terminal, and in the .vimrc file, <code> :PlugInstall</code>  to download the plugins.

#

**Install Starship**

1. To install starship, run the following command <code> curl -sS https://starship.rs/install.sh | sh </code>


2. Configure bashrc file to run starship: <code> eval "$(starship init bash)" </code>

3. Place starship.toml to the following directory: ~/.configs/


#

**Install TMUX**

1. <code> sudo apt install tmux </code>

- no configs associated with tmux yet

#

**Install Neofetch**

1. Neofetch installation can be found here: https://github.com/dylanaraps/neofetch/wiki/Installation#universal-install 

2. Place the neofetch folder inside ~/.configs/

3. The neofetch folder images are located in the pictures folder. Neofetch references ~/Pictures/new_term_image.jpg for the background images. The images can be found in the pictures folder. 

#

**Install Ant-Master for desktop**

1. Install ant: https://github.com/EliverLara/Ant

2. Place in the ~/.themes/ folder

3. Copy the contents and also place them in the ~/usr/share/themes folder

4. Open the gnome-tweaks tool (if already installed), and set the "Appications" to Ant-Master

5. Copy the /gtk-4.0/ folder from the /Ant-master into ~/.config/gkt-4.0, so it should look like ~/.config/gtk-4.0/gtk-4.0

6. Make sure that all newer apps (chrome, vscode), follow the gtk format in settings.

#

**Finalizing bash**

1. The bashrc file is in .bashrc




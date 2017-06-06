# this is for the installing the jupyter in linux-mint 18
https://www.continuum.io/downloads#linux
wget https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh
bash Anaconda3-4.4.0-Linux-x86_64.sh

# In order to activate the installation, you should source the ~/.bashrc file:

source ~/.bashrc

# Once you have done that, you can verify your install by making use of the conda command, for example with list:

conda list
# to run Jupyter 

jupyter notebook

# this is to add a desktop app for the jupyter to run it easily 


# go to the desktop app entry to create a new desktop icon 
# file:///usr/share/applications/Jupyter.desktop

[Desktop Entry]
Name=Jupyter
Comment=Jupyter Desktop Shortcut
GenericName=Text Editor
Exec=bash -c "~/anaconda3/bin/jupyter notebook --notebook-dir=~/"
Icon=/home/islam/anaconda3/pkgs/notebook-5.0.0-py36_0/info/icon.png
Path=~/
Terminal=true
Type=Application
StartupNotify=true
Categories=GNOME;GTK;Utility;TextEditor;Development;

[Desktop Entry]
Name=Jupyter
Comment=Jupyter Desktop Shortcut
GenericName=Text Editor
Exec=bash -c "/home/islam/anaconda3/bin/jupyter notebook --notebook-dir=~/"
Icon=/home/islam/anaconda3/pkgs/notebook-5.0.0-py36_0/info/icon.png
Path=/home/islam/
Terminal=true
Type=Application
StartupNotify=true
Categories=GNOME;GTK;Utility;TextEditor;Development;

#Another way is the next which is way more better 
-----
Exec=/home/paul/anaconda3/bin/jupyter notebook --notebook-dir=~/Notebook
As suggested in a comment by PaulDong, but I was having problems trying to add a path to the PYTHONPATH.

Now I am using the following (on Ubuntu 16.04):

I have created a jupyter_.sh (in /home/usr/) file with the following:
-----
#!/bin/bash     

# OPTIONAL - add to PYTHONPATH
export PYTHONPATH="${PYTHONPATH}:/path_to_add/

# start notebook at the desired folder
jupyter notebook --notebook-dir '/path_to_notebooks/'
And I have a Jupyter.desktop file with:

[Desktop Entry]
Version=1
Name=Jupyter
Comment=Open jupyter at different dir
Exec=bash -c "~/jupyter_.sh"
Icon=/home/usr/anaconda3/lib/python3.5/site-packages/anaconda_navigator/static/images/jupyter-icon-1024x1024.png
Terminal=true
Type=Application






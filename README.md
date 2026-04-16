# ASUS KEYBOARD

An app designed to run the LED colors on the keyboard of new Asus laptops such as the TUF Gaming A16. It is a workaround for the color cycles.
PREREQUISITES

Before installing, ensure your system has the following:

asusctl (The underlying driver for Asus hardware)

# QUICK INSTALL

If you want to use the pre-compiled binary, run this command block:

```bash
curl -sL https://github.com/Logawinner/Asus-Keyboard/raw/main/asus-keyboard-dist.tar.gz | tar -xvz && \
sudo mv ./Asus_Keyboard /usr/bin/asus-keyboard && \
sudo chmod +x /usr/bin/asus-keyboard && \
echo -e "[Desktop Entry]\nType=Application\nName=Asus Keyboard\nComment=Stable Asus Aura Management\nExec=/usr/bin/asus-keyboard\nIcon=/home/$USER/.local/share/icons/com.logawinner.aura-keyboard/icon_v1.png\nTerminal=false\nCategories=Settings;HardwareSettings;\nStartupWMClass=com.logawinner.aura-keyboard" > ~/.local/share/applications/asus-keyboard.desktop && \
update-desktop-database ~/.local/share/applications/
```

# MANUAL BUILD

If you prefer to build from source, ensure you have your compiler and GTK3 headers configured:

```bash
# 1. Download and Extract the files
curl -sL https://github.com/Logawinner/Asus-Keyboard/raw/main/asus-keyboard-dist.tar.gz | tar -xvz && \

# 2. Compile fresh from the extracted source
g++ -O3 Asus_Keyboard.cpp -o asus-keyboard $(pkg-config --cflags --libs gtk+-3.0) -lpthread && \

# 3. Move and setup the system environment
sudo mv ./asus-keyboard /usr/bin/asus-keyboard && \
sudo chmod +x /usr/bin/asus-keyboard && \
echo -e "[Desktop Entry]\nType=Application\nName=Asus Keyboard\nComment=Stable Asus Aura Management\nExec=/usr/bin/asus-keyboard\nIcon=preferences-desktop-keyboard\nTerminal=false\nCategories=Settings;HardwareSettings;" > ~/.local/share/applications/asus-keyboard.desktop && \
update-desktop-database ~/.local/share/applications/
```

# USAGE

Launcher: Search for Asus Keyboard in your application menu.

Terminal: Simply type asus-keyboard.

Note: Launching the app while it is already running will cleanly restart the interface and background loop.

# ASUS KEYBOARD

An app designed to run the LED colors on the keyboard of new Asus laptops such as the TUF Gaming A16. It is a workaround for the color cycles.
PREREQUISITES

Before installing, ensure your system has the following:

asusctl (The underlying driver for Asus hardware)

# QUICK INSTALL

If you have downloaded the pre-compiled asus-keyboard binary, run this command from the folder where it was downloaded:

```bash
    sudo mv ./asus-keyboard /usr/bin/asus-keyboard && \
    sudo chmod +x /usr/bin/asus-keyboard && \
    echo -e "[Desktop Entry]\nType=Application\nName=Asus Keyboard\nComment=Stable Asus Aura Management\nExec=/usr/bin/asus-keyboard\nIcon=preferences-desktop-keyboard\nTerminal=false\nCategories=Settings;HardwareSettings;" > ~/.local/share/applications/asus-keyboard.desktop && \
    update-desktop-database ~/.local/share/applications/
```

# MANUAL BUILD

If you prefer to build from source, ensure you have your compiler and GTK3 headers configured:

```bash
g++ -O3 main.cpp -o asus-keyboard $(pkg-config --cflags --libs gtk+-3.0) -lpthread
```

# USAGE

Launcher: Search for Asus Keyboard in your application menu.

Terminal: Simply type asus-keyboard.

Note: Launching the app while it is already running will cleanly restart the interface and background loop.

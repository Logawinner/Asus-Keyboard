# Asus-Keyboard
An app designed to run the LED colors on the keyboard of new Asus laptop such as the TUF Gaming A16. It is a workaround for the color cycles.

Before installing, ensure your system has the following:

    asusctl (The underlying driver for Asus hardware)
    
Quick Install (Pre-compiled Binary)

If you have downloaded the pre-compiled asus-keyboard binary, run this command from the folder where it was downloaded:
Bash

# Move to system path and set permissions
sudo mv ./asus-keyboard /usr/bin/asus-keyboard && \
sudo chmod +x /usr/bin/asus-keyboard && \
\
# Create the App Launcher entry
echo -e "[Desktop Entry]\nType=Application\nName=Asus Keyboard\nComment=Stable Asus Aura Management\nExec=/usr/bin/asus-keyboard\nIcon=preferences-desktop-keyboard\nTerminal=false\nCategories=Settings;HardwareSettings;" > ~/.local/share/applications/asus-keyboard.desktop && \
\
update-desktop-database ~/.local/share/applications/

Manual Build

If you prefer to build from source:
Bash

g++ -O3 main.cpp -o asus-keyboard $(pkg-config --cflags --libs gtk+-3.0) -lpthread

Usage

    Launcher: Search for Asus Keyboard in your application menu.

    Terminal: Simply type asus-keyboard.

    Note: Launching the app while it is already running will cleanly restart the interface and background loop.

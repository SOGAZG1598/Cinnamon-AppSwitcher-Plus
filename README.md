# Cinnamon-AppSwitcher-Plus

PLEASE BACKUP THE ORIGINAL FILE BEFORE MAKING ANY MODIFICATION.
TESTED ON CINNAMON 6.4.8. (To check your cinnamon version open the terminal and run the command: cinnamon --version)

An enhanced version of the default Cinnamon Desktop appSwitcher.js that brings Windows-style window management to your task switcher.

🚀 The Problem
By default, the Cinnamon application switcher (Alt+Tab) allows you to cycle through windows, but it doesn't provide a quick way to kill a process or close a window directly from the interface.

✨ The Solution
This modification enables the Delete (Supr) key functionality within the switcher. Just like on Windows, you can now:

Press Alt + Tab to open the switcher.

Highlight the window you want to close.

Press Delete (Supr) to close that window instantly without leaving the switcher.

🛠 Installation
Warning: This involves modifying system files. Always back up your original file before proceeding!

Locate your current switcher file:
Usually found at: /usr/share/cinnamon/js/ui/appSwitcher/appSwitcher.js

Backup the original:

Bash
sudo cp /usr/share/cinnamon/js/ui/appSwitcher/appSwitcher.js /usr/share/cinnamon/js/ui/appSwitcher/appSwitcher.js.bak
Replace with this version:
Copy the appSwitcher.js from this repository into that directory:

Bash
sudo cp appSwitcher.js /usr/share/cinnamon/js/ui/appSwitcher/appSwitcher.js
Restart Cinnamon:
Press Alt + F2, type r, and hit Enter.

📝 Modified Code Snippet
For those who prefer to manual-patch, here is the logic added to the keypress handler:

JavaScript
// Logic added to handle the Delete/Supr key
if (symbol == Clutter.Delete) {
    let targetWindow = this._items[this._selectedIndex].window;
    targetWindow.delete(global.get_current_time());
    // Additional logic to refresh switcher state
}
🤝 Contributing
Feel free to open an issue or a pull request if you have ideas for more "muscle memory" shortcuts for the Cinnamon desktop!

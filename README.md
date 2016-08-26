# Runbox Desktop Integration

Open mailto links in Linux desktop using Runbox Webmail.

## How it works

Clicking a mailto link anywhere in Linux forwards the link to the script `mailto-runbox` to format the URL correctly, and opens the formatted Runbox Webmail URL in the default web browser.

## Installation

1. Put `mailto-runbox` wherever you put your executable scripts. (Perhaps in `~/bin` or `~/.local/bin` or some other location in your path). This is the script that does the URL formatting.

2. Put `Runbox Webmail.desktop` in `~/.local/share/applications`. This adds a custom application to open mailto links.

3. Open a terminal and run this command: `update-desktop-database ~/.local/share/applications`. This makes your desktop environment aware of the custom mailto application.

4. Go to Default Applications and set "Runbox Webmail" as the default email application.

5. Restart your web browser, and make sure "Runbox Webmail" is set as the default email application.

6. Click on a mailto link in your Linux desktop. It should open a new Runbox Compose window in your web browser.

## Support

[Open an issue](https://github.com/RunboxScripts/RunboxDesktopIntegration/issues)

Feel free to:

* Report bugs and problems
* Ask any questions
* Make any suggestions

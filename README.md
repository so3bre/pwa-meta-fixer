# pwa-meta-fixer

A lightweight Bash utility for Linux users to fix missing descriptions in PWA (Progressive Web App) desktop entries created by Chromium-based browsers.

## The Problem
By default, Chromium and Ungoogled Chromium create `.desktop` files for PWAs without a `Comment` field. This results in your app launcher (KDE Plasma, GNOME, etc.) showing no description or generic text under the app name.

## The Solution
`pwa-meta-fixer` scans your local applications directory, extracts the app name, and automatically inserts a professional `Comment=Web application for [Name]` field into the metadata.

## Installation & Global Access

Follow these steps to install the script and make it accessible from any terminal window:

### 1. Clone the repository
```bash
git clone [https://github.com/so3bre/pwa-meta-fixer.git](https://github.com/so3bre/pwa-meta-fixer.git)
cd pwa-meta-fixer
```
### 2. Set up your local bin directory
To run the script as a command, you need a directory that is included in your system's PATH. I recommend ~/.local/bin.
```bash
mkdir -p ~/.local/bin
```
### 3. Add to PATH (if needed)
Check your ~/.bashrc (or ~/.zshrc) for the following line. If it's not there, add it to the end of the file:
```bash
export PATH="$HOME/.local/bin:$PATH"
```
After adding the line, reload your configuration: source ~/.bashrc

### 4. Create a symbolic link
This allows you to run the script using the short command pwa-fix without moving the original file from your Git folder:
```bash
chmod +x pwa-meta-fixer.sh
ln -s $(realpath pwa-meta-fixer.sh) ~/.local/bin/pwa-fix
```
Usage
Once installed, you can use the script in two ways:

Automated Scan: Fix all PWAs found in your system.
```bash
pwa-fix
```
Targeted Fix: Fix a specific application by its name.
```bash
pwa-fix ChatGPT
```
## License
MIT

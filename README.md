# Docs Grabber - Documentation Copying GUI

![alt text](docs-grabber.webp)

A simple GUI application that helps you grab documentation from GitHub repositories and integrate it into your working repository for AI context.

## Open Source AI Development!

I've deliberately included the prompts that I use to generate this GUI in the repository alongside the editing prompts that I use to refine the iterations. 

I ran these prompts in Windsurf IDE using Sonnet 3.7.

They reflect the implementation of a method for prompting agentic code generation tools that I've been using for the past several months by which rather than try to cram detailed prompts into the usually limited sidebar, I create them as organized markdown files and then point them from the sidebar as context. 

This message can be particularly affected when coupled with a system prompts where these identical tools support it (for example: Roo Code). 

## Purpose

Docs Grabber provides a quick means to copy documentation from a GitHub repository into your working repository, creating contextual information for AI tools like code generation utilities.

## Features

- Grab documentation from any GitHub repository or specific documentation folder
- Save documentation to a designated location in your repository
- Automatically creates an AI instructions file with metadata about the imported documentation
- Shows progress and status of the documentation grabbing process
- Simple and intuitive user interface
- Persistent settings stored in `~/.config/docs-grabber`
- Customizable filtering options to selectively import documentation:
  - Copy markdown files only (.md, .mdx)
  - Exclude code files
  - Light filtering (exclude binaries and generated files)
- "Open Docs" button to quickly access imported documentation
- System tray integration (when available) that allows minimizing the application to the system tray

## Installation

1. Clone this repository:
```bash
git clone https://github.com/danielrosehill/docs-grabber.git
cd docs-grabber
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

3. For system tray functionality on Linux systems, ensure you have the required packages:
```bash
# For Debian/Ubuntu
sudo apt-get install libxcb-cursor0

# For OpenSUSE
sudo zypper install libxcb-cursor0
```

## Usage

1. Run the application:
```bash
python docs_grabber.py
```

2. Enter the GitHub documentation URL. This can be:
   - A full repository URL (e.g., `https://github.com/open-webui/docs`)
   - A specific documentation folder within a repository (e.g., `https://github.com/All-Hands-AI/OpenHands/tree/main/docs`)

3. Select the target repository path where you want to save the documentation.

4. Choose a filtering mode:
   - **No filtering**: Copy all files from the repository
   - **Copy Markdown documents only (.md, .mdx)**: Only copy markdown files
   - **Exclude code files**: Copy all non-code files
   - **Light filtering**: Exclude binary and generated files

5. Click "Grab Docs" to start the process.

6. The documentation will be saved to a `reference` folder within your selected path, and an `ai-instructions.md` file will be created at the root of the target path.

7. After successful grabbing, click "Open Docs" to view the imported documentation.

## Settings

You can configure default settings by clicking the "Settings" button:

- **Default Repository Path**: Set your base GitHub repositories directory to save time when selecting target paths
- **Default Filtering Mode**: Choose your preferred filtering mode for documentation imports
- **System Tray Options**: Choose whether the application should minimize to the system tray when closed or exit completely

Settings are automatically saved to `~/.config/docs-grabber/settings.json` and will be loaded each time you start the application.

## System Tray Integration

When available, Docs Grabber can be minimized to the system tray:

- The application will show a document icon in your system tray
- Double-click the tray icon to show the main window
- Right-click the tray icon to access a menu with Open and Quit options
- When minimized, notifications will appear for important events (like successful documentation grabbing)

## Troubleshooting

### Display Issues

If you encounter errors related to the display or Qt platform plugin:

1. Make sure you're running the application in a graphical environment
2. Install the required xcb dependencies:
   ```bash
   # For Debian/Ubuntu
   sudo apt-get install libxcb-cursor0
   
   # For OpenSUSE
   sudo zypper install libxcb-cursor0
   ```
3. Set the QT_QPA_PLATFORM environment variable:
   ```bash
   export QT_QPA_PLATFORM=wayland  # or xcb, depending on your system
   ```

## Example

1. Input GitHub Docs URL: `https://github.com/All-Hands-AI/OpenHands/tree/main/docs`
2. Select your working repository path: `/path/to/your/project`
3. Choose filtering mode: "Copy Markdown documents only"
4. Click "Grab Docs"
5. The documentation will be saved to `/path/to/your/project/reference/`
6. An AI instructions file will be created at `/path/to/your/project/ai-instructions.md`
7. Click "Open Docs" to view the imported documentation

## Requirements

- Python 3.6 or higher
- PyQt6
- Git (command-line tool must be installed and accessible in your PATH)
- For system tray functionality: xcb libraries (on Linux)

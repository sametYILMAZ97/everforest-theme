# Everforest Theme for VS Code

A comfortable and pleasant VS Code theme based on the Everforest color palette.

## Features

- **Two variants**: Dark and Light themes
- **Carefully crafted colors**: Based on the official Everforest color scheme
- **Complete coverage**: Editor, UI, terminal, and syntax highlighting
- **Medium contrast**: Uses the default medium contrast palette

## Installation

### Option 1: Install from folder

1. Copy the `everforest-theme` folder to your VS Code extensions directory:
   - **Windows**: `%USERPROFILE%\.vscode\extensions\`
   - **macOS/Linux**: `~/.vscode/extensions/`

2. Restart VS Code

3. Press `Ctrl+K Ctrl+T` (or `Cmd+K Cmd+T` on macOS) to open the theme picker

4. Select either "Everforest Dark" or "Everforest Light"

### Option 2: Package and install as VSIX

1. Install `vsce` (VS Code Extension Manager):
   ```bash
   npm install -g @vscode/vsce
   ```

2. Navigate to the theme folder and package it:
   ```bash
   cd everforest-theme
   vsce package
   ```

3. Install the generated `.vsix` file:
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X)
   - Click the "..." menu at the top
   - Choose "Install from VSIX..."
   - Select the generated `.vsix` file

## Color Palette

### Dark Theme
- Background: `#2D353B`
- Foreground: `#D3C6AA`
- Red: `#E67E80`
- Orange: `#E69875`
- Yellow: `#DBBC7F`
- Green: `#A7C080`
- Aqua: `#83C092`
- Blue: `#7FBBB3`
- Purple: `#D699B6`

### Light Theme
- Background: `#FDF6E3`
- Foreground: `#5C6A72`
- Red: `#F85552`
- Orange: `#F57D26`
- Yellow: `#DFA000`
- Green: `#8DA101`
- Aqua: `#35A77C`
- Blue: `#3A94C5`
- Purple: `#DF69BA`

## Customization

You can customize the theme by editing the theme files in the `themes` folder:
- `everforest-dark.json` - Dark variant
- `everforest-light.json` - Light variant

After making changes, reload VS Code to see the updates.

## Credits

Based on the [Everforest](https://github.com/sainnhe/everforest) color scheme by sainnhe.

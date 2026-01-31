# Everforest Theme & Settings for Zed

A beautiful, warm color scheme for [Zed Editor](https://zed.dev/) based on the popular Everforest theme, along with optimized settings.

## Features

- 🌲 **Two Variants**: Dark and Light themes in one file
- 🎨 **Comprehensive Syntax Highlighting**: Optimized for MERN stack (MongoDB, Express, React, Node.js), Swift, HTML/CSS, and Java with Spring Boot
- 👁️ **Eye-friendly Colors**: Carefully selected warm colors that reduce eye strain
- ✨ **Modern UI**: Consistent styling across editor, panels, and terminal
- 🔤 **Typography Support**: Italic keywords, bold functions, and more
- ⚙️ **Optimized Settings**: Included `zed_settings.json` for a better experience

## Installation

### 1. Install the Theme

Copy the theme file to your Zed themes directory:

- **macOS/Linux**: `~/.config/zed/themes/`
- **Windows**: `%AppData%\Zed\themes\`

```bash
# macOS/Linux
mkdir -p ~/.config/zed/themes
cp everforest.json ~/.config/zed/themes/
```

### 2. Activate the Theme

1. Restart Zed or reload the window.
2. Open the Command Palette (`Cmd+Shift+P` on macOS or `Ctrl+Shift+P` on Windows/Linux).
3. Type "theme selector" and press Enter.
4. Choose either "Everforest Dark" or "Everforest Light".

### 3. Apply Recommended Settings

We have included a `zed_settings.json` file with configuration that complements the theme, including font adjustments and italic/bold syntax highlighting.

To apply these settings:
1. Open your Zed settings: `Cmd+,` (macOS) or `Ctrl+,` (Windows/Linux)
2. Copy the contents of `zed_settings.json` into your user settings `settings.json`.
3. Pay special attention to the `experimental.theme_overrides` section for the best typography experience.

## Color Palette

### Dark Theme
- **Background**: `#2D353B` (dark greenish-gray)
- **Foreground**: `#D3C6AA` (warm beige)
- **Accent**: `#A7C080` (sage green)
- **Keywords**: `#E67E80` (coral red)
- **Strings**: `#A7C080` (sage green)
- **Functions**: `#A7C080` (sage green, bold)
- **Types**: `#DBBC7F` (honey yellow)
- **Numbers**: `#D699B6` (dusty pink)
- **Operators**: `#E69875` (light orange)
- **Comments**: `#859289` (muted sage)

### Light Theme
- **Background**: `#FDF6E3` (warm cream)
- **Foreground**: `#5C6A72` (dark blue-gray)
- **Accent**: `#8DA101` (olive green)
- **Keywords**: `#F85552` (bright red)
- **Strings**: `#8DA101` (olive green)
- **Functions**: `#8DA101` (olive green, bold)
- **Types**: `#DFA000` (golden orange)
- **Numbers**: `#DF69BA` (bright pink)
- **Operators**: `#F57D26` (orange)
- **Comments**: `#939F91` (muted gray-green)

## Language Support

This theme is optimized for:

### JavaScript/TypeScript/React/Node.js
- JSX/TSX components
- Template literals
- Arrow functions
- Async/await syntax
- Import/export statements
- React hooks

### Swift
- SwiftUI syntax
- Attributes (`@Published`, `@State`, etc.)
- Protocols and extensions
- Optionals
- Closures
- String interpolation

### HTML/CSS
- HTML tags and attributes
- CSS selectors and pseudo-classes
- CSS variables
- Media queries
- Flexbox/Grid properties

### Java/Spring Boot
- Spring annotations (`@RestController`, `@Autowired`, etc.)
- JPA annotations
- Generics
- Lambda expressions
- Streams API
- Lombok annotations

### Also Supported
- Python
- Rust
- Go
- Ruby
- PHP
- SQL
- Markdown
- JSON/YAML
- Shell scripts

## Preview

Check out `syntax-test.md` for comprehensive examples of how different syntax elements are highlighted.

## Customization

You can customize the theme by editing the `everforest.json` file. The theme follows the [Zed theme schema](https://zed.dev/schema/themes/v0.2.0.json).

### Example: Change the accent color

```json
{
  "style": {
    "text.accent": "#YOUR_COLOR_HERE",
    "border.focused": "#YOUR_COLOR_HERE"
  }
}
```

## Credits

- Original Everforest theme by [sainnhe](https://github.com/sainnhe/everforest)
- Converted to Zed Editor format by [Samet Yılmaz](https://github.com/sametYILMAZ97)

## License

This theme is provided as-is for use with Zed Editor. Feel free to modify and distribute.

## Feedback

If you encounter any issues or have suggestions for improvements, please [open an issue](https://github.com/sametYILMAZ97/everforest-theme/issues) on GitHub.

---

**Enjoy coding with Everforest! 🌲**
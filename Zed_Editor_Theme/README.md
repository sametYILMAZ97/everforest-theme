# Everforest Theme for Zed Editor

A beautiful, warm color scheme for [Zed Editor](https://zed.dev/) based on the popular Everforest theme. This theme includes both dark and light variants optimized for long coding sessions.

## Features

- 🌲 **Two Variants**: Dark and Light themes in one file
- 🎨 **Comprehensive Syntax Highlighting**: Optimized for MERN stack (MongoDB, Express, React, Node.js), Swift, HTML/CSS, and Java with Spring Boot
- 👁️ **Eye-friendly Colors**: Carefully selected warm colors that reduce eye strain
- ✨ **Modern UI**: Consistent styling across editor, panels, and terminal
- 🔤 **Typography Support**: Italic keywords, bold functions, and more

## Installation

1. **Copy the theme file** to your Zed themes directory:
   - **macOS/Linux**: `~/.config/zed/themes/`
   - **Windows**: `%AppData%\Zed\themes\`

```bash
# macOS/Linux
mkdir -p ~/.config/zed/themes
cp everforest.json ~/.config/zed/themes/
```

2. **Restart Zed** or reload the window

3. **Select the theme**:
   - Open Command Palette (`Cmd+Shift+P` on macOS or `Ctrl+Shift+P` on Windows/Linux)
   - Type "theme selector" and press Enter
   - Choose either "Everforest Dark" or "Everforest Light"

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

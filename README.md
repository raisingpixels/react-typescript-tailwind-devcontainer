# React Parent Developer Devcontainer

A complete VSCode devcontainer setup optimized for React development by parent developers who code in fragmented time. Works with Create React App, Next.js, Vite, and custom React setups.

## Quick Start

1. **Clone this repository** into your React project as `.devcontainer/`
2. **Update your details** in `devcontainer.json` (replace email and name in `postCreateCommand`)
3. **Open in VSCode** and select "Reopen in Container" when prompted
4. **Start coding** - everything is pre-configured!

## What's Included

### 🤖 AI Assistants
- **Claude Code** - Perfect for understanding component architecture and debugging after days away
- **GitHub Copilot** - Smart completions for React, TypeScript, and modern JavaScript
- **Copilot Chat** - Ask questions about React patterns, debugging, and optimization

### ⚛️ React Development Tools
- **TypeScript support** with enhanced intellisense and auto-imports
- **ESLint and Prettier** configured for React best practices
- **React refactoring tools** for component extraction and optimization
- **Emmet support** for JSX with proper tab triggers
- **Auto rename tag** for JSX elements
- **Jest testing support** with smart test discovery

### 🎨 Modern Development Experience
- **Tailwind CSS intellisense** for rapid styling
- **File nesting** to group components, tests, and stories
- **Smart auto-imports** for React hooks and utilities
- **Multiple dev server support** (Create React App, Vite, Next.js, etc.)

### 👨‍👩‍👧‍👦 Parent Developer Optimizations
- **Auto-save after 1 second** - never lose work when interrupted
- **Smart git commits** - stage and commit in one action
- **Auto dark mode** - switches between "Quiet Light" and "Monokai Dimmed" with your system
- **Enhanced prompt** - shows current folder and git branch clearly
- **Persistent bash history** across container rebuilds

## Supported React Frameworks

This devcontainer works out of the box with:

- **Create React App** (port 3000)
- **Next.js** (port 3000)
- **Vite** (port 5173)
- **Custom Webpack setups** (port 8080)
- **Storybook** (port 6006 - add manually if needed)

## Getting Started

### Create React App
```bash
# Create new app (if needed)
npx create-react-app my-app --template typescript
cd my-app

# Start development
npm run dev # or npm start

# Run tests
npm test
```

### Next.js
```bash
# Create new app (if needed)
npx create-next-app@latest my-app --typescript --tailwind --eslint
cd my-app

# Start development
npm run dev

# Build for production
npm run build
```

### Vite
```bash
# Create new app (if needed)
npm create vite@latest my-app -- --template react-ts
cd my-app

# Start development
npm run dev

# Build for production
npm run build
```

## File Organization Features

### Smart File Nesting
Related files are automatically grouped in the file explorer:
- `Component.tsx` groups with `Component.test.tsx`, `Component.stories.tsx`
- `package.json` groups with lock files and config files
- CSS files group with their modules and source maps

### Auto-Import Configuration
- Relative imports preferred for local files
- Smart suggestions for React hooks and utilities
- Auto-import for popular libraries
- Organized imports on save

## Customization

### Adding Your Own Bash Aliases
Edit `.devcontainer/bashrc` and add:
```bash
alias component="mkdir components/$1 && touch components/$1/index.tsx"
alias story="touch $1.stories.tsx"
alias test="npm test -- --coverage --watchAll=false"
```

Then add this line to the container mounts:

```json
"source=${localWorkspaceFolder}/.devcontainer/bashrc,target=/home/node/.bashrc,type=bind"
```

### Framework-Specific Extensions
Add framework-specific extensions to the `extensions` array:

**For Next.js:**
```json
"ms-vscode.vscode-next"
```

**For Styled Components:**
```json
"styled-components.vscode-styled-components"
```

**For GraphQL:**
```json
"graphql.vscode-graphql"
```

### Port Configuration
Modify `forwardPorts` in `devcontainer.json` for custom setups:
```json
"forwardPorts": [3000, 6006], // 6006 for Storybook
```

## Troubleshooting

**Development server not starting?**
- Check if the correct port is forwarded in `devcontainer.json`
- Try the `dev` alias which works across different frameworks

**TypeScript errors on startup?**
- Run `npm install` to install dependencies
- Restart TypeScript server: `Cmd+Shift+P` → "TypeScript: Restart TS Server"

**ESLint/Prettier conflicts?**
- Configuration is optimized for React - restart the container if issues persist
- Check `.eslintrc` and `.prettierrc` in your project for conflicts

**Hot reload not working?**
- Ensure dev server is running with correct binding (the `dev` alias handles this)
- Check if files are being watched correctly

**Tests not running?**
- Jest extension auto-discovery might need a moment - wait for indexing to complete
- Use `test` alias for command-line testing

## Environment Variables

Create a `.env` file in your project root for environment variables:
```bash
# Development
REACT_APP_API_URL=http://localhost:3001
REACT_APP_DEBUG=true

# The devcontainer will automatically load these
```

## Why This Setup Works for Parent Developers

**⚡ Instant Environment**: Clone any React project and be productive in 30 seconds
**🔄 Consistent Everywhere**: Works identically on your laptop, partner's computer, or Codespaces
**🛡️ Never Lose Work**: Auto-save and smart git workflows protect your progress
**🧠 Context Recovery**: AI assistants help you remember component architecture and logic
**👀 Easy on the Eyes**: Comfortable themes for both day and night coding sessions
**🚀 Modern Tooling**: All the latest React development tools pre-configured

## Common Patterns

### Component Creation
```bash
# Create component directory and files
mkdir src/components/Button
touch src/components/Button/index.tsx
touch src/components/Button/Button.test.tsx
touch src/components/Button/Button.stories.tsx
```

### Quick Testing
```bash
# Run specific test file
npm test Button

# Run tests in watch mode
npm test -- --watch

# Generate coverage report
npm test -- --coverage --watchAll=false
```

## Contributing

This devcontainer is part of the [raisingpixels.dev](https://raisingpixels.dev) parent developer resources. Found an improvement? Open an issue or PR!

## License

MIT - Use this however helps your parent developer workflow!

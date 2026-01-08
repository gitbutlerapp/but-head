# but-head

A custom font project with demo landing page.

## Project Structure

```
but-head/
├── font/           # Font source files and exports
│   ├── source/     # Glyphs source files
│   └── export/     # Exported font files
└── demo/           # Demo landing page (Svelte + Vite)
```

## Font

The font source files are located in the `font/` directory:
- `font/source/` - Glyphs source files (ButHead-Regular.glyphs, ButHead-Italic.glyphs)
- `font/export/` - Exported font files

## Demo

A simple landing page built with Svelte and Vite to showcase the font.

### Prerequisites

- Node.js (version 16 or higher)
- pnpm (or npm/yarn)

### Installation

```bash
# Navigate to demo directory
cd demo

# Install dependencies
pnpm install
```

### Development

```bash
# Start the development server
cd demo
pnpm run dev
```

The site will be available at `http://localhost:5173/`

### Build

```bash
# Build for production
cd demo
pnpm run build
```

The built files will be in the `demo/dist` directory.

### Preview

```bash
# Preview the production build
cd demo
pnpm run preview
```

## Project Structure

```
but-head/
├── src/
│   ├── App.svelte       # Main landing page component
│   ├── app.css          # Global styles
│   └── main.js          # Application entry point
├── public/              # Static assets
├── index.html           # HTML template
└── package.json         # Project dependencies
```

## Technologies Used

- [Svelte](https://svelte.dev/) - Frontend framework
- [Vite](https://vitejs.dev/) - Build tool and dev server

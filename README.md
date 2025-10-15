# Kinde React Tauri Starter Kit

A complete starter kit for building desktop applications with React, Tauri, and Kinde authentication.

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://makeapullrequest.com) [![Kinde Docs](https://img.shields.io/badge/Kinde-Docs-eee?style=flat-square)](https://kinde.com/docs/developer-tools) [![Kinde Community](https://img.shields.io/badge/Kinde-Community-eee?style=flat-square)](https://thekindecommunity.slack.com)

## Overview

This starter kit provides a complete foundation for building desktop applications using:
- **React** - Frontend framework
- **Tauri** - Desktop app framework (Rust-based)
- **Kinde** - Authentication and user management
- **Vite** - Build tool and development server

The application includes authentication flows, user management, and a modern desktop UI.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v18 or later)
- [Rust](https://rustup.rs/) (latest stable version)
- [Tauri CLI](https://tauri.app/v1/guides/getting-started/prerequisites#1-system-dependencies)

## Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/kinde-starter-kits/tauri-starter-kit.git
   cd tauri-starter-kit
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or
   pnpm install
   ```

3. **Set up environment variables:**
   ```bash
   cp .env_sample .env
   ```
   
   Update the `.env` file with your Kinde configuration:
   ```env
   VITE_KINDE_DOMAIN=your-domain.kinde.com
   VITE_KINDE_CLIENT_ID=your-client-id
   VITE_KINDE_REDIRECT_URL=http://localhost:1420
   VITE_KINDE_LOGOUT_REDIRECT_URL=http://localhost:1420
   ```

4. **Run the development server:**
   ```bash
   npm run tauri dev
   # or
   pnpm tauri dev
   ```

## Project Structure

```
├── src/                    # React frontend source code
│   ├── components/         # React components
│   │   ├── LoggedIn.tsx    # Authenticated user component
│   │   └── LoggedOut.tsx   # Login component
│   ├── App.tsx             # Main app component
│   ├── main.tsx            # React entry point
│   └── index.css           # Global styles
├── src-tauri/              # Tauri backend (Rust)
│   ├── src/
│   │   └── main.rs         # Rust main file
│   ├── Cargo.toml          # Rust dependencies
│   └── tauri.conf.json     # Tauri configuration
├── public/                 # Static assets
└── package.json            # Node.js dependencies
```

## Available Scripts

- `npm run tauri dev` - Start development server with hot reload
- `npm run tauri build` - Build the desktop application
- `npm run dev` - Start Vite development server (web only)
- `npm run build` - Build for web
- `npm run preview` - Preview web build

## Building for Production

To build the desktop application for production:

```bash
npm run tauri build
```

The built application will be available in `src-tauri/target/release/bundle/`.

## Configuration

### Tauri Configuration

The main Tauri configuration is in `src-tauri/tauri.conf.json`. You can customize:
- App metadata (name, version, description)
- Window settings (size, title, etc.)
- Security settings
- Build configuration

### Kinde Configuration

Configure your Kinde application in the `.env` file. Make sure to:
1. Set up your Kinde application at [kinde.com](https://kinde.com)
2. Configure the redirect URLs to match your development and production URLs
3. Enable the necessary authentication flows

## Development

### Adding New Features

1. **Frontend (React):** Add new components in `src/components/`
2. **Backend (Rust):** Add new Tauri commands in `src-tauri/src/main.rs`
3. **Styling:** Update `src/index.css` or add component-specific styles

### Authentication Flow

The app uses Kinde's React SDK for authentication:
- `LoggedOut.tsx` - Handles login and registration
- `LoggedIn.tsx` - Displays user information and logout functionality

## Contributing

Please refer to Kinde's [contributing guidelines](https://github.com/kinde-oss/.github/blob/main/.github/CONTRIBUTING.md).

## License

By contributing to Kinde, you agree that your contributions will be licensed under its MIT License.

## Support

- [Kinde Documentation](https://kinde.com/docs/)
- [Tauri Documentation](https://tauri.app/)
- [React Documentation](https://react.dev/)
- [Kinde Community Slack](https://thekindecommunity.slack.com)
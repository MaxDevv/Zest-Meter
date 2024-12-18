# Zest-Meter

Zest-Meter is a fun project that analyzes the "zestiness" or subtle flamboyance of a given text input. It uses a simple SvelteKit frontend and a backend API to determine the zest level.

## Getting Started

### Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) (version 14 or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/zest-meter.git
    cd zest-meter
    ```

2. Install the dependencies:

    ```bash
    npm install
    ```

### Running the Development Server

To start the development server, run:

```bash
npm run dev
```

This will start the Vite development server. Open your browser and navigate to `http://localhost:3000` to see the application in action.

### Building for Production

To build the project for production, run:

```bash
npm run build
```

This will create an optimized production build in the `build` directory.

### Previewing the Production Build

To preview the production build, run:

```bash
npm run preview
```

This will start a local server to serve the production build.

### Linting and Formatting

To check for linting errors and format the code, run:

```bash
npm run lint
```

To format the code using Prettier, run:

```bash
npm run format
```

## Project Structure

- `src/routes/+page.svelte`: Main page where users can input text and see the zest level.
- `src/routes/level.svelte`: Component to display individual zest levels.
- `src/lib/index.js`: Placeholder for files to be imported through the `$lib` alias.
- `svelte.config.js`: SvelteKit configuration file.
- `vite.config.js`: Vite configuration file.
- `jsconfig.json`: JavaScript configuration file.
- `eslint.config.js`: ESLint configuration file.
- `.prettierrc`: Prettier configuration file.
- `.prettierignore`: Files to ignore for Prettier.
- `.gitignore`: Files to ignore for Git.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [SvelteKit](https://kit.svelte.dev/)
- [Vite](https://vitejs.dev/)
- [Prettier](https://prettier.io/)
- [ESLint](https://eslint.org/)
## Acknowledgements

- [SvelteKit](https://kit.svelte.dev/)
- [Vite](https://vitejs.dev/)
- [Prettier](https://prettier.io/)
- [ESLint](https://eslint.org/)
- [GitHub Copilot](https://github.com/features/copilot) (used exclusively for the README.md file)

---

*This is my first Svelte project and I'm really liking this library :D*

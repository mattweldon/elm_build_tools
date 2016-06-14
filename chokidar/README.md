# Elm Build Tools - Chokidar

Probably the simplest way to get started. It requires only one NPM package and watches the directories of your choosing running `elm make` if any of the files change.

## Installation

  1. Install Elm (run `elm package install` inside an empty folder)
  2. Add `src` to `source-directories` node in `elm-package.json`.
  3. Initialise `package.json` (run `npm init`)
  4. Install Chokidar CLI (run `npm install chokidar-cli --save-dev`)
  5. Add the following line to `package.json`:
  ```
  {
    …
    "scripts": {
      "watch": "chokidar 'src/*.elm' -c 'elm make src/Main.elm --output main.js' --initial"
    }
    …
  }
  ```

## Running

Run `npm run watch` to start watching all Elm files in `src/` and rebuilding on change.

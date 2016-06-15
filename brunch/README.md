# Elm Build Tools - Brunch

Brunch is a fairly lightweight build tool, typically used in Phoenix (Elixir) applications which makes it ideal for

## Installation

  1. Install Elm (run `elm package install` inside an empty folder)
  2. Add `src` to `source-directories` node in `elm-package.json`.
  3. Install Brunch (run `npm install brunch --save-dev`)
  4. Install Babel Brunch (run `npm install babel-brunch --save-dev`)
  5. Install Elm Brunch (run `npm install elm-brunch --save-dev`)
  6. Add `brunch-config.js`:
  ```
  module.exports = {
    files: {
      javascripts: {
        joinTo: {
          'public/js/app.js': /^app/
        }
      },
      stylesheets: {joinTo: 'public/css/app.css'}
    },

    server: {
      port: 3000
    },

    paths: {
      // Which directories to watch
      watched: ["src"],

      // Where to compile files to
      public: "public"
    },

    plugins: {
      elmBrunch: {
        mainModules: ["src/Main.elm"]
      }
    }
  };
  ```

## Running

Run `brunch watch --server` to start watching all Elm files in `src/` and rebuild them on change. Visit `http://localhost:3000` to view the results.

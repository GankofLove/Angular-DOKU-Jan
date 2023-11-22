


# Angular CLI

### Ausführen
`ng serve`

### Ausführen auf bestimmten Port
`ng s --port 5555`

### Start JSON Server
`json-server --watch db.json`

### Angular 17

From Angular v17 onwards, Standalone is now the new default for the CLI. So when you create a new project you won't have any modules in it if you don't specify anything.

However, it is still possible to create a module-based app by using the `--no-standalone`` flag : 

`ng new --no-standalone`

---

### ng test
ausführen der tests

#### Flags:
- --watch: Retest when some files change.
- --code-coverage: Add a coverage report.
- --progress: Show the progress while running the tests.
- --browsers: Specify which browsers to use.
- --colors: Use colors in the output or not.

---

### ng --version
Angular Version

---

### ng new my-app
neus projekt starten

#### Flags:
- --dry-run: See which files would be created, but don’t actually do anything.
- --verbose: Be more chatty.
- --skip-install: Don’t npm install, useful when offline or with slow internet.
- --skip-tests: Don’t create spec files.
- --skip-git: Don’t initialize a git repo.
- --source-dir: Name of the source directory
- --routing: Add routing to the app.
- --prefix: Specify the prefix to use for components selectors.
- --style: Defaults to css, but can be set to scss.
- --inline-style: Use inline styles for components instead of separate files.
---inline-template: Use inline templates for components instead of separate files.

---

## Create

### ng g c "name"
neue komponente erstellen

### ng g s "name"-service
Servce

### ng g pipe my-pipe
Pipe

### ng g directive "name"

### ng g module fancy-module

### ng g cl my-class

### ng g interface my-interface

### ng g guard my-guard

### ng g enum some-enum






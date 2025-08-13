# desk-display

A project to build a small desk display that shows a clock, calendar events, Todoist tasks, and a Spotify now playing display

## Project Setup

### Install

```bash
$ npm install
```

### Development

```bash
$ npm run dev
```

You'll need to delete the `dist` directory, and then rename the `out` directory to `dist`, then run `npm run dev` again

### Running in Production
```bash
lxterminal --command="npm run dev --enable-features=UseOzonePlatform --ozone-platform=wayland"
```

### Build

```bash
# For windows
$ npm run build:win

# For macOS
$ npm run build:mac

# For Linux
$ npm run build:linux
```

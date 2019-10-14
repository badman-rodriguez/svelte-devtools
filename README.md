# Heads Up Notes:

- Use NVM to install, to test locally. It needs `node": ">=11.14.0"`
- This repo also use: `inkscape` to generate the icon.'
  - `"build:icon": "for size in 16 24 48 96 128; do if [ ! -e dest/icon-$size.png -o src/svelte-logo.svg -nt dest/icon-$size.png ]; then inkscape src/svelte-logo.svg -G -o dest/icon-$size.png -w $size; fi; done"`
- The author also created a new tool called the svelte profiler here: 
  - `git+https://github.com/RedHatter/svelte-listener.git`
  - It looks pretty rough for now, so expect this update frequently.


# Svelte DevTools
[![Mozilla Add-on](https://img.shields.io/amo/users/svelte-devtools?color=red&label=Firefox)](https://addons.mozilla.org/en-US/firefox/addon/svelte-devtools/) [![Chrome Web Store](https://img.shields.io/chrome-web-store/users/ckolcbmkjpjmangdbmnkpjigpkddpogn?color=blue&label=Chrome)](https://chrome.google.com/webstore/detail/svelte-devtools/ckolcbmkjpjmangdbmnkpjigpkddpogn)

Install from the [Firefox addon page](https://addons.mozilla.org/en-US/firefox/addon/svelte-devtools/) or the
[Chrome addon page](https://chrome.google.com/webstore/detail/svelte-devtools/ckolcbmkjpjmangdbmnkpjigpkddpogn)

Svelte Devtools is a Firefox and Chrome extension for the Svelte javascript framework. It allows you to inspect the Svelte state and component hierarchies in the Developer Tools.

After installing you will see a new tab in Developer Tools. This tab displays a tree of Svelte components, HTMLx blocks, and DOM elements that were rendered on the page. By selecting one of the nodes in the tree, you can inspect and edit its current state in the panel to the right.

**Requires svelte version 3.12.0 or above**

![1.1.0 Screenshot](https://raw.githubusercontent.com/RedHatter/svelte-devtools/master/screenshot.png "1.1.0 Screenshot")

# Build from source

## Building

Clone this repository and run the package script.
```
git clone https://github.com/RedHatter/svelte-devtools.git
cd svelte-devtools
npm install
npm run package
```
This should build the codebase and output a zip file under `web-ext-artifacts`.

## Installing

### Firefox

Unsigned addons can't be install in firefox permanently but addons can be installed temporarily.
1. Navigate to `about:debugging`.
2. Click "Load Temporary Add-on" and choose the generated zip file.

### Chrome

1. Navigate to `chrome://extensions/`.
2. Turn on developer mode using the 'Developer mode' switch in the upper right hand corner of the page.
3. Click 'Load Unpacked' and select the `dest` directory.

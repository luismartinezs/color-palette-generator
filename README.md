# Color Palette Generator

Created with [GitHub - web2033/vite-vue3-tailwind-starter: Vite + Vue 3 + Tailwind CSS (starter) ⚡](https://github.com/web2033/vite-vue3-tailwind-starter)

Should be a fancy color palette generator that spits out either json, `tailwind.config.js` compatible or CSS

A palette has N colors (primary, secondary, accent, etc), a color has N shades (specific color values)

A palette or scheme template

- palette []
  - primary []
    - 100
    - ...
    - 900
  - secondary
    - ...

example of tailwind output (no arrays)
- theme
  - black
    - 50
    - 100
    - ...
    - 900
    - DEFAULT
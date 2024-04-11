# Config File

We **highly recommend using a dedicated `uno.config.ts` file** to configure UnoCSS in order to get the best experience with [IDEs](/integrations/vscode) and other integrations.

A full config file looks like this:

```ts twoslash
// uno.config.ts
import {
  defineConfig,
  presetAttributify,
  presetIcons,
  presetTypography,
  presetUno,
  presetWebFonts,
  transformerDirectives,
  transformerVariantGroup
} from 'unocss'

export default defineConfig({
  shortcuts: [
    // ...
  ],
  theme: {
    colors: {
      // ...
    }
  },
  presets: [
    presetUno(),
    presetAttributify(),
    presetIcons(),
    presetTypography(),
    presetWebFonts({
      fonts: {
        // ...
      },
    }),
  ],
  transformers: [
    transformerDirectives(),
    transformerVariantGroup(),
  ],
})
```

By default, UnoCSS will automatically look for `uno.config.{js,ts,mjs,mts}` or `unocss.config.{js,ts,mjs,mts}` in the root directory of your project. You can also specify the config file manually, for example in Vite:

```ts
// vite.config.ts
import { defineConfig } from 'vite'
import UnoCSS from 'unocss/vite'

export default defineConfig({
  plugins: [
    UnoCSS({
      configFile: '../my-uno.config.ts',
    }),
  ],
})
```

For the full list of supported configuration options refer to the [Configurations reference](/config/).

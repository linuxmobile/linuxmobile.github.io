---
layout: post
title: "Configurando Neovim para que luzca increible!"
description: Hace unos días atrás decidí pasarme de mi confiable Geany a Neovim. ¿Las razones? Bueno, quiero comenzar a aprender ReactJS, NextJS, y otros. Y Geany siento que se queda un poco corto. Por eso acá te dejo mi configuración de Neovim para poder programar como los dioses.
date: 2022-01-18
image: https://i.imgur.com/QbJ7boW.png
tags:
- Neovim
- Linux
- Documentacion

---

Hace unos días atrás decidí pasarme de mi confiable Geany a Neovim. ¿Las razones? Bueno, quiero comenzar a aprender ReactJS, NextJS, y otros. Y Geany siento que se queda un poco corto. Por eso acá te dejo mi configuración de Neovim para poder programar como los dioses.

`Por cierto, quiero aclarar que no voy a explicar como instalar Neovim. Ni cada uno de los "plugins/configuraciones" que voy a recomendar. Por lo tanto si algo no entiendes, espérate a mi siguiente post. Donde explicaré como tengo DWM (y mi configuración de Neovim está incluído)`

### ¿Por qué usar NEOVIM? 🤌

Estuve pensando mucho sobre qué IDE utilizar. Y al pasar los días me he decidido por **[Neovim](https://github.com/neovim/neovim)**. Algunas diferencias podrían ser insignificantes para algunos. Pero voy a nombrarlas porque yo las considero "interesantes". 
- **Neovim** limpió el código de vim. **Vim lleva bastante tiempo existiendo.** (Su primer commit fue en el [2004](https://github.com/vim/vim/commit/0c628d1da896bf523373c4fc9616baee712a6e96)). **Neovim limpió** bastante el código "antiguo" con el fin de que sea más ligero.
- **Neovim** me parece más **enfocado en la comunidad**. Vim tiene tan solo 84 colaboradores. Mientras que Neovim tiene 746. Esto no quiere decir mucho. Tan solo que **Neovim** acepta más colaboraciones de parte de las personas.
- Con Neovim hay, aún, **más plugins**. Gracias a **Lua** Neovim a crecido mejor. No más, porque no creo que sea así, sino que hay plugins en Neovim que no funcionan en vim.
- **LSP funciona por default**. En Neovim, ya viene incluído.

#### ¿Por qué Neovim por sobre Geany? 👌

Bueno, resulta que quisiera aprender algunos lenguajes como **NextJS, Vite, y otros**. Y la verdad que **Geany** me resulta espectacular. Pero **no es suficiente**. Así qué tomé la decisión de aprender, primeramente, Neovim. Nunca lo había utilizado anteriormente. Así que tuve que comenzar desde cero.

<div class="gallery-box">
  <div class="gallery">
    <img src="https://i.imgur.com/fg8j8J4.png">
    <img src="https://i.imgur.com/SBAS2bT.png">
  </div>
</div>

### Plugins y Configuraciones ⚙️  :

- **[Packer](https://github.com/wbthomason/packer.nvim)**: *Un administrador de paquetes. Escrito en Lua.*

- **[Nvim-tree](https://github.com/kyazdani42/nvim-tree.lua)**: *Un explorador de archivos escrito en Lua.*

![](https://raw.githubusercontent.com/siduck/dotfiles/all/rice%20flex/nvimtree.png)

- **[Telescope-nvim](https://github.com/nvim-telescope/telescope.nvim)**: *Un buscador "fuzzy". Funciona con las características de Newovim. Es modular y puede hacer de todo. Buscar archivos, texto, configuraciones.
![](https://camo.githubusercontent.com/3d59e34d1f406890adf620546d3d97017ce0aacda034b1788c66fa872f192134/68747470733a2f2f692e696d6775722e636f6d2f5454546a6136742e676966)

- **[Indent-blankline.nvim](https://github.com/lukas-reineke/indent-blankline.nvim)**: *Este plugin añade unas líneas que te sirven de guía para una correcta estructura del código.*

![](https://camo.githubusercontent.com/8f46a98731fdd4dcf098a1bb0652ef076a969197b266105ba96e6470cd243913/68747470733a2f2f692e696d6775722e636f6d2f336752473571492e706e67)

- **[Feline-nvim](https://github.com/feline-nvim/feline.nvim)**: *Una "barra de estado" minimalista, configurable y que queda muy bien!. Escrita en Lua también.*

![](https://raw.githubusercontent.com/siduck/dotfiles/all/rice%20flex/statusline.png)

- **[Bufferline](https://github.com/akinsho/bufferline.nvim)**: *Una especia de "tabs" que te ayuda marcando cuando hay un error. Además podes agregar algunos ajustes gráfico como por ejemplo la X para cerrar y demás.*

![](https://raw.githubusercontent.com/siduck/dotfiles/all/rice%20flex/bufferline.png)

- **[Nvim-web-devicons](https://github.com/kyazdani42/nvim-web-devicons)**: *Es un fork de (vim-devicons)[https://github.com/ryanoasis/vim-devicons]. Y provee de unos íconos coloridos muy bonitos.

![](https://i.imgur.com/IlcSR22.png)

- **[Nvim-Treesitter](https://github.com/nvim-treesitter/nvim-treesitter)**: *Es una herramienta para utilizar (tree-sitter)[https://github.com/tree-sitter/tree-sitter] de forma fácil. Sirve para agregar los highlights que necesites. (Markdown, html, css, js, lua).*

- **[Nvim-Colorizer](https://github.com/tree-sitter/tree-sitter)**: *Un excelente plugin para visualizar los colores.*

![](https://raw.githubusercontent.com/norcalli/github-assets/master/nvim-colorizer.lua-demo-short.gif)

- **[Gitsigns](https://github.com/lewis6991/gitsigns.nvim)**: *Integra algunas herramientas de git. Escrito en lua.

- **[lspconfig](https://github.com/neovim/nvim-lspconfig)**: *Un plugin para trabajar con LSP.*

- **[LSP-Signature](https://github.com/ray-x/lsp_signature.nvim)**: *Va mostrando algunas firmas mientras escribes. (Es algo similar a codelens para vscode)* 

- **[Better-Escape](https://github.com/jdhao/better-escape.vim)**: *Es una herramienta que te ayuda a salir más "rápido" del modo `insert`. Funciona con una combinación de teclas.*

- **[Friendly-Snippets](https://github.com/rafamadriz/friendly-snippets)**: *Una colección de 'Snippets' pre-configurados.*

![](https://user-images.githubusercontent.com/67771985/131255337-d53f3408-b60d-44a2-93ba-9a3240a7436e.gif)

- **[Nvim-CMP](https://github.com/hrsh7th/nvim-cmp)**: *Un motor de completado.*

![](https://user-images.githubusercontent.com/629908/139000570-3ac39587-a88b-43c6-b35e-207489719359.mp4)

- **[Nvim-AutoPairs](https://github.com/windwp/nvim-autopairs)**: *Un completo `AutoPair` escrito en Lua.*

- **[Dashboard-nvim](https://github.com/glepnir/dashboard-nvim)**: *Simplemente es un Dashboard para que nvim luzca lindo*

### Otros plugins que te pueden interesar 💎 :

- [diaglist](https://github.com/onsails/diaglist.nvim)
- [lspking](https://github.com/onsails/lspkind-nvim)
- [fzf-lsp](https://github.com/gfanto/fzf-lsp.nvim)
- [goto-preview](https://github.com/rmagatti/goto-preview) *recomendado*
- [virtual-types](https://github.com/jubnzv/virtual-types.nvim)
- [navigator](https://github.com/ray-x/navigator.lua)
- [nvim-magic](https://github.com/jameshiew/nvim-magic) *recomendado*
- [glow](https://github.com/ellisonleao/glow.nvim) *recomendado*
- [gpeek](https://github.com/stevearc/gkeep.nvim) *útil*
- [twilight](https://github.com/folke/twilight.nvim) *recomendado*

##### ¡Iré agregando más plugins si encuentro alguno que sea útil! Agradecería muchisimo si pudieran compartir el post o el blog. 


#### Créditos y Agradecimientos especiales
*© [NvChad](https://github.com/NvChad/NvChad)*
*© [r/unixporn](https://www.reddit.com/r/unixporn/)*
*© [NeoVim](https://github.com/neovim/neovim)*
*© [Vim](https://github.com/vim/vim)*
*© And everyone who do a contribution to linux community.*

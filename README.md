A fortune plugin for neovim
Useful for dashboard plugins like mini.starter and dashbiard.nvim 

## Installation

Using [packer](https://github.com/wbthomason/packer.nvim) in lua

```lua
use {"rubiin/fortune.nvim", tag = '*'}
```

Using [lazy.nvim](https://github.com/folke/lazy.nvim) in lua

```lua
{
  -- amongst your other plugins
  {'rubiin/fortune.nvim', version = "*"}
}
```

Using [vim-plug](https://github.com/junegunn/vim-plug) in vimscript

```vim
Plug 'rubiin/fortune.nvim', {'tag' : '*'}
```

## Usage
The plugin returns a lua table
```lua
          footer = function()
            local stats = require('lazy').stats()
            local ms = (math.floor(stats.startuptime * 100 + 0.5) / 100)
            local fortune = require('fortune')()
            local info = {}
            info[1] = '⚡ Neovim loaded ' .. stats.loaded .. '/' .. stats.count .. ' plugins in ' .. ms .. 'ms'
            info[2] = ''
            local footer = vim.list_extend(info, fortune)
            return footer
          end,

```

## Configuration
```lua

require('fortune')({
     max_width = 60, -- max width the fortune section should take place
}
)
```

# vscodeVim配置文件
### VSCode setting.json
```
{
    "vim.easymotion": true,
    "vim.incsearch": true,
    "vim.useSystemClipboard": true,
    "vim.useCtrlKeys": true,
    "vim.hlsearch": true,
    "vim.normalModeKeyBindingsNonRecursive": [
      {
        "before": ["<leader>", "d"],
        "after": ["d", "d"]
      },
      {
        "before": ["<C-n>"],
        "commands": [":nohl"]
      },
      {
        "before": ["K"],
        "commands": ["lineBreakInsert"],
        "silent": true
      },
      {
        "before": ["t","h"],
        "commands": [":tabp"]
      },
      {
        "before": ["t","l"],
        "commands": [":tabn"]
      },
      {
        "before": ["leader","t"],
        "commands": ["workbench.action.terminal.focus"]
      },
      {
        "before": ["L"],
        "after": ["$"]
      },
      {
        "before": ["L"],
        "after": ["$"]
      },
      {
        "before": ["H"],
        "after": ["^"]
      },
      // 关闭搜索高亮
      {
        "before":["<C-n>"],
        "commands": [
            ":nohl",
        ]
    },
    // 保存文件
    {
        "before": ["leader", "w"],
        "commands": [
            "workbench.action.files.save",
        ]
    },
    // 
    {
      "before": ["£"],
      "after": ["#"]
  },
  {
    "before": ["leader","g","c"],
    "commands": [
        "workbench.action.showCommands",
    ],
    "silent": true
},
],
"vim.normalModeKeyBindings": [],
"vim.visualModeKeyBindings": [
  {
      "before": [
          ">"
      ],
      "commands": [
          "editor.action.indentLines"
      ]
  },
  {
      "before": [
          "<"
      ],
      "commands": [
          "editor.action.outdentLines"
      ]
  },
], 
    "vim.leader": "<space>",
    "vim.handleKeys": {
      "<C-a>": false,
      "<C-f>": false
    },
    "workbench.iconTheme": "material-icon-theme",
    "editor.formatOnSave": true,
    "[html]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    }
   
}
```

### VSCode Keybinding.json
```
// Place your key bindings in this file to override the defaults
[
    {
        "key": "cmd+shift+y",
        "command": "vim.remap",
        "when": "inputFocus && vim.mode == 'Normal'",
        "args": {
          "after": ["y", "y"],
        }
      },

 
]
```

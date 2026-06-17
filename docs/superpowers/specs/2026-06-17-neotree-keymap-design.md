# Neo-tree 快捷键设计

**日期**: 2026-06-17
**状态**: 已批准

## 目标

用 neo-tree 替代 snacks.explorer 作为文件浏览器，设置 `<leader>e` 快捷键打开/关闭 neo-tree。

## 当前状态

- `lua/plugins/snacks.lua`：explorer 已禁用（`explorer = { enabled = false }`），`<leader>e` 绑定已注释
- `lua/plugins/neo-tree.lua`：neo-tree v3.x 已安装配置，无快捷键绑定
- `lua/config/keymaps.lua`：无 `<leader>e` 绑定

## 设计

### 快捷键行为

`<leader>e` → `:Neotree reveal<cr>`（normal 模式）

- 未打开时：打开 neo-tree 并定位到当前文件
- 已打开时：关闭 neo-tree

使用 neo-tree v3.x 内置 `reveal` 命令的 toggle 语义，无需自定义函数。

### 修改清单

1. **lua/config/keymaps.lua** — 新增 `<leader>e` 绑定
2. **lua/plugins/snacks.lua** — 删除已注释的旧 explorer 绑定（第 68 行）
3. **lua/plugins/neo-tree.lua** — 不变

### 不涉及

- 不修改 neo-tree 的其他默认快捷键（如 `l` 打开文件/展开目录，`h` 折叠/回上级）
- 不改变 snacks.lua 的其他配置

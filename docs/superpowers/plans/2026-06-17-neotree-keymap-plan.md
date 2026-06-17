# Neo-tree 快捷键实现计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task.

**Goal:** 绑定 `<leader>e` 为 neo-tree toggle 快捷键，清理旧注释。

**Architecture:** 在 keymaps.lua 新增一行快捷键映射；在 snacks.lua 删除已注释的旧绑定。

**Tech Stack:** Neovim Lua config

---

### Task 1: 添加 neo-tree 快捷键

**Files:**
- Modify: `lua/config/keymaps.lua`

- [ ] **Step 1: 在 keymaps.lua 末尾新增 `<leader>e` 绑定**

在文件末尾（`<leader>|` 行之后）插入：

```lua
map("n", "<leader>e", "<cmd>Neotree reveal<cr>", { desc = "Toggle Neo-tree" })
```

### Task 2: 清理旧注释

**Files:**
- Modify: `lua/plugins/snacks.lua`

- [ ] **Step 1: 删除第 68 行已注释的 explorer 绑定**

删除行：
```lua
            -- { "<leader>e",       function() Snacks.explorer() end,                                       desc = "File Explorer" },
```

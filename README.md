# Dotfiles
Vim / Git / VSCode（vscodevim）用の個人設定ファイル集。

## 設定内容

- [Vim の設定ファイル（`.vimrc`）](#vim-の設定ファイル)
- Git の設定ファイル（`.gitconfig`）
- [Vim 設定（VSCode + WSL + `vscodevim`）](#vscode--wsl--vim-設定20260207)

## Vim の設定ファイル

- dein.vim のインストール手順  
- https://github.com/Shougo/dein.vim

## VSCode + WSL + Vim 設定（2026/02/07）

### 環境

- **VSCode（v1.109.0）**
  - **Extensions**
    - [Vim v1.32.4 (`vscodevim`)](https://github.com/VSCodeVim/Vim/issues)
    - WSL（Ubuntu 24.04）

### ⚠️ 注意事項（重要）

> **vscodevim は WSL 側の `$HOME/.vimrc` を読み込まない。**  
> **必ず Windows 側のユーザーディレクトリに `.vimrc` を保存する。**
>
> - ❌ `\\wsl$\Ubuntu-24.04\home\user\.vimrc`
> - ✅ `C:\Users\<WindowsUser>\.vimrc`

### settings.json（WSL 用）

#### 開き方

- Windows / Linux: `Ctrl + Shift + P`  (macOS: `Cmd + Shift + P`)
- **Preferences: Open Remote Settings (JSON) (WSL: Ubuntu-24.04)** を開き、下記を記述
- **Developer: Reload Window** で再読み込み

```json
{
  "vim.vimrc.enable": true,
  "vim.vimrc.path": "$HOME/.vimrc"
}
```

### 参考

- vscodevim が WSL 側の `.vimrc` を読み込まない問題に関する Issue  
  https://github.com/VSCodeVim/Vim/issues/9735

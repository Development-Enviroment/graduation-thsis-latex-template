## 環境

### MacBook Pro, Intel, 2020

## Homebrew

### Homebrew のインストール

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## LaTeX

### LaTeX のインストール

✳️CUI の LaTeX です

```
brew install mactex-no-gui --cask
```

### .latexmkrc を作成

1. ホームディレクトリに`.latexmkrc`を作成
2. .latexmkrc に下記を記述

```
#!/usr/bin/env perl

# LaTeX
$latex = 'platex -synctex=1 -halt-on-error -file-line-error %O %S';
$max_repeat = 5;

# BibTeX
$bibtex = 'pbibtex %O %S';
$biber = 'biber --bblencoding=utf8 -u -U --output_safechars %O %S';

# index
$makeindex = 'mendex %O -o %D %S';

# DVI / PDF
$dvipdf = 'dvipdfmx %O -o %D %S';
$pdf_mode = 3;

# preview
$pvc_view_file_via_temporary = 0;
if ($^O eq 'linux') {
    $dvi_previewer = "xdg-open %S";
    $pdf_previewer = "xdg-open %S";
} elsif ($^O eq 'darwin') {
    $dvi_previewer = "open %S";
    $pdf_previewer = "open %S";
} else {
    $dvi_previewer = "start %S";
    $pdf_previewer = "start %S";
}

# clean up
$clean_full_ext = "%R.synctex.gz"
```

## Visual Studio Code

### Visual Studio Code のインストール

```
brew install visual-studio-code --cask
```

### .vscode/settings.json の作成

ルートに`.vscode/settings.json`を作成し、下記を記述

```
{
  "[tex]": {
    // スニペット補完中にも補完を使えるようにする
    "editor.suggest.snippetsPreventQuickSuggestions": false,
    // インデント幅を2にする
    "editor.tabSize": 5
  },

  "[latex]": {
    // スニペット補完中にも補完を使えるようにする
    "editor.suggest.snippetsPreventQuickSuggestions": false,
    // インデント幅を2にする
    "editor.tabSize": 2
  },

  "[bibtex]": {
    // インデント幅を2にする
    "editor.tabSize": 2
  },

  // 使用パッケージのコマンドや環境の補完を有効にする
  "latex-workshop.intellisense.package.enabled": true,

  // 生成ファイルを削除するときに対象とするファイル
  // デフォルト値に "*.synctex.gz" を追加
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk",
    "*.snm",
    "*.nav",
    "*.dvi",
    "*.synctex.gz"
  ],

  // 生成ファイルを "out" ディレクトリに吐き出す
  "latex-workshop.latex.outDir": "../out",

  // ビルドのレシピ
  "latex-workshop.latex.recipes": [
    {
      "name": "latexmk",
      "tools": ["latexmk"]
    }
  ],

  // ビルドのレシピに使われるパーツ
  "latex-workshop.latex.tools": [
    {
      "name": "latexmk",
      "command": "latexmk",
      "args": ["-silent", "-outdir=%OUTDIR%", "%DOC%"]
    }
  ]
}

```

### 拡張機能 LaTeX Workshop のインストール

vscode の拡張機能検索で`latex`と検索すると、LaTeX Workshop が出てくるのでそれをインストール
![latex workshop](latex_workshop.png)

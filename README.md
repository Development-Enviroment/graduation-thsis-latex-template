# 卒業論文用 LaTeX 環境

## LaTeX Tips💡

- [公式ドキュメント](https://www.comp.tmu.ac.jp/tsakai/lectures/intro_tex.html)
- [環境構築](docs/build_enviroment.md)
- vscode 上で ⌘+shift+p を押し，Count words in LaTeX document を押すと，右下に文字数が表示される(セクションの見出し・図表のキャプション・display スタイルの数式は語数にカウントされない)

## ディレクトリ構成

保存(⌘+s)すると、自動的に`out/`フォルダ内に pdf ファイルが出力される(または更新される)

```
root/
 ├── .vscode/
 │      └──settings.json              ・・・vscodeの設定
 ├── docs/                            ・・・ドキュメント
 └── src/
      ├── img/                        ・・・論文に使用する画像など
      ├── out/                        ・・・出力されるpdfファイル
      ├── submission/                 ・・・提出用のファイル
      └── tex/                        ・・・texファイル
           ├── abstract.tex           ・・・概要
           ├── acknowledgments.tex    ・・・謝辞
           ├── chapter1.tex           ・・・第1章
           ├── chapter2.tex           ・・・第2章
           ├── chapter3.tex           ・・・第3章
           ├── chapter4.tex           ・・・第4章
           ├── chapter5.tex           ・・・第5章
           ├── graduation-thsis.tex   ・・・メインファイル
           └── reference.tex          ・・・参考文献
```

# Ngai and Pissarides (2007) Beamer Slides

本仓库用于协作维护高级宏观经济学 II 课程展示 slides。展示论文为：

> Ngai, L. Rachel, and Christopher A. Pissarides. 2007. "Structural Change in a Multisector Model of Growth." *American Economic Review* 97(1): 429--443.

当前版本是一份可直接编辑和编译的 Beamer slides V1。Slides 基于岭南 Beamer 模板整理，重点覆盖论文的多部门增长模型、结构转型机制、总量平衡增长条件、扩展模型和附录推导。

## Repository Contents

```text
.
├── README.md
├── lingnan_beamer_template/
│   ├── main.tex
│   ├── main.pdf
│   ├── latexmkrc
│   ├── beamerthemelingnan.sty
│   ├── beamercolorthemelingnan.sty
│   ├── beamerinnerthemelingnan.sty
│   ├── beamerouterthemelingnan.sty
│   ├── image/
│   │   └── logo3.png
│   └── tex/
│       ├── 01_introduction.tex
│       ├── 02_core_analysis.tex
│       ├── 03_structural_change.tex
│       ├── 04_aggregate_growth.tex
│       ├── 05_extensions_discussion.tex
│       └── 99_appendix.tex
└── paper/
    ├── Ngai和Pissarides - Structural Change in a Multisector Model of Growth.pdf
    └── Ngai和Pissarides - Structural Change in a Multisector Model of Growth-mineru-md/
        └── Ngai和Pissarides - Structural Change in a Multisector Model of Growth.md
```

主要文件说明：

- `lingnan_beamer_template/main.tex`：slides 主入口，包含标题页、作者信息、目录和各章节 `\input{...}`。
- `lingnan_beamer_template/tex/*.tex`：实际 slides 内容，协作修改通常集中在这里。
- `lingnan_beamer_template/main.pdf`：当前已编译的 slides PDF。
- `lingnan_beamer_template/*.sty`：岭南 Beamer 主题样式文件，一般不需要修改。
- `lingnan_beamer_template/image/logo3.png`：页脚 logo。若替换或重命名，需要同步修改 `beamerouterthemelingnan.sty`。
- `paper/*.pdf`：原始论文 PDF。
- `paper/*-mineru-md/*.md`：由 MinerU 转换得到的论文 Markdown，便于检索和摘取公式。

## How To Compile

推荐使用 XeLaTeX。进入 slides 目录后编译两次，以确保目录、页码和跳转链接正确更新：

```powershell
cd lingnan_beamer_template
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

如果本地安装了 `latexmk`，也可以使用：

```powershell
cd lingnan_beamer_template
latexmk -xelatex main.tex
```

编译成功后，输出文件为：

```text
lingnan_beamer_template/main.pdf
```

## Editing Guide

建议按下面的分工方式修改：

- 修改标题、课程名、作者、汇报人：编辑 `lingnan_beamer_template/main.tex`。
- 修改论文背景和研究问题：编辑 `tex/01_introduction.tex`。
- 修改基准模型和核心推导：编辑 `tex/02_core_analysis.tex`。
- 修改结构转型机制：编辑 `tex/03_structural_change.tex`。
- 修改总量平衡增长部分：编辑 `tex/04_aggregate_growth.tex`。
- 修改扩展模型、讨论和结论：编辑 `tex/05_extensions_discussion.tex`。
- 修改附录推导和备份页：编辑 `tex/99_appendix.tex`。

编写 slides 时建议保持以下约定：

- 每页只保留一个核心结论或一段关键推导。
- 公式编号尽量与原论文保持一致，便于核对。
- 引用论文中的变量时沿用原文记号，例如 $x_i$、$X$、$\bar{\gamma}$、$\varepsilon$、$\theta$。
- 新增推导页时，优先放入 `99_appendix.tex`，正文页只保留展示所需的关键步骤。
- 若新增图片，放入 `lingnan_beamer_template/image/`，并使用相对路径引用。

## Suggested Workflow

1. 修改对应章节的 `.tex` 文件。
2. 在 `lingnan_beamer_template/` 下重新编译 `main.tex`。
3. 打开 `main.pdf` 检查公式、分页、遮挡和目录跳转。
4. 提交修改时尽量只提交源文件、必要图片和更新后的 `main.pdf`。

如果多人协作，建议每次提交集中处理一个章节或一个主题，避免同时修改太多文件。

## What Is Ignored

`.gitignore` 已排除以下内容：

- LaTeX 编译中间文件，例如 `.aux`、`.log`、`.nav`、`.snm`、`.toc`、`.xdv`。
- MinerU 转换过程中的内部 JSON、原始副本 PDF 和图片目录。
- 本地中文讲义目录 `paper_explanation_ngai_pissarides/`。
- 任务记录文件 `taskmacropre.md`。
- 模板压缩包和本地 review 截图。
- 常见系统和编辑器临时文件。

因此，GitHub 仓库主要保留可协作编辑 slides 所需的内容，而不包含本地任务笔记和转换中间产物。

## Notes

这份 slides 是 V1，用于提供完整、可修改的展示基础。后续精修可以重点压缩正文页、调整讲述顺序、补充图示，或把较长推导移动到 appendix。

# CTA 期刊 LaTeX 模板 — GBK → UTF-8 转换

《控制理论与应用》(Control Theory & Applications) 期刊 LaTeX 模板的编码转换项目。

## 项目结构

```
.
├── gbk/                    # GBK 编码原版（pdfLaTeX / CTeX 编译）
│   ├── kzllyy.cls
│   ├── kzllyyhead.tex
│   ├── kzllyy template20181214.tex
│   ├── kzllyy template20181214.pdf
│   ├── cite.sty
│   ├── GB.cpx
│   └── 1-1.eps
│
├── utf8/                   # UTF-8 版本 — 本地编译（XeLaTeX + Windows 字体）
│   ├── kzllyy.cls
│   ├── kzllyyhead.tex      ← 使用 SimSun/SimHei/KaiTi/FangSong
│   ├── kzllyy template20181214.tex
│   ├── cite.sty
│   └── 1-1.eps
│
├── utf8-overleaf/          # UTF-8 版本 — Overleaf 编译（XeLaTeX + Fandol 字体）
│   ├── kzllyy.cls
│   ├── kzllyyhead.tex      ← 使用 FandolSong/FandolHei/FandolKai/FandolFang
│   ├── kzllyy template20181214.tex
│   ├── cite.sty
│   └── 1-1.eps
│
└── kzllyy template20181214/ # 原始文件（可删除，已备份至 gbk/）
```

## 三个版本的区别

| | gbk | utf8 | utf8-overleaf |
|---|-----|------|---------------|
| **文件编码** | GBK | UTF-8 | UTF-8 |
| **中文宏包** | `CJK` | `xeCJK` | `xeCJK` |
| **编译器** | pdfLaTeX | XeLaTeX | XeLaTeX |
| **字体** | 系统 CJK 字体 | Windows 字体 | Fandol 字体 (TeX Live 自带) |
| **适用环境** | CTeX 套装 | 本地 TeX Live + Windows | Overleaf / Linux TeX Live |

## 编译方法

### GBK 版本
```bash
pdflatex "kzllyy template20181214.tex"
pdflatex "kzllyy template20181214.tex"
```

### UTF-8 版本（本地 / Overleaf）
```bash
xelatex "kzllyy template20181214.tex"
xelatex "kzllyy template20181214.tex"
```

或使用 latexmk：
```bash
latexmk -xelatex "kzllyy template20181214.tex"
```

### Overleaf 使用方法
1. 将 `utf8-overleaf/` 目录下的所有文件打包为 zip
2. 在 Overleaf 中 New Project → Upload Project → 上传 zip
3. 左上角 **File** → **Settings** → **Main Document** 选 `kzllyy template20181214.tex`
4. **Settings** → **Compiler** 选 **XeLaTeX**

## 字体说明

### 本地 Windows 环境 (`utf8/`)
使用系统自带的 Windows 中文字体：
- SimSun（宋体）、SimHei（黑体）、KaiTi（楷体）、FangSong（仿宋）

### Overleaf / Linux 环境 (`utf8-overleaf/`)
使用 TeX Live 自带的 Fandol 开源字体：
- FandolSong（宋体）、FandolHei（黑体）、FandolKai（楷体）、FandolFang（仿宋）

如需更换字体，编辑对应版本的 `kzllyyhead.tex` 中 `\setCJKmainfont` 和 `\newCJKfamily` 行。

## 🧐 Research

### 🤖 Some general advices (in order) for my friends who are interested in Computer Vision
1. **Read/watch something fun to find your motivations.** - I started my journey in computer vision and machine learning in medical image analysis. That's where I found this topic interesting and impactful to the real world. Some people like robotics, autonomous driving, AI for science, or TikToking. Have as much fun as you can and you will see some problems that you want to work on.
2. **Study a bit about theory first, probably a fundamental course.** - [Justin Johnson's course on Computer Vision](https://www.youtube.com/watch?v=dJYGatp4SvA&list=PL5-TkQAfAZFbzxjBHtzdVCWE0Zbhomg7r&ab_channel=MichiganOnline) was my choice to get a big picture of computer vision and deep learning ; ). If you speak Chinese, [Hung-yi Lee's course on Machine Learning](https://www.youtube.com/watch?v=Ye018rCVvOo&list=PLJV_el3uVTsMhtt7_Y6sgTHGHp1Vb2P2J&ab_channel=Hung-yiLee) is the most fun lecture series to watch. Both courses covered the most fundamental topics in computer vision and machine learning.
3. **Be prepared with coding.** - Computer vision professionals, including both scientists and engineers, code to prove their ideas and build real-world applications. Read and practice programming (usually Python) and you will find yourself familiar with code projects.
4. **Learn mathematics when necessary.** - I don't suggest beginners learn about a lot of math, because an excessive dose of math is acute trauma for many people like me. When I was lost in math for too long, it could become chronic trauma. If you want to dive into research or understand the theory part in papers, it can be less painful to start with some tutorials built on the undergraduate level of math. [MML Book](https://mml-book.github.io/) is my pick as the first math reference book.

### 📑 Literature
How to Read a Paper
https://web.stanford.edu/class/ee384m/Handouts/HowtoReadPaper.pdf

### 📝LaTex
VS Code Latex setting (with Latex-Workshop plugin):
1. Make sure you have installed TeX Live and VS Code Latex-Workshop plugin on your Mac.
2. Add the following code to global `settings.json` of VS Code.
3. Replace `latex-workshop.latexindent.path` with your TeX Live install path, if the path is different.
```
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "%DOC%"
            ]
        },
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "%DOC%"
            ]
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        },
        {
            "name": "makeglossaries",
            "command": "makeglossaries",
            "args": [
              "%DOCFILE%"
            ]
          }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        }
    ],
    "latex-workshop.latexindent.path": "/usr/local/texlive/2021/texmf-dist/scripts/latexindent/latexindent.pl",
    "latex-workshop.view.pdf.viewer": "tab",
    "[latex]": {
        "editor.wordWrap": "on",
        "editor.defaultFormatter": "James-Yu.latex-workshop"
    }
```

### 📈 Experiment

### 🗣️ Communication
How to Speak - YouTube
https://www.youtube.com/watch?v=Unzc731iCUY&ab_channel=MITOpenCourseWare
Some project page templates
https://github.com/nerfies/nerfies.github.io
https://yenchenlin.me/nerf-supervision/
https://mbaradad.github.io/learning_with_noise/


### 💾 Datasets
`Check public datasets quickly`
Roboflow Universe: Open Source Computer Vision Community
https://universe.roboflow.com/


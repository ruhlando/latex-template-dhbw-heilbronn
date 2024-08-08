# DHBW Heilbronn LaTeX Template

## General Notes
* The template is only a sample! Please adapt it to your needs as agreed with your academic supervisor. For example, adapt the citation style, page margins, etc.
* Always use the latest version of this template.
* The template is written for a thesis in English or German.
* The template is written in pure LaTeX. It requires a basic knowledge of LaTeX.

## Template Structure
The template is basically divided into 6 parts:

* main.tex
* ads/
* content/
* images/
* lang/
* settings/

### main.tex
main.tex is the core file of the template and therefore also the file that must be compiled. 
The document structure is described by importing other files (can be changed if required, e.g. if no restriction note is required).

### ads
The ads folder contains the following predefined templates, which do not need to be customised (adjustments are made automatically):

* commandDefs.tex
* cover.tex
* declaration.tex
* header.tex
* restrictionNotices.tex

### content
You can store all your written chapters in the /content/chapter folder.
The following files can also be found here:
* abstract.tex
* appendix.tex
* glossary.tex (to create glossary/list of acronyms run the following command: `makeglossaries main.acn && makeglossaries main.glo`)

### images
You can save all images in the images folder.

### lang
The lang folder contains all the necessary translations.

### settings
The settings folder contains two files:

* settings.tex
* document.tex

Basic settings are predefined in the settings.tex file. (e.g. quoteStyle, documentFont, ...)
Some information about the document to be written must be entered in the document.tex file. (e.g. documentLanguage, documentType, locationUniversity, companyName, ...)

## Document Types
The template offers the following different document types:

* T2_1000 Project Thesis (Semester 1 & 2)
* T2_2000 Project Thesis (Semester 3 & 4)
* T2_3100 Seminar Paper
* T2_3300 Bachelor Thesis
* Others

The template automatically adjusts all relevant settings as soon as the document type is changed.

* The seminar paper (T2_3100) is purely a university thesis. For this reason, the location of the company and the restriction notice are removed. It is also possible to submit the student research project as a   group. The variable multipleAuthors is available for this purpose. If this is set to true, the declaration of independence adapts itself from the I to the we form. Multiple authors only need to be entered in the documentAuthor variable, separated by commas.
* For types other than the predefined types, the document type can be entered directly in the `documentType` field. Company information is then hidden.

## How to install LaTeX

Here you will find links to help you with the installation:
* [Official LaTeX  Website ](https://www.latex-project.org/get/)
* [Getting Started Guide](https://guides.nyu.edu/LaTeX/installation)

If you don't want to install LaTeX on your computer, you can use an online editor: [Overleaf](https://www.overleaf.com/)

Useful website to learn the basics of latex: [Overleaf: Learn LaTeX](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)

> [!TIP]
> If you are already familiar with vscode you can use VS Code as a latex editor with the help of the [LaTeX Workshop](https://github.com/James-Yu/LaTeX-Workshop) extension.

If you use LaTeX Workshop in VS Code, I recommend that you extend your settings.json file as follows to configure the extension:
```json
{
    "latex-workshop.latex.tools": [

        {
         "name": "latexmk",
         "command": "latexmk",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "-pdf",
          "-outdir=%OUTDIR%",
          "%DOC%"
         ],

         "env": {}

        },

        {
         "name": "xelatex",
         "command": "xelatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%"
         ],

         "env": {}

        },

        {
         "name": "pdflatex",
         "command": "pdflatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%"
         ],

         "env": {}

        },

        {
         "name": "biber",
         "command": "biber",
         "args": [
          "%DOCFILE%"
         ],

         "env": {}

        }
       ],

    "latex-workshop.latex.recipes": [
        {
         "name": "pdfLaTeX",
         "tools": [
          "pdflatex"
         ]
        },

        {
         "name": "latexmk",
         "tools": [
          "latexmk"
         ]
        },

        {
         "name": "xelatex",
         "tools": [
          "xelatex"
         ]
        },

        {
         "name": "pdflatex ➞ biber ➞ pdflatex ×2",
         "tools": [
          "pdflatex",
          "biber",
          "pdflatex",
          "pdflatex"
         ]
        },

        {
        "name": "xelatex ➞ biber ➞ xelatex ×2",
        "tools": [
          "xelatex",
          "biber",
          "xelatex",
          "xelatex"
         ]
        }

    ],

    "latex-workshop.synctex.afterBuild.enabled": true,
    "latex-workshop.view.pdf.viewer": "tab",
    "editor.wordWrap": "on"

}
```


---
MOC: "[[PRODUCTIVITE]]"
tags:
---
---
***Références :***

---



> [!info]
> une version raccourcis pour obsidian avec le module [[LATEX SUITE]]

## 📖 Introduction

**LaTeX** est un système de composition de documents basé sur TeX, particulièrement adapté pour la création de documents scientifiques, techniques et académiques. Il se distingue par sa gestion exceptionnelle des formules mathématiques et sa mise en page automatique de haute qualité.

### Avantages de LaTeX

- Qualité typographique professionnelle
- Gestion automatique de la mise en page
- Excellente gestion des mathématiques
- Références croisées automatiques
- Séparation du contenu et de la forme
- Stabilité et portabilité des documents

## 🚀 Installation et Configuration

### Distributions LaTeX

- **Windows** : MikTeX ou TeX Live
- **macOS** : MacTeX (basé sur TeX Live)
- **Linux** : TeX Live via gestionnaire de paquets

### Éditeurs recommandés

- **TeXstudio** (multiplateforme)
- **Overleaf** (en ligne)
- **Visual Studio Code** avec extension LaTeX Workshop
- **Texmaker** (multiplateforme)

## 📋 Structure de base d'un document

```latex
\documentclass[12pt,a4paper]{article}  % Classe et options
\usepackage[utf8]{inputenc}            % Encodage
\usepackage[french]{babel}             % Langue
\usepackage[T1]{fontenc}               % Police

\title{Mon Document}
\author{Votre Nom}
\date{\today}

\begin{document}
\maketitle                             % Titre

\section{Introduction}
Contenu de votre document...

\end{document}
```

## 🏗️ Classes de documents

|Classe|Usage|
|---|---|
|`article`|Articles, rapports courts|
|`report`|Rapports longs, thèses|
|`book`|Livres|
|`letter`|Lettres|
|`beamer`|Présentations|

### Options communes

- `10pt`, `11pt`, `12pt` : Taille de police
- `a4paper`, `letterpaper` : Format papier
- `twocolumn` : Deux colonnes
- `draft` : Mode brouillon

## ✍️ Formatage du texte

### Styles de base

```latex
\textbf{Gras}
\textit{Italique}
\underline{Souligné}
\texttt{Police à chasse fixe}
\emph{Emphase}
```

### Tailles de police

```latex
\tiny \scriptsize \footnotesize \small \normalsize
\large \Large \LARGE \huge \Huge
```

### Alignement

```latex
\begin{center}
Texte centré
\end{center}

\begin{flushleft}
Texte aligné à gauche
\end{flushleft}

\begin{flushright}
Texte aligné à droite
\end{flushright}
```

## 📊 Listes et énumérations

### Liste à puces

```latex
\begin{itemize}
\item Premier élément
\item Deuxième élément
    \begin{itemize}
    \item Sous-élément
    \end{itemize}
\end{itemize}
```

### Liste numérotée

```latex
\begin{enumerate}
\item Premier point
\item Deuxième point
\end{enumerate}
```

### Liste de description

```latex
\begin{description}
\item[LaTeX] Système de composition de documents
\item[PDF] Format de fichier portable
\end{description}
```

## 🧮 Mathématiques

### Mode mathématique en ligne

```latex
La formule $E = mc^2$ est célèbre.
```

### Mode mathématique en bloc

```latex
\begin{equation}
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
\end{equation}
```

### Formules non numérotées

```latex
\[ \lim_{x \to 0} \frac{\sin x}{x} = 1 \]
```

### Symboles mathématiques courants

|Commande|Résultat|Commande|Résultat|
|---|---|---|---|
|`\alpha`|α|`\sum`|∑|
|`\beta`|β|`\int`|∫|
|`\gamma`|γ|`\partial`|∂|
|`\infty`|∞|`\nabla`|∇|
|`\leq`|≤|`\geq`|≥|

### Fractions et indices

```latex
\frac{a}{b}         % Fraction
x^2                 % Exposant
x_i                 % Indice
x^{2y}              % Exposant complexe
x_{i,j}             % Indice complexe
\sqrt{x}            % Racine carrée
\sqrt[n]{x}         % Racine nième
```

### Matrices

```latex
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}

\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
```

## 🔗 Références et liens

### Étiquettes et références

```latex
\section{Introduction}\label{sec:intro}

Voir la section~\ref{sec:intro} page~\pageref{sec:intro}.

\begin{equation}\label{eq:einstein}
E = mc^2
\end{equation}

L'équation~\ref{eq:einstein} montre...
```

### Notes de bas de page

```latex
Texte principal\footnote{Note de bas de page}.
```

## 📚 Bibliographie

### Bibliographie simple

```latex
\begin{thebibliography}{9}
\bibitem{einstein}
A. Einstein. 
\textit{Zur Elektrodynamik bewegter Körper}.
Annalen der Physik, 17:891–921, 1905.
\end{thebibliography}

Citation : \cite{einstein}
```

### Avec BibTeX

```latex
% Dans le préambule
\usepackage{natbib}

% Dans le document
\citep{einstein}  % Citation parenthésée
\citet{einstein}  % Citation textuelle

% En fin de document
\bibliographystyle{plain}
\bibliography{references}
```

## 🖼️ Figures et tableaux

### Insertion d'images

```latex
\usepackage{graphicx}

\begin{figure}[h]
\centering
\includegraphics[width=0.8\textwidth]{image.png}
\caption{Légende de l'image}
\label{fig:exemple}
\end{figure}
```

### Tableaux

```latex
\begin{table}[h]
\centering
\begin{tabular}{|l|c|r|}
\hline
Gauche & Centre & Droite \\
\hline
A & B & C \\
D & E & F \\
\hline
\end{tabular}
\caption{Titre du tableau}
\label{tab:exemple}
\end{table}
```

### Options de positionnement

- `h` : ici (here)
- `t` : en haut (top)
- `b` : en bas (bottom)
- `p` : page séparée
- `!` : force la position

## 📦 Packages essentiels

### Packages de base

```latex
\usepackage[utf8]{inputenc}      % Encodage UTF-8
\usepackage[T1]{fontenc}         % Police européenne
\usepackage[french]{babel}       % Localisation française
\usepackage{amsmath,amsfonts}    % Mathématiques avancées
\usepackage{graphicx}            % Images
\usepackage{hyperref}            % Liens hypertexte
```

### Packages utiles

```latex
\usepackage{geometry}            % Mise en page
\usepackage{fancyhdr}           % En-têtes personnalisés
\usepackage{listings}           % Code source
\usepackage{xcolor}             % Couleurs
\usepackage{tikz}               % Dessins vectoriels
\usepackage{booktabs}           % Tableaux élégants
```

## 🎨 Personnalisation

### Géométrie de la page

```latex
\usepackage[margin=2cm]{geometry}
\usepackage[top=3cm, bottom=2cm, left=2.5cm, right=2.5cm]{geometry}
```

### En-têtes et pieds de page

```latex
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhf{}
\fancyhead[L]{Titre}
\fancyhead[R]{\today}
\fancyfoot[C]{\thepage}
```

### Couleurs

```latex
\usepackage{xcolor}
\textcolor{red}{Texte rouge}
\colorbox{yellow}{Fond jaune}
```

## 💻 Code source

### Environment listings

```latex
\usepackage{listings}
\usepackage{xcolor}

\lstset{
    language=Python,
    basicstyle=\ttfamily,
    keywordstyle=\color{blue},
    commentstyle=\color{green},
    stringstyle=\color{red},
    numbers=left,
    numberstyle=\tiny,
    frame=single
}

\begin{lstlisting}
def hello():
    print("Hello, World!")
\end{lstlisting}
```

## 🔧 Commandes personnalisées

### Nouvelles commandes

```latex
\newcommand{\nom}[nombre_args]{définition}

% Exemples
\newcommand{\R}{\mathbb{R}}           % Sans argument
\newcommand{\vect}[1]{\vec{#1}}       % Avec argument
\newcommand{\abs}[1]{\left|#1\right|} % Valeur absolue
```

### Nouveaux environnements

```latex
\newenvironment{nom}[args]{début}{fin}

% Exemple
\newenvironment{theoreme}
{\begin{quote}\textbf{Théorème :}}
{\end{quote}}
```

## 🐛 Dépannage courant

### Erreurs fréquentes

- **Undefined control sequence** : Commande inconnue
- **Missing $ inserted** : Problème de mode mathématique
- **File not found** : Fichier manquant
- **Too many }'s** : Accolades mal équilibrées

### Caractères spéciaux

```latex
\$ \% \& \# \{ \} \_ \textbackslash
```

## 📋 Modèles de documents

### Article scientifique

```latex
\documentclass[11pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[french]{babel}
\usepackage[T1]{fontenc}
\usepackage{amsmath,amsfonts,amssymb}
\usepackage{graphicx}
\usepackage[margin=2.5cm]{geometry}
\usepackage{hyperref}

\title{Titre de l'article}
\author{Auteur(s)}
\date{\today}

\begin{document}
\maketitle

\begin{abstract}
Résumé de l'article...
\end{abstract}

\section{Introduction}
\section{Méthode}
\section{Résultats}
\section{Discussion}
\section{Conclusion}

\bibliographystyle{plain}
\bibliography{references}

\end{document}
```

### Rapport/Mémoire

```latex
\documentclass[12pt,a4paper]{report}
\usepackage[utf8]{inputenc}
\usepackage[french]{babel}
\usepackage[T1]{fontenc}
\usepackage{graphicx}
\usepackage[margin=2.5cm]{geometry}
\usepackage{fancyhdr}

\pagestyle{fancy}
\fancyhf{}
\fancyhead[L]{\leftmark}
\fancyfoot[C]{\thepage}

\title{Titre du rapport}
\author{Votre nom}
\date{\today}

\begin{document}
\maketitle
\tableofcontents
\newpage

\chapter{Introduction}
\chapter{Développement}
\chapter{Conclusion}

\end{document}
```

## 🎯 Bonnes pratiques

### Organisation des fichiers

- Un fichier principal `.tex`
- Dossier `images/` pour les figures
- Fichier `.bib` pour la bibliographie
- Dossier `chapters/` pour les gros documents

### Style et lisibilité

- Indenter le code LaTeX
- Commenter les sections complexes
- Utiliser des noms d'étiquettes explicites
- Séparer logiquement les sections

### Performance

- Compiler régulièrement pour détecter les erreurs
- Utiliser `\includeonly{}` pour les gros documents
- Optimiser les images (résolution, format)

## 🔄 Processus de compilation

1. **pdflatex** → fichier.pdf
2. **bibtex** → traitement bibliographie
3. **pdflatex** → mise à jour références
4. **pdflatex** → finalisation

```bash
pdflatex document.tex
bibtex document
pdflatex document.tex
pdflatex document.tex
```

## 📖 Ressources complémentaires

### Documentation officielle

- [LaTeX Project](https://www.latex-project.org/)
- [CTAN](https://www.ctan.org/) - Archive des packages
- [Overleaf Documentation](https://www.overleaf.com/learn)

### Outils en ligne

- **Overleaf** : Éditeur collaboratif
- **Detexify** : Reconnaissance de symboles
- **Tables Generator** : Générateur de tableaux
- **Mathpix** : OCR pour formules mathématiques

---

_Fiche créée pour Obsidian - LaTeX Guide Complet_
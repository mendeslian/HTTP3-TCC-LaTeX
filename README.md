# Estudo para migração de APIs REST para o protocolo HTTP/3

Monografia em LaTeX - Trabalho de Conclusão de Curso (Sistemas de Informação, CEFET/RJ, 2026).  
Autor: Lian Prado Tourinan Mendes.

O código e os roteiros dos experimentos estão no repositório [QUICBench-Node](https://github.com/mendeslian/QUICBench-Node).

## Estrutura do projeto

| Pasta / arquivo        | Conteúdo                                                                                             |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| `main.tex`             | Documento principal; inclui pré-textuais, capítulos e referências                                    |
| `config/`              | Pacotes e formatação (`pacotes.tex`)                                                                 |
| `pre-textuais/`        | Capa, folha de rosto, aprovação, agradecimentos, resumo, abstract, listas (figuras, tabelas, siglas) |
| `capitulos/capituloN/` | Corpo do texto (`conteudo.tex`), capítulos 1 a 6                                                     |
| `pos-textuais/`        | Referências bibliográficas                                                                           |
| `assets/figuras/`      | Figuras usadas nos capítulos                                                                         |
| `build/`               | Saída da compilação (PDF e arquivos auxiliares); não é versionado                                    |

## Pré-requisitos

Distribuição TeX com **XeLaTeX** (por exemplo [MiKTeX](https://miktex.org/) ou [TeX Live](https://www.tug.org/texlive/)). Este projeto usa `fontspec` e não compila com `pdflatex`.

Opcional: `latexmk` para compilar em um comando.

## Como gerar o PDF

Na raiz do repositório:

**Opção A —** `latexmk` **(recomendada)**

```bash
latexmk -xelatex -interaction=nonstopmode -output-directory=build main.tex
```

Se o sumário ou links internos ficarem desatualizados, rode o comando de novo ou limpe os auxiliares com `latexmk -c -output-directory=build main.tex` e recompile.

**Opção B — XeLaTeX manual (duas passagens)**

```bash
xelatex -interaction=nonstopmode -output-directory=build main.tex
xelatex -interaction=nonstopmode -output-directory=build main.tex
```

O PDF gerado fica em `build/main.pdf`.

No Windows (PowerShell), use os mesmos comandos a partir da pasta do projeto.

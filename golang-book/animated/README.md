# GoPL 1.4 — GIF animado (Lissajous)

Este diretório registra meu estudo da seção **1.4** do livro *A Linguagem de Programação Go* (Donovan & Kernighan),
gerando **GIFs animados** com Go usando os pacotes `image`, `image/color` e `image/gif`.

## O que eu aprendi aqui

- Um GIF animado é uma sequência de **frames** (imagens) + um **delay** entre eles.
- O tipo `gif.GIF` guarda:
  - `Image`: lista de frames (`[]*image.Paletted`)
  - `Delay`: lista de delays (um por frame, em unidades de 10ms)
  - `LoopCount`: quantas vezes a animação repete
- `image.NewPaletted(rect, palette)` cria uma imagem que usa **paleta de cores**.
  - Em vez de salvar RGB em cada pixel, ela salva um **índice** (`0, 1, 2...`) apontando para `palette`.
  - Por isso a gente desenha com `SetColorIndex(x, y, index)`.

## Como gerar um GIF

Exemplo gerando um arquivo na pasta `animated/` (na raiz do repo):

```bash
go run golang-book/animated/animated-gifs-ex.go > animated/out.gif

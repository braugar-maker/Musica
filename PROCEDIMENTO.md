# Procedimento: repositório Música

Escrito em 21 de setembro de 2026, para quem nunca mexeu nisto.

## O que é e onde está no ar

Este repositório guarda os arquivos de áudio das músicas de Braulio Garcia e o player que toca em https://brauliogarcia.com.br/musica/. Não é acervo de domínio público: **todos os direitos das gravações são do autor.**

- Player em janela própria: https://braugar-maker.github.io/Musica/
- Dados: https://braugar-maker.github.io/Musica/catalogo.json
- Página no site pessoal: https://brauliogarcia.com.br/musica/

Pasta nesta máquina: `/Users/macbook/Arquivos/Musica`
Repositório: `https://github.com/braugar-maker/Musica` (ramo `main`, GitHub Pages servindo a raiz)

## Como regerar

O gerador não mora em `~/bin`. Ele está na pasta de implementação do site pessoal:

```bash
python3 "/Users/macbook/Arquivos/Site Pessoal/Entregas Claude/2026-09-14 meridiano (design)/implementacao/montar_musica.py"
```

Um comando só faz as duas coisas: monta a página Música do `brauliogarcia.com.br` e regera este repositório (`catalogo.json`, `index.html`, `README.md`).

A lista de faixas, com título, ano, gênero e descrição, está dentro do próprio script, nas listas `SOLO` e seguintes. **Para acrescentar uma música nova, edite o script**, não o `index.html`: o HTML é gerado e qualquer edição manual nele se perde na próxima rodada.

## Como publicar

```bash
cd /Users/macbook/Arquivos/Musica && git add -A && git commit -m "descreva a mudança" && git push
```

A página do site pessoal é publicada à parte, pelo WordPress.com, e sempre com confirmação explícita do autor.

## Armadilhas conhecidas

- **Dezesseis das faixas são cópia do fluxo do SoundCloud, a 128 kbps.** Elas estão marcadas na pasta `_origem-soundcloud`. Quando aparecer o master de alguma, troque o arquivo e regere: qualidade melhor sem mexer no resto.
- **`_log/` não é publicado** (está no `.gitignore`).
- **O bounce é o padrão.** Em música antiga reaberta no Logic, o timbre e o arranjo de referência são os do bounce original, não o que o Logic mostra ao abrir o projeto hoje. Plug-in trocado ou ausente muda o som sem avisar.
- **Arquivo grande pesa no Git.** MP3 de mais de 50 MB faz o GitHub reclamar. Para faixa longa, reduza o bitrate antes de acrescentar.

## O que este projeto não faz

Não distribui as músicas em loja nenhuma (isso é a CD Baby), não altera projeto do Logic e não publica no site pessoal sozinho.

# Site pessoal: de blog parado a perfil da pessoa por tras do estudio

Data: 2026-08-26 · Repositorio: `marcelobohn/marcelobohn.github.io`

## O problema

O endereco servia um blog Jekyll criado em 2015: 4 posts, tema padrao do
`jekyll new`, pagina "About" ainda com o texto de exemplo do Jekyll. A stack foi
modernizada hoje (Jekyll 3.6.2 -> 4.4.1, deploy pelo Actions), mas isso resolveu
a infraestrutura, nao a pergunta de para que o endereco serve.

O problema real e de duplicacao. Existiam quatro superficies publicas dizendo
quem Marcelo e, sem nenhuma decisao sobre o papel de cada uma:

| Superficie | Estado antes desta decisao |
|---|---|
| README do perfil (`marcelobohn/marcelobohn`) | reescrito em 2026-08-26 |
| `marcelobohn.github.io` | blog de 2015, tema padrao |
| `resume` + `app-resume` | curriculo JSON, `lastUpdate: 09/10/2017` |
| `ilumina.app.br` | site do estudio, no ar, ativo |

## A descoberta que mudou o desenho

A primeira direcao escolhida foi "vitrine profissional para cliente de software
sob medida". A investigacao mostrou que **essa vitrine ja existe**:
`ilumina.app.br` responde 200 e serve um estudio de desenvolvimento web, com
secoes de Servicos, Portfolio, Qualidade e Contato. O portfolio ja exibe o
iCaixa e o Promessas como estudo de caso com imagem propria — resolvendo, por
conta propria, o problema de mostrar produto privado.

Construir a mesma vitrine no `github.io` criaria duas paginas competindo pela
mesma funcao, e obrigaria o cliente a decidir se contrata a Ilumina ou o
Marcelo. A decisao foi outra: **o estudio vende, a pessoa da lastro.**

## Decisoes

1. **Papel** — o `github.io` e o perfil individual: quem e Marcelo, trajetoria,
   como pensa sobre software. Quando o assunto for contratar, aponta para a
   Ilumina.
2. **Escrita** — os 3 posts reais de 2015 ficam no ar, nas mesmas URLs, numa
   secao de arquivo. A home deixa de ser lista de posts, entao blog parado nao
   parece abandono. O `first-post.markdown` (3 palavras) sai.
3. **Stack** — segue Jekyll 4, ja modernizado e com deploy verde. Descartadas:
   pagina estatica pura (perderia as URLs dos posts) e Vue 3 como no site da
   Ilumina (SPA e peso sem retorno numa pagina feita para ser lida e indexada).
4. **Nao duplicar** — a home nao lista os repositorios publicos; o README do
   perfil ja faz isso. Linka para o GitHub e para.

## Estrutura

| URL | O que e |
|---|---|
| `/` | O perfil |
| `/escrita/` | Os 3 posts de 2015, enquadrados como arquivo |
| `/dev/2015/11/21/artesao-engenheiro.html` e os outros dois | Intactas |
| `/about/` | Redirect para `/` (hoje tem o texto padrao do Jekyll) |
| `/feed.xml` | Continua |

Secoes da home: nome e uma frase · hoje · trajetoria · escrita · contato.

## Arquivos

- novo: `_layouts/home.html`, `escrita.md`
- reescrito: `index.html`, `about.md` (vira redirect)
- ajustado: `_includes/header.html`, `_includes/footer.html`, `_config.yml`
  (`url` em `https`, sem barra final)
- removido: `_posts/2015-11-21-first-post.markdown`
- intocado: `_sass/` (modernizado hoje), `_layouts/post.html`, `feed.xml`

## Entrada que falta

O conteudo da home depende de fatos que nao estao em lugar nenhum do
repositorio. O unico registro e o `resume/pt-BR.json`, de outubro de 2017.
Necessario antes de escrever:

1. O que Marcelo faz hoje: onde, desde quando, em que papel.
2. A Ilumina: de quem e, e como deve aparecer na pagina.
3. Quanto da trajetoria contar.
4. Que contatos expor. O telefone do curriculo fica de fora.

## Fora deste escopo, decorrente dele

`resume` e `app-resume` perdem a funcao quando a trajetoria estiver na home. O
`resume/pt-BR.json` e publico e expoe telefone, data de nascimento e e-mail
pessoal, parado desde 2017. Arquivar os dois e acao em outros repositorios,
tratada em separado.

## Criterios de aceite

- [ ] As 3 URLs de post de 2015 continuam respondendo 200, com o mesmo conteudo.
- [ ] `/about/` nao da 404.
- [ ] A home nao repete a lista de repositorios do README do perfil.
- [ ] Nenhum fato biografico escrito sem origem declarada pelo Marcelo.
- [ ] Build sem avisos, deploy verde pelo Actions.
- [ ] Contraste WCAG AA (4.5:1) em texto de corpo, nos dois temas.

## Revisao de 2026-08-26 — camada visual

O layout era o tema padrao do `jekyll new`. Direcao escolhida: editorial
sobrio, com os tokens do site da Ilumina (`ilumina.app.br`, `src/style.css`)
para que os dois enderecos pertencam a mesma familia — Space Grotesk, IBM Plex
Sans e IBM Plex Mono, mais o azul e a tinta dela.

Herdado: familias, cor, tinta e fundo. **Nao herdado**: pilula de raio 100px,
sombra azul com brilho e cartoes — a linguagem de quem vende. Aqui o registro e
de leitura, coerente com "o estudio vende, a pessoa da lastro".

Isto revoga o criterio "nenhum recurso externo novo": o Marcelo optou pelas
fontes do Google, cientes do custo. Mitigado com `display=swap` e pilha de
fallback real em cada familia — falha do Google troca a fonte, nunca esconde o
texto.

O `--blue` da Ilumina (#2f6bff) da 4.35:1 sobre fundo claro, abaixo do minimo
de 4.5:1 para texto de corpo. No claro entra o `--blue-hover` dela (#1f56e0,
5.86:1); no escuro, o `--blue-lt` (#6da0ff, 7.36:1). A paleta continua sendo a
dela — muda so qual tom ocupa qual papel.

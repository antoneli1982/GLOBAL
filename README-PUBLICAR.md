# Central de Apontamentos — agora é um App (PWA)

O seu painel continua sendo uma página web (funciona no GitHub Pages como antes),
mas agora pode ser **instalado** como aplicativo: no celular vai para a tela de
início e abre em tela cheia, sem a barra do navegador; no PC/notebook instala em
uma janela própria, como um programa. Também abre **offline** depois da primeira
visita, e ganhou um **ícone moderno** próprio.

## Arquivos desta pasta

Todos precisam ser publicados juntos, com os **mesmos nomes**:

- `index.html` — o painel (é o mesmo de antes, com a camada de "app" adicionada)
- `manifest.webmanifest` — a "identidade" do app (nome, ícone, cores)
- `sw.js` — faz o painel abrir sem internet
- `icon-192.png`, `icon-512.png` — ícones do app
- `icon-maskable-192.png`, `icon-maskable-512.png` — ícones adaptáveis (Android)
- `apple-touch-icon.png` — ícone no iPhone/iPad
- `favicon.svg`, `favicon.ico`, `favicon-32.png` — ícone na aba do navegador

## Como publicar (GitHub Pages)

1. Suba **todos** os arquivos acima para a raiz do repositório (ex.: substitua o
   `index.html` antigo e adicione os demais).
2. Se ainda não tiver, ative o Pages em **Settings → Pages** (branch `main`).
3. Acesse o endereço do painel (ex.: `https://antoneli1982.github.io/painel/`).

> Importante: a instalação só funciona pelo endereço publicado (**https://**).
> Abrir o `index.html` direto do computador (file://) mostra a página, mas não
> permite instalar.

## Como instalar

- **Android (Chrome):** aparece o botão **"Instalar app"** no topo do painel — ou
  use o menu ⋮ do navegador → *Instalar aplicativo / Adicionar à tela inicial*.
- **iPhone / iPad (Safari):** toque em **Compartilhar** e depois em **Adicionar à
  Tela de Início**. (O painel mostra essa dica automaticamente.)
- **PC / Notebook (Chrome ou Edge):** clique em **"Instalar app"** no topo — ou no
  ícone de instalar que aparece na barra de endereço.

*Observação: o texto exato dos botões/menus muda um pouco conforme a versão do
navegador. Se algo estiver com nome diferente, vale conferir no menu do seu
navegador.*

## Como adicionar ou editar uma ferramenta

Igual a antes: abra o `index.html`, procure `const TOOLS = [` (perto do fim) e
edite os blocos. Nada mudou nessa parte.

## ⚠️ Ao republicar depois de editar (passo que evita dor de cabeça)

Como o app guarda uma cópia para abrir offline, os aparelhos já instalados podem
continuar mostrando a **versão antiga** depois de uma edição. Para forçar a
atualização, abra o `sw.js` e troque o número da versão na primeira linha:

```js
const CACHE = "apontamentos-v1";   // mude para "apontamentos-v2", "v3"...
```

Salve, republique, e na próxima vez que o app abrir com internet ele se atualiza.

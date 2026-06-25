# 🎉 Arraiá DNR 2026

Site da festa junina **Arraiá DNR 2026** (08/08/2026). Página única com confirmação de
presença, "o que falta levar", brincadeiras, playlist, mural de recados, votação de
horário, local/mapa e vaquinha via Pix.

🔗 **No ar em:** https://arraia-dnr-2026.web.app

## Como funciona
- Site estático (um único `public/index.html`) em JavaScript puro.
- Os dados ficam no **Firebase Firestore** (projeto `casa-tha`), isolados na coleção
  `arraia2026`, e atualizam **em tempo real** pra todos os convidados.

## Como editar
Edite o arquivo [`public/index.html`](public/index.html) — direto aqui no GitHub
(botão ✏️) ou no computador.

Coisas comuns de trocar (é só buscar no arquivo):
- Link do grupo do WhatsApp: `https://chat.whatsapp.com/SEU-LINK-DO-GRUPO`
- Link da playlist do Spotify: `https://open.spotify.com/`

## Como publicar as mudanças
No computador, dentro desta pasta:

```powershell
firebase deploy --only hosting
```

> Edições feitas só aqui no GitHub **não** vão pro ar sozinhas — é preciso rodar o
> comando acima. (Dá pra automatizar isso com GitHub Actions, se quiser.)

## Sobre o `firebaseConfig`
As chaves do Firebase no `index.html` (apiKey etc.) **podem ser públicas** — não são
senha. A segurança vem das **regras do Firestore**, que liberam só a coleção `arraia2026`.

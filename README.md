# Escuta · protótipo PWA

Protótipo navegável do app de escuta anônima por ligação. Telas, busca, filtros e fluxos funcionam; ouvintes e ligações são simulados.

## O que tem aqui

- `index.html`: o app inteiro, numa página só
- `manifest.webmanifest`: nome, cores e ícones para instalar na tela inicial
- `sw.js`: service worker; depois da primeira visita o app abre sem internet
- `icons/`: ícones do app (192, 512, maskable, Apple e SVG)

## Publicar

Qualquer hospedagem estática com HTTPS serve:

- **Netlify**: arraste esta pasta em https://app.netlify.com/drop
- **GitHub Pages**: suba os arquivos num repositório e ative Pages em Settings
- **Vercel**: rode `npx vercel` dentro desta pasta

Depois de publicado, abra o link no celular e use "Adicionar à tela inicial".

## Testar no computador

```
python3 -m http.server 8080
```

Abra http://localhost:8080. O service worker só funciona em HTTPS ou em localhost.

## O que falta para virar produto

- Voz real: WebRTC com servidor TURN e sinalização por WebSocket
- Fila e matching por tema e disponibilidade no servidor
- Notificações push para ouvintes (Web Push)
- Moderação: fila de denúncias e bloqueio por dispositivo, sem gravar áudio

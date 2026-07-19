# Deploy do n8n no Render (Blueprint)

Este repo contem o render.yaml que define o servico n8n no Render.
O n8n roda a partir da imagem oficial n8nio/n8n:latest (nao precisa build).

## Como subir
1. Clone: git clone https://github.com/helviocorp/meu-n8n.git && cd meu-n8n
2. Coloque render.yaml e README.md na raiz
3. git add . && git commit -m "add n8n blueprint" && git push origin main
4. Render -> New -> Blueprint -> conecta helviocorp/meu-n8n
   - Blueprint Name: Trampoaki-v01
   - Branch: main
   - Blueprint Path: (vazio)

## Variaveis sync:false (preencher no dashboard do Render apos o deploy)
  N8N_BASIC_AUTH_USER   = admin (ou outro)
  N8N_BASIC_AUTH_PASSWORD = senha forte
  N8N_ENCRYPTION_KEY    = gere: openssl rand -hex 24
  WEBHOOK_URL           = https://<nome>.onrender.com

## Detalhes
- Plano Starter (1GB RAM) minimo recomendado. Free tier trava por RAM.
- Disco persistente montado em /home/node/.n8n (1GB) -> guarda workflows/credenciais.
- Health check: /
- Porta: 5678

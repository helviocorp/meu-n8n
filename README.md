# Deploy do n8n no Render (Blueprint)

Este repo contem apenas o `render.yaml` que define o servico n8n no Render.
O n8n roda a partir da imagem oficial `n8nio/n8n:latest` (nao precisa build).

## Como subir

1. Clone este repo:
   git clone https://github.com/helviocorp/meu-n8n.git
   cd meu-n8n

2. (os arquivos render.yaml e README.md ja estao aqui)

3. Commit e push:
   git add .
   git commit -m "add n8n render blueprint"
   git push

4. No Render:
   - New -> Blueprint
   - Conecta o repo helviocorp/meu-n8n
   - O Render le o render.yaml e cria o servico "n8n"

## Variaveis de ambiente (preencher no dashboard do Render apos o deploy)

As variaveis marcadas como "sync: false" no render.yaml DEVEM ser preenchidas
voce mesmo no dashboard (Render -> n8n -> Environment), nunca commite segredos:

  N8N_BASIC_AUTH_USER       = usuario de acesso (ex: admin)
  N8N_BASIC_AUTH_PASSWORD   = senha forte
  N8N_ENCRYPTION_KEY        = gere com:  openssl rand -hex 24
  WEBHOOK_URL               = https://<nome-do-service>.onrender.com

## Observacoes

- Plano Starter (1GB RAM) eh o minimo recomendado. Free tier trava por falta de RAM.
- Health check: /
- Porta: 5678
- Apos "Live", acesse https://<seu-nome>.onrender.com e faca login.

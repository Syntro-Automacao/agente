# Site público do agente Syntro

Site estático para publicação em `https://agente.syntro.com.br/`. Esta pasta é
independente do agente de WhatsApp e não contém credenciais nem dados de clientes.

## Páginas

- Início: `https://agente.syntro.com.br/`
- Política de privacidade: `https://agente.syntro.com.br/privacidade/`
- Termos de uso: `https://agente.syntro.com.br/termos/`

## Configuração no Google Auth Platform

Depois que o deploy estiver concluído e os três endereços abrirem em HTTPS:

- Página inicial do aplicativo: `https://agente.syntro.com.br/`
- Link da Política de Privacidade: `https://agente.syntro.com.br/privacidade/`
- Link dos Termos de Serviço: `https://agente.syntro.com.br/termos/`
- Domínio autorizado: `syntro.com.br`

O domínio precisa estar verificado no Google Search Console pela conta que
administra o projeto OAuth. O callback OAuth `http://localhost:3333/oauth2callback`
continua configurado no cliente OAuth; ele não é substituído pelo domínio do site.

## Git e cPanel

Use o conteúdo desta pasta como raiz do repositório GitHub dedicado ao site
(`Syntro-Automacao/agente`). Não inicialize o Git na raiz do projeto do bot.
No cPanel, clone esse repositório e publique seu conteúdo no document root de
`agente.syntro.com.br`, garantindo que `index.html` fique na raiz pública.

Se o repositório GitHub ainda não existir, crie-o vazio e, no terminal aberto
nesta pasta, configure o remoto e envie a branch `main`:

```powershell
git init
git add README.md index.html styles.css privacidade/index.html termos/index.html
git commit -m "Add public OAuth information pages"
git branch -M main
git remote add origin https://github.com/Syntro-Automacao/agente.git
git push -u origin main
```

## Revisão antes de publicar

O texto descreve o comportamento atual observado no código do agente. Antes de
usar as URLs numa publicação/verificação OAuth, a Syntro deve validar o texto
com a pessoa responsável por privacidade/jurídico e confirmar a identificação
empresarial oficial e os processos reais de retenção, backups e atendimento a
pedidos LGPD.

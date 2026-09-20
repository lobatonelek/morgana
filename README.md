# Morgana Hub — Versão Final

Hub de enxoval e preparação para a chegada da Morgana.

## O que esta versão inclui
- Inventário com fraldas, roupas e demais itens.
- Progresso da gestação calculado dinamicamente pela DPP de **17/11/2026** (40 semanas).
- Checklist: ao clicar **Comprei**, o item sai da lista e entra no inventário.
- Aba **Presente**: convidados podem reservar/comprar itens; presentes comprados aparecem na tela inicial até a família confirmar o recebimento; ao confirmar, entram no inventário.
- Calendário com consultas, exames, tarefas, trabalho e outros compromissos, com data e horário.
- Modo local via localStorage e modo compartilhado via Supabase.

## Deploy na Vercel
- Framework: Vite
- Build command: `npm run build`
- Output directory: `dist`
- Install command: `npm install`

## Para sincronizar Presentes/Calendário entre celulares
1. Crie um projeto no Supabase.
2. No **SQL Editor**, execute `supabase/schema.sql`.
3. Na Vercel, adicione as variáveis:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_PUBLISHABLE_KEY`
4. Faça um novo deploy.

Sem Supabase, o Hub continua funcionando, mas cada navegador mantém seus próprios dados. Isso significa que uma compra marcada por um convidado não chegará ao celular da família.

## Observação de privacidade
O schema atual permite leitura e alteração anônima para que convidados possam marcar presentes sem login. Quem tiver o link poderá interagir com os dados. Se o Hub for compartilhado amplamente, a próxima evolução recomendada é adicionar autenticação/PIN para as áreas da família.


## Release final
Esta versão consolida as alterações aprovadas em 20/09/2026.

- DPP configurada: **17/11/2026**.
- Calendário permanece como a última categoria do menu lateral.
- Checklist comprado entra automaticamente no inventário.
- Presente reservado/comprado aparece na tela inicial até ser marcado como recebido.
- Presente recebido entra automaticamente no inventário.

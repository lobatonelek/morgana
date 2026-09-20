# Morgana Hub — v3.2

Hub de enxoval e preparação para a chegada da Morgana.

## Integração entre Checklist, Presentes, Recomendações e Inventário

- **Adicionar desejo:** cria o item no Checklist e na lista de Presentes ao mesmo tempo.
- **Comprei:** remove a pendência, retira o item da lista disponível para presentes e adiciona ao Inventário.
- **Presente reservado/comprado:** deixa de aparecer como compra pendente no Checklist, evitando compra duplicada.
- **Liberar presente:** devolve o item ao Checklist e à lista disponível.
- **Recebemos:** adiciona ao Inventário e remove das pendências.
- **Recomendações:** itens originalmente em falta são recalculados quando entram no Inventário.

## Modo online

Com `VITE_SUPABASE_URL` e `VITE_SUPABASE_PUBLISHABLE_KEY` configuradas na Vercel, Inventário, Checklist, Presentes e Calendário são compartilhados via Supabase.

Execute `supabase/schema.sql` no SQL Editor do Supabase antes do primeiro uso online.

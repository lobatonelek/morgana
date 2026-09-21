# Morgana Hub — v3.3

Hub de enxoval, presentes e preparação para a chegada da Morgana.

## Mudanças da v3.3

- Início simplificado: mantém gestação, calendário, estoque total e roupas catalogadas.
- Presentes comprados/aguardando entrega aparecem logo abaixo do calendário.
- Fraldas e roupas ficam lado a lado, com visualização rápida por tamanho/peça.
- Inventário permite ordenar todas as colunas clicando no cabeçalho.
- Recomendações em formato de lista, com **Temos**, **Faixa de referência** e status:
  - Verde = Sobrando
  - Amarelo = OK
  - Vermelho = Falta
- Checklist e Presentes usam a mesma lista lógica:
  - adicionar no Checklist também adiciona em Presentes;
  - comprar pela família remove das duas listas e adiciona ao Inventário;
  - presente comprado por terceiro remove de Checklist e Presentes e aparece no Início aguardando entrega;
  - confirmar recebimento adiciona ao Inventário e recalcula Recomendações.
- Aba Presente mostra apenas itens ainda disponíveis.
- Calendário mostra **Agenda do mês** e **Próximos eventos** com o mesmo padrão visual.

## Supabase / modo online

Variáveis na Vercel:

```env
VITE_SUPABASE_URL=...
VITE_SUPABASE_PUBLISHABLE_KEY=...
```

Execute `supabase/schema.sql` no SQL Editor do Supabase.

## Deploy seguro

Use a branch `morgana.v3.online`, faça o push, teste o Preview da Vercel e só depois faça merge na `main`.

## Novidades v3.4

- Checklist aceita um **link de exemplo do produto**; o mesmo link é exibido na lista de Presentes.
- Recomendações agora têm o botão **Adicionar recomendação**.
- Uma recomendação personalizada pode usar um item já existente no Inventário e comparar automaticamente o estoque atual com uma **meta definida pela família**.
- Recomendações personalizadas ficam sincronizadas via Supabase.

### Atualização do Supabase

Depois de publicar a v3.4, execute novamente `supabase/schema.sql` no SQL Editor. Ele faz uma migração segura, adicionando `product_url` às tabelas `checklist`/`gifts` e criando `custom_recommendations` sem apagar os dados existentes.

## v3.5
- Aba Presente passa a refletir diretamente o Checklist, evitando divergência de contagem.
- Recomendações podem ser ordenadas por Item, Temos, Referência/meta e Status.
- Inventário ganhou filtro por tamanho e uma barra de filtros limpa, sem controle visual extra.
- Calendário voltou ao layout com Agenda do mês e Próximos eventos empilhados na lateral.
- Não há alteração de schema nesta versão; não é necessário rodar SQL novo no Supabase se a v3.4 já foi aplicada.

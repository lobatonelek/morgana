# Morgana Hub — Online

Hub de enxoval, presentes e organização para a chegada da Morgana.

## Novidades desta versão

- Tema claro/escuro com preferência salva no navegador.
- Calendário em destaque logo abaixo do progresso da gestação na tela inicial.
- Sincronização em tempo real de inventário, checklist, presentes e calendário via Supabase.
- Continua funcionando em modo local se o Supabase ainda não estiver configurado.

## 1. Supabase

1. Crie um projeto em https://supabase.com.
2. Abra **SQL Editor** e execute todo o arquivo `supabase/schema.sql`.
3. Em **Project Settings → API**, copie:
   - **Project URL**
   - **Publishable key** (ou anon key, se sua tela ainda usar essa nomenclatura)

## 2. Vercel

No projeto do Morgana Hub, abra **Settings → Environment Variables** e crie:

- `VITE_SUPABASE_URL` = Project URL do Supabase
- `VITE_SUPABASE_PUBLISHABLE_KEY` = Publishable key do Supabase

Marque **Production**, **Preview** e **Development** para as duas variáveis. Depois faça um novo deploy.

Quando estiver correto, o rodapé da barra lateral mostrará **“Sincronizado online”** e **“Supabase conectado · dados compartilhados”**.

## 3. GitHub / Vercel

O projeto usa Vite:

- Framework Preset: `Vite`
- Build Command: `npm run build`
- Output Directory: `dist`
- Root Directory: `./`

## Observação de acesso

A configuração atual permite acesso público aos dados via chave pública do projeto para que a lista de presentes funcione sem login. Use este Hub apenas para informações que vocês aceitam compartilhar com quem tiver o link. Não cadastre dados médicos sensíveis, documentos, telefones, endereços particulares ou outras informações privadas.

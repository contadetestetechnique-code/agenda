# Agenda João Reinaldo — GitHub Pages + Supabase

Projeto estático: GitHub Pages hospeda o site; Supabase fornece autenticação e banco de dados.

## 1) Criar o projeto Supabase
1. Acesse https://supabase.com/ e crie um projeto.
2. No painel, abra **SQL Editor**.
3. Copie todo o conteúdo de `supabase/schema.sql`, cole no SQL Editor e execute.
4. Em **Project Settings → API** (o nome pode variar), copie a **Project URL** e a chave pública **anon / publishable**.

## 2) Configurar o site
1. Abra `index.html` em um editor de texto.
2. Procure `SUPABASE_URL` e `SUPABASE_ANON_KEY`.
3. Substitua os textos `COLE_AQUI...` pela URL e pela chave pública do seu projeto.
4. Salve. **Nunca use service_role/secret key, senha do banco ou credenciais privadas no HTML/GitHub.**

## 3) Publicar no GitHub Pages
1. Crie no GitHub um repositório, por exemplo `agenda-joao-reinaldo`.
2. Envie `index.html`, `README.md`, `.nojekyll` e a pasta `supabase` para a raiz do repositório.
3. Abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**, branch `main`, pasta `/ (root)` e salve.
5. Aguarde o endereço, geralmente `https://SEU-USUARIO.github.io/agenda-joao-reinaldo/`.

## 4) Configurar URLs no Supabase
Em **Authentication → URL Configuration**, defina o endereço publicado como **Site URL** e adicione o endereço completo do GitHub Pages em **Redirect URLs**. Salve.

## 5) Criar a conta e usar
Abra o site, escolha **Criar conta**, informe seu e-mail e crie uma senha. Se o Supabase pedir confirmação, confirme pelo e-mail. Depois entre com a mesma conta no PC e no Moto G60.

## Incluído
- Login, criação de conta, logout e solicitação de recuperação de senha.
- Calendário mensal; criar, editar e excluir compromissos.
- Tarefas; criar, editar, concluir/reabrir e excluir.
- Clientes; criar, editar e excluir.
- Anotações sincronizadas na nuvem.
- Políticas RLS por usuário para proteger os registros.

## Segurança e limitações
GitHub Pages é hospedagem estática; o banco e autenticação ficam no Supabase. A chave pública anon/publishable é própria para uso no navegador, pois as políticas RLS limitam o acesso aos dados do usuário autenticado. Nunca exponha `service_role` ou chaves secretas. Para agenda de uso pessoal, depois de criar a sua conta, considere desativar novos cadastros nas configurações de autenticação do Supabase.

# Meu Treino — sistema para personal trainer

App web (um único `index.html`) para você montar treinos e seus alunos acessarem pelo celular.
Hospedagem: GitHub Pages (grátis). Login e dados: Firebase (plano gratuito Spark é suficiente).

## 1. Criar o projeto no Firebase (5 min)
1. Acesse https://console.firebase.google.com → **Adicionar projeto**.
2. **Authentication** → *Primeiros passos* → ative **E-mail/senha**.
3. Ainda em Authentication → aba **Usuários** → **Adicionar usuário**: crie a **sua** conta de personal (seu e-mail + senha).
4. **Firestore Database** → *Criar banco de dados* → modo produção → escolha uma região (ex.: `southamerica-east1`).
5. Firestore → aba **Regras** → cole o conteúdo de `firestore.rules`, troque `seu-email@exemplo.com` pelo seu e-mail (minúsculas) → **Publicar**.
6. Configurações do projeto (engrenagem) → **Seus apps** → ícone `</>` (Web) → registre o app e copie o objeto `firebaseConfig`.

## 2. Configurar o index.html
No começo do `<script>`, no bloco `CONFIGURAÇÃO`, cole os valores do `firebaseConfig` e coloque o seu e-mail em `personalEmail` (o mesmo do passo 3).

## 3. Publicar no GitHub Pages
1. Crie um repositório no GitHub e envie o `index.html`.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)` → Save.
3. Seu link será `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.
4. No Firebase → Authentication → Configurações → **Domínios autorizados** → adicione `SEU-USUARIO.github.io`.

No celular: abra o link e use "Adicionar à tela inicial" para virar um ícone de app.

## 4. Usar
- Entre com seu e-mail e senha → aba **Ajustes**: coloque seu nome e WhatsApp (ex.: `5591999999999`).
- Aba **Alunos** → **+ Novo aluno**: informe nome, login (ex.: `maria.souza`) e senha. Passe o link e esses dados para o aluno.
- Dentro do aluno → **+ Novo treino** → adicione exercícios da biblioteca, defina séries, reps, carga, descanso e observações → Salvar.
- Aba **Exercícios**: mais de 130 exercícios de academia comum/rede/bairro, com instruções. Você pode editar instruções, colar o link de um vídeo do YouTube seu e criar exercícios novos.
- O aluno vê o treino, marca o que fez, anota a carga do dia, abre "Como fazer", "Ver execução" (YouTube) e "Tirar dúvida" (abre o WhatsApp com mensagem pronta para você).

## Observações
- Sem link de vídeo cadastrado, o botão "Ver execução" abre uma busca do YouTube pelo nome do exercício. Cole o link do vídeo que preferir na edição do exercício.
- Senha do aluno: o app não consegue trocar a senha de outro usuário. Para o aluno poder recuperar a senha sozinho, cadastre-o com um **e-mail real** no campo de login (ele usa "Esqueci a senha"). Se o aluno foi criado só com login simples e esqueceu a senha, cadastre-o de novo com outro login (ex.: `maria.souza2`).
- Excluir um aluno remove os dados dele do app; a conta de login continua existindo no Firebase (sem acesso a nada).

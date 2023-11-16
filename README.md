# VS Code Extension - Code Snnipet

- O intuito dessa extensão é facilitar o uso do design system da zenvia.

# Instalação

```bash
npm install -g yo generator-code
```

Para iniciar. basta executar

```bash
yo code

# ? What type of extension do you want to create? New Code Snnipets
```

Preencha as demais perguntas e bora.

# Código

Todo o código do nosso snnipet vai ficar em `snippets/snippets.code-snippets`

Por padrão, o vs code já gera um comentário com a estrutura que devemos seguir.

Podemos alterar e criar um snnipet para adicionar um texto negrito.

```bash
{
"Text bold 300": {
    "prefix": "bold-300",
    "body": ["text-bold-300"],
    "description": "Log output to console"
  },
}
```

Antes de usarmos, é necessário “instalar” a extensão de forma local. Temos duas opções. Podemos buscar pelo ctrl shift p pelo nome dela ou jogar a nossa pasta dentro das extensões do vs code em `.vscode/extensions`

Feito isso, podemos salvar, reiniciar o vs code e já testarmos no código.

# Publicação

Para iniciarmos na publicação. execute o seguinte comando:

```bash
npm install -g @vscode/vsce
```

Enquanto instala, acesse a página para criação de [tokens](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows) e clique em abrir devops.

Caso não tenha uma organização, crie uma.

Para criar um novo token, acessse `Personal access token`

![Personal token](https://github.com/LeoGonzaga/design-system-vs-code-extension/blob/main/assets/personal_token.png)

Crie um novo token:

![Novo token](https://github.com/LeoGonzaga/design-system-vs-code-extension/blob/main/assets/new_token.png)
Preencha as informações seguindo o exemplo abaixo. Coloque o nome que quiser. O importatne é marcar o marketplace como `Manage`

![Criar novo token](https://github.com/LeoGonzaga/design-system-vs-code-extension/blob/main/assets/personal_token.png)

- Copie o token gerado.
- Agora, crie um [publisher](https://marketplace.visualstudio.com/manage/)

Voltando para o terminal:

```bash
vsce login <id do publisher>
```

Adicione o token quando solicitado.

Por fim, adicione o `"publisher": "nome-da-extensao"` em seu package json e edite o README. Com isso, basta executar:

```bash
vsce publish
```

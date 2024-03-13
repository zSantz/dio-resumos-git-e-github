# Resumo | Configurações Git

Aqui está um resumo das configurações iniciais que devem ser feitas no Git, abordando os seguintes tópicos:

- **Variáveis de Configuração**
- **Configuração de Nome e E-mail**
  - Nome e E-mail
  - Verificando Configurações
- **Configurando a Branch Padrão**
- **Visualizando as Configurações Feitas**
- **Autenticação**
  - Via Token
  - Via SSH

### 1️⃣ - Variáveis de Configuração

Existem variáveis de configuração no Git que limitam até onde vai a configuração. São elas: 

```bash
--system = Engloba todo o sistema
--global = Engloba apenas o usuário autenticado no momento
--local = As configurações serão feitas apenas no repositório atual
```

### 2️⃣ - Configurando Nome e E-mail do autor

#### Nome e E-mail 📧

Essas configurações de nome e e-mail permanecerão nos commits futuros. Se houver outros commits anteriores, os nomes e e-mails do usuário e autor do commit anterior não serão afetados pela mudança, apenas nos commits futuros.

```bash
git config --[option] user.name " " = Configura qual será o nome de usuário
git config --[option] user.email " " = Configura qual será o e-mail do usuário
```

> É uma boa prática colocarmos os usuários e e-mails referentes ao configurado no GitHub.

#### Verificando as configurações 🔍

Para verificar qual usuário está configurado no momento, utilize os seguintes comandos:

```bash
git config user.name = Para ver o usuário
git config user.email = Para ver o e-mail
```

### 3️⃣ - Configurando a Branch padrão

Em projetos antigos, o **GitHub** utilizava o nome **master** como padrão para suas Branchs principais. Hoje em dia, isso foi descontinuado, embora você ainda possa encontrar essas nomeações em projetos antigos. Atualmente, o nome padrão que o **GitHub** utiliza é **main**.

Para configurar, ou seja, alterar o nome da Branch padrão, a gente utiliza os comandos:

```bash
git config init.DefaultBranch main == Para alterar a branch padrão para main
git config init.DefaultBranch = Exibe a Branch Principal
```

### 4️⃣ - Visualizando as configurações feitas

Para visualizar, listar as configurações feitas no seu git é bem simples, basta utilizar o comando:

```bash
git config --[option] --list = Vai listar todas as configuração realizadas
```

### 5️⃣ - Autenticação

> É importante saber que o Git não depende de plataformas como o GitHub para fazer esse versionamento de código.

Antes, o processo de autenticação do GitHub para você armazenar um repositório era feito através do nome e da senha. Porém, isso foi alterado. Agora existem dois jeitos de se autenticar no GitHub, através do modelo:

#### Via Token 🔑

- Primeiro passo é criar o Token na página do GitHub. Para isso, siga este processo:

	- Clique na sua **foto de usuário** no canto superior direito;
	- Vá em **settings**, role até o final da tela e clique em **Developer Settings**;
	- Clique em **Personal access token**, depois em **Token Classic**;
	- Em seguida, clique em **Generate new token**, e depois em **Generate new token (classic)**;
	- Defina um **nome** para o token, o **tempo de validade** e as **permissões**, depois clique em **Gerar Token**;
	- Pronto, seu token está criado. **LEMBRE-SE, SE VOCÊ SAIR DA PÁGINA SEM COPIAR O TOKEN, VOCÊ NÃO VAI CONSEGUIR MAIS UTILIZÁ-LO**.

- Agora que o Token foi criado, vamos configurá-lo na nossa máquina:
	- Abra o **git bash**;
	- Digite o comando ``git clone [repositório.git]`` ;
	- Insira o seu nome de **usuário** do **GitHub**;
	- Agora, cole o **Token Gerado** e pronto, ele está configurado na sua máquina.

- Para salvar essas credenciais na nossa máquina, vamos executar os seguintes comandos:
	- Utilize o comando ``git config --[option] credential.helper cache`` para armazenar temporariamente as credenciais;
	- E o comando ``git config --[option] credential.helper store`` para armazenar permanentemente as credenciais.

---

#### Via SSH 🔑

SSH, abreviação de **Security Shell**, é um protocolo de rede que permite a comunicação segura entre seu computador **local** e um servidor **remoto**, utilizando criptografia na rede.

Este protocolo opera com um par de chaves, uma pública e outra privada. Ao se conectar através de uma chave SSH, você se autentica por meio da chave privada, que permanece em seu computador.

> A chave privada equivale a uma senha e não deve ser exposta. A chave que utilizaremos para nos conectar ao GitHub é a chave pública.

- O primeiro passo é verificar se já existe alguma chave SSH criada em nosso sistema, seguindo este tutorial da documentação do GitHub. [Mais](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)
    1. Abra o git bash.
    2. Digite `ls -al ~/.ssh` para verificar se existem chaves SSH presentes. Caso existam, por padrão, os nomes dos arquivos de chaves públicas compatíveis com o GitHub são:
        - id_rsa.pub
        - id_ecdsa.pub
        - id_ed25519.pub
    > Dica: se você receber um erro indicando que _~/.ssh_ não existe, você não terá um par de chaves SSH existente no local padrão. Você pode criar um novo par de chaves SSH na próxima etapa.
- Para gerar novas **chaves SSH**, siga este tutorial na documentação do GitHub. [Mais](https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
    1. Abra o Git Bash.
    2. Cole o texto abaixo, substituindo o e-mail usado no exemplo pelo seu endereço de e-mail do GitHub:
        - ```
          ssh-keygen -t ed25519 -C "seu_email@example.com" ```
          
        - `ssh-keygen` = Responsável por gerar nossas chaves.
        - `-t` = Parâmetro responsável por definir o algoritmo de criptografia.
        - `ed25519` = Algoritmo de criptografia.
        - `-C` = Parâmetro responsável por adicionar um comentário identificando a finalidade.
    3. Quando for solicitado um local para salvar a chave, pressione **Enter** para aceitar o local padrão do arquivo.
    4. Pronto, a chave foi gerada.
- Agora vamos adicionar a chave privada ao `ssh-agent` para armazená-la de forma segura:
    1. Inicie o `ssh-agent` com o comando:

        ```bash
        eval "$(ssh-agent -s)"
        ```
    2. Em seguida, adicione a chave privada ao `ssh-agent` com o comando:
        ```bash
        ssh-add ~/.ssh/id_ed25519
        ```
    3. Insira sua passphrase, se solicitado.
    4. Pronto, sua chave está armazenada com segurança em seu computador.
- Agora, vamos adicionar a chave pública ao GitHub, seguindo estes passos:
    1. Abra o site do GitHub, clique na sua foto de usuário no canto superior direito e selecione "Settings".
    2. Em "Settings", clique em "SSH and GPG Keys" e depois em "New SSH Keys".
    3. Escreva um título para sua chave, defina o tipo de chave como "autenticação" e cole a chave no campo "Keys".
    4. Pronto, sua chave está adicionada.

---
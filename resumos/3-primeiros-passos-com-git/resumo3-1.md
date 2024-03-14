## 2️⃣ - Salvando Alterações no Repositório Local

### Criando e Iniciando um Repositório Git** 🚀

Para criar e iniciar um repositório Git, você pode seguir estes passos:

1. **Criar um Diretório:** Primeiro, crie uma pasta onde deseja iniciar o seu repositório. Isso pode ser feito usando o comando `mkdir nome_da_pasta`. Por exemplo:
   ```bash
   mkdir meu_projeto
   ```

2. **Iniciar o Repositório Git:** Em seguida, dentro do diretório recém-criado, execute o comando `git init` para iniciar o repositório Git. Isso criará um repositório local na pasta especificada.
   ```bash
   cd meu_projeto
   git init
   ```

Ao usar o comando `git init`, você pode adicionar algumas variáveis úteis para personalizar o comportamento do Git de acordo com suas necessidades:

- **`--bare`:** Inicializa um repositório Git sem um diretório de trabalho, o que é útil para criar repositórios compartilhados em servidores.
- **`--initial-branch <nome>`:** Define o nome da branch inicial. Por padrão, o Git cria a branch principal com o nome `master`, mas você pode alterá-la para `main` ou outro nome de sua preferência.
- **`--template=<diretório>`:** Especifica um diretório que contém arquivos a serem copiados para o novo repositório. Isso pode ser útil para configurar modelos personalizados para novos projetos.

Por exemplo, para criar um repositório compartilhado sem um diretório de trabalho e com a branch inicial chamada `main`, você pode executar:
```bash
git init --bare --initial-branch main
```

Essas opções adicionais do comando `git init` oferecem flexibilidade para adaptar o seu fluxo de trabalho e a estrutura do repositório conforme necessário.

### Verificando o Estado com ``git status`` 📊

Após criar um repositório local e iniciar o Git, é crucial verificar o estado da árvore de trabalho e da área de preparação.

> A área de preparação é onde preparamos os arquivos para serem empacotados.

```bash
git status
```

Este comando permite verificar o estado dos arquivos, da árvore de trabalho e da área de preparação.

###  Adicionando Arquivos à Nossa Área de Preparação 📁

Depois de criar um arquivo dentro do repositório, é necessário adicioná-lo à área de preparação para que possa ser empacotado em um commit e enviado para o repositório remoto. Para isso, vamos utilizar o seguinte comando:

```bash
git add nome_do_arquivo 
```
ou
```bash
git add .
```

O primeiro comando adiciona um arquivo específico à área de preparação, enquanto o segundo adiciona todos os arquivos modificados ou novos.

### Salvando Alterações 💾

Todas as alterações que você faz e adiciona na área de preparação estão apenas esperando para serem salvas. Para salvar essas alterações, utiliza-se o comando:

```bash
git commit -m "mensagem"
```

Este comando cria um novo commit com uma mensagem descritiva que explica as alterações realizadas. É importante fornecer uma mensagem clara e concisa para documentar o motivo e o impacto das alterações feitas.

### Extra - Diretórios Vazios no Git 📁

Ao lidar com o Git, é importante entender que ele não consegue rastrear diretórios vazios. Isso significa que se um diretório não contiver nenhum arquivo, o Git o ignorará ao verificar as mudanças no repositório.

Para contornar essa limitação, podemos utilizar algumas estratégias:

1. **Adicionar um arquivo `.gitkeep`**: Dentro do diretório vazio, podemos incluir um arquivo chamado `.gitkeep`. Embora este arquivo possa estar vazio, ele permite que o Git rastreie o diretório. Funciona como um marcador de posição para indicar que o diretório deve ser mantido vazio intencionalmente.

2. **Adicionar arquivos relevantes ao projeto**: Outra abordagem é adicionar arquivos ao projeto dentro do diretório vazio. Isso pode incluir arquivos de configuração, documentação ou qualquer outro tipo de arquivo necessário para o projeto. Dessa forma, o diretório não estará mais vazio e será rastreado pelo Git.

Além disso, em projetos onde desejamos que o Git ignore determinados diretórios, podemos usar o arquivo `.gitignore`. Esse arquivo permite especificar padrões de arquivos e diretórios que o Git deve ignorar durante a indexação e o commit, proporcionando maior controle sobre o que é incluído no repositório.

<br>

____

Agora vamos avançar para a parte final, onde aprenderemos a desfazer alterações no repositório local e a enviar e baixar alterações para o repositório remoto. 🔄💻 [Clique aqui](resumo3-2.md) para continuar!
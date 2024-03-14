
# Primeiros Passos com Git e GitHub 🚀

Este resumo será dividido em três partes para uma melhor organização e compreensão. Aqui estão os tópicos abordados:

1. **Criando e Clonando Repositórios**
2. **Salvando Alterações no Repositório Local**
3. **Desfazendo as Alterações no Repositório Local**
4. **Enviando e Baixando Alterações no Repositório Remoto**
<br>
Vamos começar explorando cada parte para entender melhor como usar o Git e o GitHub em seu projeto!

## 1️⃣ - Criando e Clonando Repositórios

Existem duas formas de obter um repositório Git na sua máquina local:
1. Transformando um diretório local que não está sob controle de versão, num repositório Git;
2. Clonando um repositório Git existente. 

### 🏗️ Criando um Repositório Local


#### 🎬 Inicializando um Repositório Git

Para começar a usar o controle de versão do Git em um diretório local, basta usar o comando `git init`. Isso cria um repositório Git em sua máquina, controlando todas as alterações nos arquivos.

Depois de usar o git init, uma pasta oculta chamada .git será criada. Esta pasta gerencia todas as informações sobre as versões dos arquivos do projeto, incluindo as configurações definidas no arquivo config.

#### 💻 Vinculando o repositório Git local a um remoto

Para vincular um repositório local a um repositório remoto, utilizamos o comando:

```bash
git remote add origin <link repo remoto>
```

Para exibir os repositórios remotos vinculados ao nosso repositório local, usamos o comando:

```bash
git remote -v
```

### 📥 Clonando um repositório remoto

**Para clonar um repositório remoto na sua máquina, existem as seguintes maneiras.**

1. **Clonar um Repositório Padrão:**
```bash
git clone URL
```
Este comando clona o repositório remoto especificado na URL para o diretório local atual. Ele cria uma cópia completa do repositório, incluindo todos os branches e histórico de commits.

2. **Clonar para um Diretório Específico:**
```bash
git clone URL DIRETORIO
```
Este comando clona o repositório remoto especificado na URL para o diretório local especificado. É útil quando você deseja clonar um repositório em um diretório com um nome diferente do padrão.

3. **Clonar e Renomear o Diretório:**
```bash
git clone URL NOVO-NOME
```
Este comando clona o repositório remoto especificado na URL para o diretório local atual e o renomeia com o nome fornecido. É útil quando você deseja clonar um repositório e dar a ele um nome diferente do padrão.

4. **Clonar Apenas uma Branch Específica:**
```bash
git clone URL --branch NOME_BRANCH --single-branch
```
Este comando clona apenas a branch especificada do repositório remoto, reduzindo o tempo de clone e economizando espaço em disco, pois ignora os outros branches.

<br>

____

Agora, vamos avançar para a próxima parte e explorar como salvar suas alterações no repositório local, além de adicionar conteúdo novo. 💾✨ [Clique aqui](resumo3-1.md) para prosseguir!

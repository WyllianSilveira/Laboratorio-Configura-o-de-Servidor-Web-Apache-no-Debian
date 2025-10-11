# 🛠️ Laboratório – Configuração de Servidor Web Apache no Debian

## 📘 Descrição Geral

Este laboratório demonstra o processo completo de **instalação, configuração e validação do servidor web Apache** em um ambiente **Linux Debian**, executado em uma **máquina virtual (VM)** configurada no **Oracle VirtualBox**.  
O ambiente foi projetado para simular um **cenário real de infraestrutura**, permitindo compreender a **estrutura de diretórios do sistema**, o **gerenciamento de serviços** e a **edição de arquivos de configuração** do Apache.  

Durante o procedimento, foram registradas capturas de tela (prints) e incluídas explicações objetivas sobre os comandos utilizados em cada etapa, servindo como **referência técnica** para futuras configurações e padronização de ambientes web baseados em Linux.

---

## 🎯 Objetivo

Demonstrar o processo técnico de **implantação e administração do serviço Apache** em ambiente Debian virtualizado, abordando os seguintes pontos:  
- Instalação e habilitação do pacote `apache2` via linha de comando.  
- Configuração de **VirtualHosts** e diretórios de publicação.  
- Ajuste de **permissões e propriedades** dos diretórios do servidor.  
- Validação do serviço por meio de **testes locais e análise de logs**.  
- Aplicação de **boas práticas de segurança e organização** em servidores web Linux.  
<br><br>


# 🧾 DOCUMENTAÇÃO – CONFIGURAÇÃO DO SERVIDOR APACHE NO DEBIAN 
## 🔹 1 Instalando o Apache2

### Comando

```bash
apt-get install apache2
````
Explicação
Comando instala o servidor Apache2 no Debian, resolvendo dependências automaticamente e instalando pacotes como apache2-bin, apache2-data, entre outros.

📸 Imagem: 
![Instalação do Apache2](./imagens/instalacao-apache2.png)
<br><br>

## 🔹 2. Navegando pelo Diretório de Configuração do Apache2

### Comando

```bash
cd /etc/apache2/
ls
````

📸 Imagem:
![Diretório de configuração do Apache2](./imagens/diretorio-apache2.png)

## 🔧 Explorando o Diretório de Configuração do Apache2

Agora, ao executar o comando `cd /etc/apache2/`, você acessa o diretório de configuração principal do Apache2. O comando `ls` lista os arquivos e pastas importantes, como `apache2.conf`, `ports.conf`, e os 
diretórios `sites-enabled` e `mods-enabled`, que controlam a configuração dos sites e módulos ativos no servidor.
<br><br>

## 🔹 3. Visualizando o VirtualHost Padrão

### Comando

```bash
cd /etc/apache2/sites-available/
cat 000-default.conf | more
````

📸 Imagem:  
![Configuração padrão do Apache](./imagens/000-default-conf.png)

### Explicação

Neste passo, foi acessado o arquivo `000-default.conf`, responsável pela configuração do **VirtualHost padrão** do Apache na porta 80.

A diretiva `DocumentRoot` aponta para `/var/www/html`, indicando o diretório onde o site será hospedado. Esse caminho é utilizado para carregar o `index.html` padrão do Apache.

Outros pontos:

- **ServerAdmin**: define o e-mail do administrador.  
- **ErrorLog** e **CustomLog**: indicam os arquivos de log.

⚠️ Nenhuma alteração foi feita nesta configuração — já veio com o padrão definido.  
A única modificação foi no arquivo `index.html`, que será exibido no navegador.


## 🔹 4. Acessando os Logs do Servidor Apache

### Comando

```bash
cd /var/log/apache2/
ls
````

📸 Imagem:  
![Listando arquivos de log do Apache](./imagens/apache2-logs.png)

### Explicação

O diretório `/var/log/apache2/` armazena os principais arquivos de log gerados pelo Apache. Esses registros são fundamentais para o **diagnóstico de erros**, **análise de acesso** e **monitoramento** do funcionamento do servidor.

Os principais arquivos são:

- **access.log**: registra todas as requisições feitas ao servidor (IP, navegador, status HTTP, etc.).
- **error.log**: armazena mensagens de erro geradas pelo Apache.
- **other_vhosts_access.log**: acessos relacionados a outros VirtualHosts configurados.

# Analisando o Arquivo access.log

### Comando

```bash
cat access.log
````

##Explicação
Este comando exibe o conteúdo do arquivo access.log, onde cada linha representa uma requisição HTTP recebida.

📸 Imagem:  
![Verificando arquivos de log do Apache](./imagens/verificando_apache2-logs.png)

### Exemplo de linha registrada:
192.168.0.204 - - [21/Sep/2025:19:20:35 -0300] "GET / HTTP/1.1" 200 3383 ...

###Informações contidas:

IP do cliente

Data e hora do acesso

Método e rota acessada (GET /)

Código de status HTTP (ex: 200 = sucesso, 404 = não encontrado)

Agente de usuário (navegador e sistema operacional)

Esses dados permitem validar se o servidor respondeu corretamente às requisições e identificar erros comuns, como o 404 ao tentar carregar /favicon.ico.



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
<br.<br>

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




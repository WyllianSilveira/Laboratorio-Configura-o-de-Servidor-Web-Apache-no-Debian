# 🧰 Laboratório: Servidor Apache no Debian

Este repositório contém a documentação de um laboratório prático que demonstra a **instalação, configuração e validação do servidor web Apache** em um ambiente **Debian Linux**, utilizando **máquinas virtuais no VirtualBox** para simular um ambiente real de infraestrutura web.

---

## 🌐 Descrição do Ambiente

- O host é um **Windows 11**, conectado à internet via Wi-Fi.  
- O **servidor Debian** foi configurado com o serviço **Apache2**.  
- O acesso foi testado a partir de um **cliente Windows 10** via navegador.  
- Rede interna configurada: **192.168.0.0/24** (modo Bridge / Host-Only).  

---

## 🎯 Objetivos

- Instalar e habilitar o pacote **apache2** via linha de comando.  
- Configurar **VirtualHosts** e diretórios de publicação.  
- Ajustar **permissões e propriedades** de diretórios web.  
- Validar o serviço por meio de **testes locais e análise de logs**.  
- Aplicar **boas práticas de segurança e organização** em ambientes Linux.  

---

## 📦 Conteúdo do Repositório

- Capturas de tela do processo e comandos executados → **(/imagens)**  
- Arquivo HTML personalizado hospedado no Apache → **(index.html)**  
- Documentação detalhada do processo → **(Laboratório_Apache_Debian.md)**  

---

## 🧠 Resumo Técnico

O laboratório foi dividido em etapas que abordam:

1. **Instalação do Apache2**
   - Comando: `apt-get install apache2`  
   - Verificação do serviço com `systemctl status apache2`.

2. **Configuração e Estrutura de Diretórios**
   - `/etc/apache2/` → diretório principal de configuração.  
   - `/var/www/html/` → raiz padrão de hospedagem (DocumentRoot).  

3. **Validação do Serviço**
   - Teste de escuta de portas com `ss -tlnp`.  
   - Verificação de logs em `/var/log/apache2/access.log` e `error.log`.  

4. **Teste via Navegador**
   - Acesso via IP da VM Debian (`http://192.168.0.xxx`).  
   - Página `index.html` personalizada exibida corretamente no cliente Windows.



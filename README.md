# medusa-bruteforce-lab/
Laboratório de Brute Force com Kali Linux e Medusa  Objetivo. 
Este projeto tem como objetivo simular ataques de força bruta em um ambiente controlado utilizando o Kali Linux, a ferramenta Medusa e máquinas vulneráveis como o Metasploitable 2 e DVWA.

Ambiente Utilizado
Kali Linux (máquina atacante)
Metasploitable 2 (máquina vulnerável)
VirtualBox
Rede: Host-Only

Configuração do Ambiente
Criação de duas máquinas virtuais:
- Kali Linux
- Metasploitable 2
Configuração de rede:
Tipo: Host-only Adapter

Verificação do IP das máquinas:
- ifconfig

Descoberta de Serviços
Utilizei o Nmap para identificar serviços ativos:
nmap -sV 172.31.45.1

Serviços encontrados:
FTP (porta 21)
SMB (porta 445)
HTTP (porta 80)

Ataque de Força Bruta (FTP)
Comando utilizado:
medusa -h 172.31.45.1 -u msfadmin -P wordlists/passwords.txt -M ftp
Resultado:
Acesso obtido com credenciais válidas.

Ataque em Aplicação Web (DVWA)
Passos:
Acessei DVWA via navegador:
http://172.31.45.1/dvwa
Configurei nível de segurança para "low"
Testei login com automação de tentativas

Password Spraying (SMB)
Comando:
medusa -h 172.31.45.1 -U users.txt -p 123456 -M smbnt
Objetivo:
Testar uma senha comum para múltiplos usuários.

Wordlist utilizada
123456
password
admin
msfadmin
12345

Medidas de Mitigação
- Uso de senhas fortes e complexas
- Implementação de MFA (autenticação multifator)
- Bloqueio após múltiplas tentativas de login
- Monitoramento de logs
- Uso de CAPTCHA em aplicações web

Aprendizados
Funcionamento de ataques de força bruta
Uso da ferramenta Medusa
Importância de boas práticas de segurança
Identificação de vulnerabilidades reais

Autor
Leonardo Ramos

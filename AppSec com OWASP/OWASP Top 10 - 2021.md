# OWASP Top 10 - 2021

### A01:2021 – Broken Access Control

O controle de acesso (ou autorização) é a aplicação de restrições sobre quem (ou o que) pode realizar tentativas de ações ou acessar recursos solicitados, ou seja tem a função de conceder o nível apropriado de acesso a pessoas e processos autorizados e negar o acesso a funções ou indivíduos não autorizados. 

Mais Informação:
[Controles de acesso](https://github.com/brunoesm07/Cybersecurity_notes_and_summaries/blob/main/Certifica%C3%A7%C3%B5es_em_Cybersecurity/CERTIFIED%20IN%20CYBERSECURITY%20(CC)%20-%20(ISC)%C2%B2/Cap%C3%ADtulo%203%20Controle%20de%20acesso.md)

O *Broken Access Control* ocorre quando uma falha no controle de acesso permite que usuários acessem recursos ou realizem ações fora de suas permissões. Portanto, se um usuário não autenticado puder acessar qualquer uma das páginas, isso é uma falha. Se um não administrador puder acessar a página de administração, isso também é uma falha.

Exemplos de quebra de controles de acesso:

**Escalação de privilégios** -> um usuário obtem acesso a uma funcionalidade que não tem permissão para acessar. Algumas formas de obter esse acesso são:
- Inserindo-se *robots.txt* ao final da url que revelará o caminho para o painel de administração.
````
https://insecure-website.com/robots.txt
````
- Buscando em um script através das ferramentas do desenvolvedor no navegador (URL imprevisivel)
````
<script> 
var isAdmin = false; 
if (isAdmin) { 
	...
	var adminPanelTag = document.createElement('a');
	adminPanelTag.setAttribute('https://insecure-website.com/administrator-panel-yb556');
	adminPanelTag.innerText = 'Admin panel'; 
	... 
} 
</script>
````
- Obtendo acesso através de modificação de parâmetros de solicitação
 
##### Prevenção

- Implementar controles de acesso no código do lado do servidor
- Utilizar a regra "negar por padrão"
- Reutilizar os mecanismos de controle de acesso em toda a aplicação
- Definir regras de negócio únicas aplicadas ao domínio
- Desabilitar a lista de diretórios do servidor web

Fonte:
[A01:2021-Broken Access Control](https://owasp.org/Top10/A01_2021-Broken_Access_Control/)
[Access control vulnerabilities and privilege escalation](https://portswigger.net/web-security/access-control)

### A02:2021 – Cryptographic Failures

### A03:2021 – Injection

### A04:2021 - Insecure Design

O design inseguro capta o fato de que precisamos começar a planejar a segurança no início da construção de nosso aplicativo. Não importa o quão bem você implemente um controle de segurança, se não tivermos tempo para examinar nosso aplicativo, projetá-lo bem e escolher os controles de segurança adequados para implementar nos lugares certos, o invasor terá portas abertas para contornar o controles de segurança que usamos.

Essa ameaça é uma grande porta que permite ao invasor explorar as outras ameaças.

A modelagem de ameaças é muito importante quando estamos pensando em desenvolver um aplicativo seguro porque é quando nos sentamos e olhamos para nosso aplicativo, como todos os dados fluem, como todos os componentes funcionam.

### A05:2021 - Security Misconfiguration

A configuração incorreta de segurança é quando alguém comete um erro ou perde alguma coisa. Estamos implantando um aplicativo e esquecemos de fazer algo para bloqueá-lo de uma maneira melhor.

Para uma configuração incorreta de segurança, o risco é que haja uma exposição de dados. Se não bloquearmos o aplicativo corretamente, um invasor poderá acessar nossos dados.

### A06:201 - Vulnerable and Outdated Components

Componentes desatualizados capturam os problemas que temos com a cadeia de suprimentos de software. Os componentes e coisas que incluímos em nosso aplicativo trazem vulnerabilidades.

### A07:2021 - Identification and Authentication Failures 




  

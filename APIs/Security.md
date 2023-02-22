SOP -> protocolo que se destina a fornecer segurança para APIs

# CSP

[CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) é um protocolo que pode ser usado para fornecer um nível adicional de segurança sobre vários problemas, como [XSS](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting) , injeção de dados etc.

# CORS

[CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) ou Cross-Origin Resource Sharing é um mecanismo baseado nos cabeçalhos HTTP que permitem ao servidor responder de quais origens o servidor pode aceitar. O servidor pode aceitar a solicitação se ela estiver sendo feita da mesma origem que o servidor, mas pode rejeitar solicitações de outras origens ou domínios por meio [da política de mesma origem](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy) .

## Política de Mesma Origem

[A política de mesma origem](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy) é um mecanismo de segurança que limita a capacidade de um documento de uma origem interagir com os recursos presentes em uma origem diferente. Essa medida de segurança foi tomada para garantir que os dados de um domínio não possam ser roubados de outro.

Também deve ser observado que qualquer domínio pode solicitar um recurso de outro domínio, mas não pode acessar a resposta, a menos que a resposta use o cabeçalho CORS correto.


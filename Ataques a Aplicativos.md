# Ataques conhecidos e direcionados a aplicativos web

## XSS

O Cross-site scripting (XSS) é uma vulnerabilidade encontrada nos aplicativos da Web, que permite que os criminosos injetem scripts com código malicioso em páginas da Web confiáveis. 

Um invasor pode usar XSS para enviar um script malicioso a um usuário desavisado. O navegador do usuário final não tem como saber que o script não é confiável e executará o script. Como acredita que o script veio de uma fonte confiável, o script malicioso pode acessar quaisquer cookies, tokens de sessão ou outras informações confidenciais retidas pelo navegador e usadas com esse site. 

O conteúdo malicioso enviado ao navegador da Web geralmente assume a forma de um segmento de JavaScript, mas também pode incluir HTML, Flash ou qualquer outro tipo de código que o navegador possa executar. A variedade de ataques baseados em XSS é quase ilimitada, mas geralmente incluem a transmissão de dados privados, como cookies ou outras informações de sessão, para o invasor, redirecionando a vítima para o conteúdo da Web controlado pelo invasor ou realizando outras operações maliciosas na máquina do usuário sob o disfarce do site vulnerável.

[Types of Cross-Site Scripting](https://owasp.org/www-community/Types_of_Cross-Site_Scripting)

## Injeção de código

**Injeção de XML** 

Depois que o usuário dá a entrada, o sistema acessa os dados necessários através de uma consulta. O problema ocorre quando o sistema não examina corretamente a solicitação de entrada fornecida pelo usuário e assim, os criminosos podem manipular a consulta, programando para atender às suas necessidades e acessar as informações no banco de dados.

**Injeção de SQL**

Uma vulnerabilidade é explorada inserindo uma instrução SQL mal-intencionada em um campo de entrada. Mais uma vez, o sistema não filtra a entrada do usuário corretamente para os caracteres em uma instrução SQL. 

## Buffer Overflow

Um buffer overflow ocorre quando os dados ultrapassam os limites de um buffer. Ao alterar os dados além dos limites, o aplicativo acessa a memória alocada a outros processos. A gravação fora dos limites de um bloco de memória alocada pode corromper dados, travar o programa ou causar a execução de código malicioso.

No nível do código, as vulnerabilidades de estouro de buffer geralmente envolvem a violação das suposições de um programador.

O que é buffer?

Os buffers são áreas de memórias alocadas a um aplicativo. 
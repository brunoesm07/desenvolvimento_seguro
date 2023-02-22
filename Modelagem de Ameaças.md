Descubra quem são seus "inimigos".
O que os motiva? Quais seus objetivos?
Conheça bem o seu próprio sistema.
Crie camadas de proteção.
Mitigue os riscos.

# Visão Geral

A modelagem de ameaças funciona para identificar, comunicar e entender ameaças e mitigações no contexto de proteger algo de valor.  Ela analisa um sistema na perspectiva de um invasor em potencial, em oposição ao ponto de vista de um defensor.

Um modelo de ameaça é uma representação estruturada de todas as informações que afetam a segurança de um aplicativo. Em essência, é uma visão do aplicativo e seu ambiente pelas lentes da segurança.

Um modelo de ameaça geralmente inclui:

-   Descrição do assunto a ser modelado
-   Suposições que podem ser verificadas ou contestadas no futuro conforme o cenário de ameaças muda
-   Ameaças potenciais ao sistema
-   Ações que podem ser tomadas para mitigar cada ameaça
-   Uma forma de validação do modelo e ameaças, e verificação do sucesso das ações tomadas

O processo de modelagem de ameaças pode ser decomposto em três etapas:

1. Decompor o aplicativo
2. Determinar e Classificar as Ameaças
3. Determinar contramedidas e mitigação

## Modelagem de ameaças em todo o ciclo de vida

A modelagem de ameaças é melhor **aplicada continuamente** ao longo de um projeto de desenvolvimento de software. O processo é essencialmente o mesmo em diferentes níveis de abstração, embora as informações fiquem cada vez mais granulares ao longo do ciclo de vida. Idealmente, um modelo de ameaça de alto nível deve ser definido no início do conceito ou fase de planejamento e, em seguida, refinado ao longo do ciclo de vida. À medida que mais detalhes são adicionados ao sistema, novos vetores de ataque são criados e expostos. O processo contínuo de modelagem de ameaças deve examinar, diagnosticar e abordar essas ameaças.

A atualização dos modelos de ameaças é aconselhável após eventos como:

-   Um novo recurso é lançado
-   Ocorre um incidente de segurança
-   Mudanças arquitetônicas ou de infraestrutura

A estrutura de quatro perguntas a seguir pode ajudar a organizar a modelagem de ameaças:

-   Em que estamos trabalhando? => **Avalie o escopo** - Isso pode ser tão pequeno quanto um sprint ou tão grande quanto um sistema inteiro.
-   O que pode dar errado? => **Identifique o que pode dar errado** - Isso pode ser tão simples quanto um brainstorm ou tão estruturado quanto usar STRIDE, Kill Chains ou Attack Trees.
-   O que você irá fazer sobre isso? => **Identifique contramedidas ou gerencie riscos** - Decida o que você fará com cada ameaça. Isso pode ser para implementar uma mitigação ou aplicar as abordagens aceitar/transferir/eliminar do gerenciamento de riscos.
-   Fizemos um bom trabalho? => **Avalie seu trabalho** - Você fez um trabalho bom o suficiente para o sistema em questão?




## Links

Processo de Modelagem de Ameaças (OWASP) (https://owasp.org/www-community/Threat_Modeling_Process)
Modelagem de ameaças da Microsoft (https://www.microsoft.com/en-us/securityengineering/sdl/threatmodeling)

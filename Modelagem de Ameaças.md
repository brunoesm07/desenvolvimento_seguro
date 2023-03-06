# Introdução

## Objetivos

Descubra quem são seus "inimigos".
O que os motiva? Quais seus objetivos?
Conheça bem o seu próprio sistema.
Crie camadas de proteção.
Mitigue os riscos.

Corrigir um problema de segurança **depois** que o produto está desenvolvido e em produção pode **custar centenas de vezes mais** que prevenir ele em sua concepção.

## Visão Geral

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


# Decompor o aplicativo

Existem muitas vulnerabilidades e ameaças possíveis e é improvável que seu aplicativo encontre todos eles. Também é improvável que sua empresa precise abordar todos eles. A modelagem de ameaças ajuda a identificar onde sua equipe precisa concentrar esforços.

Todos os desenvolvedores, designers de software e arquitetos devem se esforçar para incluir a modelagem de ameaças em seu ciclo de vida de desenvolvimento de software. **Mas em um primeiro momento concentre-se no que você está trabalhando.**

Eu utilizarei para estudo prático um aplicativo Fintech, voltado para usuários que desejam planejar de forma flexível seus orçamentos e gerenciar o dia a dia de suas finanças, que estou desenvolvendo academicamente.

Dito isso, é importante que se decomponha todo o sistema e faça perguntas para que se encontre onde as vulnerabilidades se encontram. A primeira etapa no processo de modelagem de ameaças se preocupa em entender o aplicativo e como ele interage com entidades externas.

### Identifique o design do aplicativo

Entender o design do aplicativo é fundamental para realizar a modelagem de ameaças. Se você estiver muito familiarizado com o design do aplicativo, poderá identificar fluxos de dados adicionais e limites de confiança em todo o processo de modelagem de ameaças.

-  Identifique os casos de uso, defina os pontos de entrada do aplicativo e os níveis de confiança, mesmo que permaneçam inalterados como resultado do projeto.
-  Identifique atores, ativos, serviços, funções e fontes de dados.
-  Documente a movimentação de dados (em movimento e em repouso) via Diagrama de Fluxo de Dados. 
-  Documente todos os dados trocados e sua classificação.

Uma compreensão completa de como o sistema foi projetado também o ajudará a avaliar a probabilidade e o impacto potencial de qualquer ameaça específica que você identificar.

## Decomponha e modele o aplicativo

Precisamos tomar nota do processo para que em um eventual momento se possa consultar o que foi feito.  Baseado no Processo de Modelagem de Ameaças da OWASP, iniciamos a documentação com a etapa 1 - decompondo o aplicativo, conforme segue abaixo:

## Informações de identificação

1.  **Nome do Sistema** : O nome do aplicativo examinado.
2.  **Versão do aplicativo** : a versão do aplicativo examinado.
3.  **Descrição** : Uma descrição de alto nível do aplicativo.
4.  **Proprietário do documento** : o proprietário do documento de modelagem de ameaças.
5.  **Participantes** : os participantes envolvidos no processo de modelagem de ameaças para este aplicativo.
6.  **Revisor** : O(s) revisor(es) do modelo de ameaça.

Exemplo prático:

1. Nome: ContabiLivre
2. Versão: v0.1
3. Descrição: Aplicativo web de planejamento financeiro pessoal, capacitado com sincronização de saldo bancário e despesas de cartão de crédito.
4. Proprietário do documento: Bruno Martins

Os ítens 4 e 5 não foram preenchidos pois pratiquei sozinho e não tive a oportunidade de ter um revisor. Porém são dois ítens de extrema importância para uma boa elaboração do modelo de ameaças.

## Dependências externas

Dependências externas são itens externos ao código do aplicativo que podem representar uma ameaça ao aplicativo.

As dependências externas devem ser documentadas da seguinte forma:

1.  **ID** : um ID exclusivo atribuído à dependência externa.
2.  **Descrição** : uma descrição textual da dependência externa.

Exemplo prático:
| ID | Descrição |
| ----- | ----- |
| 1 | Tela de login do usuário através de um browser onde autenticará seus dados para acesso |
| 2 | Acesso ao banco de dados com informações do perfil
| 3 | API de conexão com saldo bancário |
| 4 | API de conexão com cartão de crédito |

## Pontos de entrada

Os pontos de entrada definem as interfaces por meio das quais invasores em potencial podem interagir com o aplicativo ou fornecer dados a ele.

Os pontos de entrada devem ser documentados da seguinte forma:

1.  **ID** : Um ID exclusivo atribuído ao ponto de entrada. Isso será usado para fazer referência cruzada do ponto de entrada com quaisquer ameaças ou vulnerabilidades identificadas. No caso de pontos de entrada em camadas, uma notação maior.menor deve ser usada.
2.  **Nome** : um nome descritivo que identifica o ponto de entrada e sua finalidade.
3.  **Descrição** : Uma descrição textual detalhando a interação ou processamento que ocorre no ponto de entrada.
4.  **Níveis de confiança** : o nível de acesso necessário no ponto de entrada. Eles serão cruzados com os níveis de confiança definidos posteriormente no documento.

Exemplo prático:
| ID | Nome | Descrição | Nivel de Confiança |
| ----- | ----- | ----- | ----- |
| 1 | Login | Tela de acesso ao perfil do usuário. | Request HTTP |
| 2 | Acesso ao Banco de Dados | Armazenamento de dados dos usuários | O time de desenvolvimento tem credenciais de acesso |
| 3 | Utilização do App | Manuseio e utilização das informações contidas no aplicativo | Qualquer pessoa que tiver acesso ao telefone da pessoa pode mexer no app. |

## Pontos de saída

Em muitos casos, as ameaças habilitadas pelos pontos de saída estão relacionadas às ameaças do ponto de entrada correspondente. Muitas vezes poderá, inclusive, ter múltiplas saídas, uma vez que a interação com o ponto de entrada pode mudar.

Exemplo prático:
| ID Entrada | Ponto de Saída |
| ----- | ----- |
| 1 | Response HTTP |
| 2 | O acesso é somente leitura, a única pessoa que faz alterações no banco é quem cuida dos bancos de dados.
| 3 | Caso faça login, o app receberá o token de sessão e armazenará ele. |

Se você já tiver o código do aplicativo e tiver conhecimento técnico total sobre o funcionamento do mesmo, também poderá indicar os pontos de entrada e sáida conforme abaixo:

```
ID Entrada: 1
Descrição Entrada:
GET /usuario/$ID_USUARIO/perfil-usuário HTTP/1.1
Host: contabilivre.com.br

Authorization: $TOKEN_DE_SESSAO

Descrição Saída:
    HTTP/1.1 200 OK
    Content-Type: text/html

    $HTML_PERFIL_USUARIO
```

## Ativos

O sistema deve ter algo que interesse ao invasor e esses itens ou áreas de interesse são definidos como ativos. Os ativos são essencialmente os alvos dos invasores, ou seja, são a razão pela qual as ameaças existirão.

Os ativos envolvidos no fluxo de informações devem ser definidos e avaliados quanto ao seu valor de confidencialidade, integridade e disponibilidade.

Os ativos são documentados no modelo de ameaça da seguinte forma:

1.  **ID** : Um ID exclusivo é atribuído para identificar cada ativo. Isso será usado para fazer referência cruzada do ativo com quaisquer ameaças ou vulnerabilidades identificadas.
2.  **Nome** : um nome descritivo que identifica claramente o ativo.
3.  **Descrição** : uma descrição textual do que é o recurso e por que ele precisa ser protegido.
4.  **Níveis de confiança** : o nível de acesso necessário para acessar o ponto de entrada é documentado aqui. Eles serão cruzados com os níveis de confiança definidos na próxima etapa.

### Considere dados em trânsito e dados em repouso

Embora os dados em repouso às vezes sejam considerados menos vulneráveis ​​do que os dados em trânsito, os invasores geralmente consideram os dados em repouso um alvo mais valioso do que os dados em movimento. 

Proteger dados confidenciais em trânsito e em repouso é fundamental para as empresas modernas, pois os invasores encontram maneiras cada vez mais inovadoras de comprometer os sistemas e roubar dados.

## Níveis de confiança

Os níveis de confiança representam os direitos de acesso que o aplicativo concederá a entidades externas.

Os níveis de confiança são documentados no modelo de ameaça da seguinte forma:

1.  **ID** : Um número exclusivo é atribuído a cada nível de confiança. Isso é usado para fazer referência cruzada do nível de confiança com os pontos de entrada e ativos.
2.  **Nome** : um nome descritivo que permite identificar as entidades externas que receberam esse nível de confiança.
3.  **Descrição** : Uma descrição textual do nível de confiança detalhando a entidade externa que recebeu o nível de confiança.

Exemplo:
| ID | Nome | Descrição|
| ----- | ----- | ----- |
| 1 | Usuário | Proprietário do perfil logado |
| 2 | Credenciais de Acesso ao Banco de Dados | Usuário e senha compartilhado com o time de desenvolvimento para acesso ao banco, possui permissão de leitura e escrita.|
| 3 | Desenvolvedores(as) | Equipe técnica com acesso ao ambiente para modificar ou corrigir o sistema.
| 4 | Acesso SSH ao servidor | Precisamos rever como é esse acesso. Mas sabemos que o sistema de versionamento o usa para publicar o sistema. |

## Diagramas de fluxo de dados

Todas as informações coletadas nos permitem modelar com precisão o aplicativo por meio do uso de Diagramas de Fluxo de Dados ( DFDs ). Os DFDs nos permitirão entender melhor o aplicativo, fornecendo uma representação visual de como o aplicativo processa os dados.

![imagem](https://github.com/brunoesm07/desenvolvimento_seguro/blob/552f89a7cdb2af3b9b160432992b22d6e806c48b/assets/Diagrama%20de%20fluxo%20de%20dados.png)

A quantidade de informações a serem incluídas no diagrama de fluxo de dados depende de alguns fatores-chave:

- Tipo de sistema que você está construindo - Os sistemas que não lidam com dados confidenciais ou são usados apenas internamente podem não precisar de tanto contexto quanto um sistema externo.
- Contexto necessário de sua equipe de segurança - As equipes de segurança são precisas com o que procuram nos modelos de ameaças. Fale com sua equipe de segurança para confirmar a camada de profundidade necessária.


### Referências:

- Threat Modeling Process OWASP
- Curso de Modelagem de ameaças: identifique riscos na concepção do software - Alura
- O papel do dev no processo de modelagem de ameaças | Izabela Matos - AppSec to Go
- Curso Learning Threat Modeling for Security Professionals - LinkedIn Learning
- Threat Modeling in 2021 with Adam Shostack - DevSecCon (Youtube)






Determinar e classificar ameaças

- A segunda questão na modelagem de ameaças é o que pode dar errado?






# Terminologias Utilizadas em Modelagem de Ameaças

Em modelagem de ameaças utilizam-se algumas terminologias que podem não ser familiares para alguns profissionais, principalmente em início de carreira. Por isso achei útil compartilhar o guia abaixo:  

- **Ameaça** - Uma pessoa ou coisa que toma medidas para explorar (ou fazer uso de) as vulnerabilidades do sistema de uma organização-alvo, como parte de atingir ou promover sua meta ou objetivos.
- **Atacante**: quem realizou o ataque. Neste caso, o criminoso que invadiu o sistema e roubou os dados.
- **Ataque** - Pode ser real ou hipotético, com base em possíveis ações ou ataques tentados por um cibercriminoso, como um ataque à rede da sua empresa. 
- **Ativo** - Coisas importantes para você, informações confidenciais. Por exemplo, dados PCI ou PII. Um ativo é algo que precisa de proteção.
- **Biblioteca de conteúdo** - Uma base de conhecimento de padrões de risco, onde cada padrão consiste em um grupo lógico de ameaças de segurança, pontos fracos e contramedidas.
- **Contramedidas** - Ações que podem ser implementadas para mitigar o impacto ou a probabilidade de uma ameaça.
- **Controles** - São salvaguardas ou contramedidas que você implementa para evitar, detectar, neutralizar ou minimizar possíveis ameaças contra suas informações, sistemas ou outros ativos.
- **Componentes** - Partes que compõem a representação como uma instância do EC2 ou uma API ou ainda uma função dentro de uma aplicação web. Os componentes podem ser aninhados uns nos outros.
- **Exploit**: conjunto de técnicas e tecnologia que explora uma vulnerabilidade.
- **Fluxos de dados** - Como as informações e os ativos se movem entre os componentes.
- **Insider:** Alguém interno que pode colaborar com o atacante para vazar informações ou comprometer a empresa.
- **Impacto** - É uma medida do dano potencial causado por uma ameaça específica. Dependendo do negócio em que você atua, os ataques que expõem as informações do usuário podem resultar em uma ameaça física de dano ou perda de vida para seus usuários, aumentando consideravelmente o impacto das ameaças que permitiriam tal exposição.
- **Metadados do projeto** - nome, identificador, descrição, proprietário da coisa que você está modelando como ameaça.
- **Mitigações** - São controles implementados para reduzir a probabilidade ou o impacto de uma ameaça, embora não necessariamente a impeçam completamente.
- **Modelo -** Os modelos podem ser criados do zero ou gerados a partir de projetos pré-existentes para agilizar a criação de futuros modelos de ameaças. Os modelos costumam ser usados ​​para fornecer o esqueleto de um modelo de ameaça para dar aos colegas uma vantagem inicial na análise do diagrama.
- **Padrões** - Cada setor e país tem seus próprios padrões a serem seguidos ou considerados, desde saúde e finanças até organizações governamentais, como por exemplo o RGPD. 
- **Pontuação de risco** - Uma métrica para avaliar o nível de risco do seu negócio.
- **Probabilidade** - É uma medida da possibilidade de uma ameaça ser realizada. Uma variedade de fatores pode impactar a probabilidade de uma ameaça ser executada, incluindo quão difícil é a implementação da ameaça e quão gratificante seria para o invasor.
- **RBAC/Role Based Access Controls** - Um meio de restringir o acesso a usuários com base em suas funções, como Admin.
- **Representações** - Uma perspectiva sobre o que está sendo modelado como ameaça, por exemplo, diagrama de arquitetura, diagrama de fluxo de dados, código-fonte, JIRA, interface do usuário.
- **Relatórios** - Periodicamente, ao longo do ciclo de vida de um projeto, as equipes podem querer gerar relatórios executivos para capacitar internamente e fornecer às partes interessadas as informações de que precisam. Eles podem ser gerados para vários casos de uso, como um resumo de conformidade ou um relatório detalhado de todas as contramedidas identificadas
- **Risco** - Riscos são a combinação de uma ameaça e uma vulnerabilidade. Da-se o nome de risco a potencial perda, dano ou destruição de qualquer coisa que seja valiosa para a empresa, como um sistema, reputação, etc.
- **Trust Zone** - Os diferentes níveis de segurança e confiança. Internet x Web x App x Camada de dados.
- **Unidade de negócios** - Um grupo de usuários e produtos dentro do sistema. Com permissões básicas, os usuários têm acesso apenas aos Produtos que estão em sua Unidade de Negócios e limitados à função que lhes foi atribuída.
- **Versionamento** - O versionamento consiste em estratégias para gerenciar as diferentes versões de um código, de um sistema ou de um modelo. É uma forma de administrar as mudanças que são feitas e de garantir mais segurança na transição de uma versão para outra.
-   **Vulnerabilidade** - uma fraqueza ou brecha em um de nossos sistemas que pode ser explorado por um atacante e causar danos.




###  Links

- Threat Modeling Manifesto (https://www.threatmodelingmanifesto.org/)
- Processo de Modelagem de Ameaças (OWASP) (https://owasp.org/www-community/Threat_Modeling_Process)
- Modelagem de ameaças da Microsoft (https://www.microsoft.com/en-us/securityengineering/sdl/threatmodeling)

**Ferramentas para Modelagem de Ameaças**

- Cairis (https://cairis.org/cairis/tmdocsmore/)
- IriusRisk (https://www.iriusrisk.com/threat-modeling-platform)
- Threat Dragon OWASP (https://owasp.org/www-project-threat-dragon/#:~:text=What%20is%20Threat%20Dragon%3F,of%20the%20threat%20modeling%20manifesto.)

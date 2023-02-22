# Introdução às WEB APIs 

As APIs são os blocos de construção do software moderno porque permitem o compartilhamento de recursos e serviços entre aplicativos, organizações e dispositivos. Uma API é um conjunto de diretrizes ou regras que indicam como os aplicativos interagem. Uma API permite que um aplicativo solicite dados de outro sistema.

Você pode pensar nas APIs como sendo um garçom em um restaurante, servindo como um intermediário entre o cliente e a cozinha.

Um cliente que quer sopa não vai para a cozinha cozinhar. Eles nem precisam saber fazer sopa! Eles só precisam saber _como pedir_ sopa ao _garçom_ _e_ esperar que o garçom traga a sopa de volta _._ As APIs funcionam da mesma forma, mas há nomes diferentes para os jogadores envolvidos. Em vez de sopa, o solicitante pode solicitar dados ou execução de um serviço.

-   Cliente = **Cliente** (solicitante. Ex: navegador, aplicativo web, aplicativo móvel) 
-   Garçom = **API** (interface simplificada para interagir com o back-end)  
-   Cozinha = **Servidor** (back-end onde o processamento acontece)

### Anatomia de uma solicitação de API

| Nome | Descrição |
| ------ | ------|
| Endpoint | A URL que você solicita |
| Método | O tipo do pedido (GET, POST, DELETE, etc) |
| Cabeçalho | Informações adicionais para o cliente ou o servidor |
| Corpo | Informações enviadas ao servidor |

## Acessibilidade

As APIs variam no escopo de quem pode acessá-las.  

- APIs **públicas** (também conhecidas como APIs abertas) - consumíveis por qualquer pessoa que saiba sobre a API
- APIS **privadas** - consumíveis apenas dentro de uma organização e não tornadas públicas.
- APIs de parceiros - consumíveis entre uma ou mais organizações que possuem um relacionamento estabelecido.

## Arquiteturas

Há mais de uma maneira de criar e consumir APIs. Alguns tipos de arquitetura que você pode encontrar são:

-   REST (Transferência de Estado Representacional)
-   GraphQLGenericName
-   WebSockets
-   webhooks
-   SOAP (Simple Object Access Protocol)
-   gRPC (chamada de procedimento remoto do Google)
-   MQTT (Transporte de Telemetria MQ)

### APIs REST

As APIs REST se comunicam por meio de solicitações HTTP para executar operações CRUD (ou criar, ler, atualizar e excluir). Algumas características das APIs REST incluem não armazenar o estado da sessão entre as solicitações, a capacidade de armazenar em cache e a capacidade de enviar e receber vários tipos de dados.

APIs REST seguem [seis princípios](../APIs_REST) de design que são os seguintes:

1. Separação cliente-servidor
2. Stateless
3. Armazenável em cache
4. Sistema em Camadas
5. Interface uniforme
6. Code on Demand (opcional)

## Métodos HTTP

O HTTP possui um número fixo de métodos que o cliente pode usar para indicar que tipo de operação deseja realizar por meio da solicitação. Esses métodos de solicitação também são conhecidos como verbos HTTP.

1.  GET - A solicitação **GET** é usada para solicitar dados de um servidor. - **Read**
2.  POST - A solicitação **POST** é usada para enviar alguns dados para o servidor. - **Create**
3.  DELETE - A solicitação **DELETE** é usada para excluir o recurso especificado. - **Delete**
4.  PATCH - é usado para modificar parcialmente um recurso. - **Update**
5.  PUT - é usado para atualizar todo o recurso no servidor. - **Update**
6.  HEAD
7.  TRACE
8.  CONNECT
9.  OPTIONS

GET, POST, PATCH, PUT e DELETE são os mais populares.

## Parâmetros de Consulta

Os ingredientes mínimos que você precisa para fazer um pedido são:

-   um método de solicitação ( `GET`/ `POST`/ `PUT`/ `PATCH`/ `DELETE`, etc)
-   um URL de solicitação

Os parâmetros de consulta são adicionados ao final do caminho. Eles começam com um ponto de interrogação `?`, seguido pelos pares de chave-valor no formato: `<key>=<value>`. Por exemplo, esta solicitação abaixo pode buscar todas as fotos com orientação paisagem:

``GET https://some-api.com/photos?orientation=landscape``

Se houver vários parâmetros de consulta, cada um será separado por um e comercial `&`. Abaixo, dois parâmetros de consulta para especificar a orientação e o tamanho das fotos a serem retornadas:

`GET https://some-api.com/photos?orientation=landscape&size=500x400`

Às vezes, os parâmetros de consulta são opcionais e permitem adicionar filtros ou dados extras às suas respostas. Às vezes, eles são necessários para que o servidor processe sua solicitação. 

## Parâmetros de Caminho

Um parâmetro de caminho (ou "variável de caminho") é uma seção dinâmica de um caminho e geralmente é usado para IDs e nomes de entidade, como nomes de usuário.

Os parâmetros do caminho vêm imediatamente após uma barra no caminho. Por exemplo, a [API do GitHub](https://docs.github.com/en/rest/reference/users#get-a-user) permite pesquisar usuários do GitHub fornecendo um nome de usuário no caminho `{username}`, conforme vemos abaixo: 

`GET https://api.github.com/users/bruno `

_* Estas são apenas convenções! Algumas APIs podem solicitar que você passe um ID ou nome de usuário em um parâmetro de consulta como este:_ `/users?username=bruno`

## Autorização

Algumas APIs exigem **autorização** (também conhecida como **Auth** ) para determinado endpoint para permitir uma solicitação.

Existem vários métodos para autorizar uma solicitação. Alguns exemplos são **Basic Auth** (nome de usuário e senha), **OAuth** (autorização sem senha) e **API Keys** (strings secretas registradas para um desenvolvedor a partir de uma API).

As APIs que usam autenticação de chave de API (API Keys) geralmente permitem que os desenvolvedores se inscrevam em um portal de desenvolvedor, onde receberão uma chave de API aleatória que pode ser usada para autorizar suas solicitações para a API. A API Key permite que a API rastreie quem está fazendo chamadas e com que frequência.

## Códigos de Status

Quando o servidor retorna uma resposta, um número de três dígitos também é enviado como parte da resposta. Esse número de três dígitos também é conhecido como "código de status".

| Nome | Faixa de códigos de status |
| ------ | : ------ : |
| Informativo | 100-199 |
| Bem-sucedido | 200-299 |
| Redirecionamento | 300-399 |
| Erro do cliente | 400-499 |
| Erro de servidor | 500-599 |



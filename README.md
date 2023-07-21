# Fundamentos Teóricos do REST

Neste guia, abordaremos os conceitos fundamentais relacionados à arquitetura REST (Representational State Transfer).

![O que é REST](/assets/What-Is-a-REST.jpg)

## Sumário

- [O que é Web Services?](#o-que-é-web-services)
- [SOAP vs REST](#soap-vs-rest)
- [O que é REST?](#o-que-é-rest)
- [Request e Response](#request-e-response)
- [Tipos de Parâmetros](#tipos-de-parâmetros)
- [HTTP Status Code](#http-status-code)
- [Verbos HTTP](#verbos-http)
- [Níveis de Maturidade do REST](#niveis-de-maturidade-do-rest)
- [HATEOS](#hateos)
- [Documentação Swagger](#documentação-swagger)
- [Autenticação](#autenticação)
- [Versionamento](#versionamento)

## O que é Web Services?

Web Service é uma solução utilizada na integração de sistemas e na comunicação entre aplicações diferentes. Com esta tecnologia é possível que novas aplicações possam interagir com aquelas que já existem e que sistemas desenvolvidos em plataformas diferentes sejam compatíveis. 

Os Web Services utilizam uma série de padrões e protocolos com o objetivo de permitir a comunicação entre diferentes aplicações e linguagens de programação. Entre os protocolos mais utilizados estão o XML (Extensible Markup Language), SOAP (Simple Object Access Protocol) e o REST (Representational State Transfer).

## SOAP vs REST

Enquanto muitos sistemas legados ainda usam SOAP, REST surgiu depois e costuma ser visto como uma alternativa mais rápida nos casos baseados em web. REST é um conjunto de diretrizes que oferece uma implementação flexível. Já SOAP é um protocolo com requisitos específicos, como a mensageria XML.

As APIs REST são leves e ideais para contextos mais modernos, como a Internet das Coisas (IoT), desenvolvimento de aplicações mobile e serverless. Os serviços web SOAP oferecem segurança integrada e transações em conformidade que atendem a muitas necessidades empresariais, mas que também os deixam mais pesados.

## O que é REST?

REST é um conjunto de princípios de arquitetura que atende às necessidades de aplicações mobile e serviços web leves. Como se trata de um grupo de diretrizes, são os desenvolvedores que precisam implementar essas recomendações.

Quando uma solicitação de dados é enviada a uma API REST, ela normalmente é feita por meio do protocolo de transferência de hipertexto (hypertext transfer protocol, mais conhecido como HTTP). Depois que a solicitação é recebida, as APIs projetadas para REST (chamadas de serviços web ou APIs RESTful) retornam mensagens em diversos formatos: HTML, XML, texto simples e JSON.

As recomendações do estilo de arquitetura REST incluem:

- **Cliente-servidor:** a interface do usuário e a lógica do servidor devem ser separadas.
- **Stateless:** cada solicitação do cliente para o servidor deve conter todas as informações necessárias para que o servidor compreenda a solicitação, sem necessidade de manter um estado.
- **Cacheable:** as respostas do servidor devem ser explicitamente marcadas como cacheáveis ou não-cacheáveis.
- **Sistema em camadas:** um cliente não deve ser capaz de dizer se está se comunicando diretamente com o servidor final ou com um intermediário.
- **Interface uniforme:** a interface entre o cliente e o servidor deve ser padronizada, simplificando assim a arquitetura geral e melhorando a visibilidade, portabilidade e escalabilidade.
- **Código sob demanda (opcional):** os clientes podem baixar e executar código (como applets Java e Javascript) do servidor.

## Request e Response 

Request e Response são termos utilizados em programação para se referir a troca de informações entre um cliente e um servidor.

Um cliente faz uma requisição (Request) para um servidor, que então envia uma resposta (Response) ao cliente.

Na web, as requisições e respostas geralmente são feitas por meio de URLs (Uniform Resource Locators). Quando um usuário digita um endereço em seu navegador, ele está fazendo uma requisição para o servidor que hospeda o site correspondente. O servidor então envia uma resposta, que é exibida no navegador do usuário.

## Tipos de Parâmetros

Existem vários tipos de parâmetros que podem ser utilizados em Web Services, dependendo do método de comunicação e das necessidades específicas da aplicação. Alguns dos tipos de parâmetros mais comuns são:

1. Parâmetros de consulta (Query Parameters): São utilizados em requisições HTTP GET para enviar dados na URL. Eles são usados para filtrar ou especificar detalhes da requisição. Por exemplo, em uma requisição de busca de produtos, é possível utilizar um parâmetro de consulta para especificar o nome ou o preço máximo dos produtos desejados.
2. Parâmetros de caminho (Path Parameters): Também são utilizados em requisições HTTP, geralmente em combinação com o método GET. Eles são inseridos diretamente na URL para identificar um recurso específico. Por exemplo, em uma API de gerenciamento de usuários, o ID do usuário pode ser passado como um parâmetro de caminho na URL.
3. Parâmetros de formulário (Form Parameters): São utilizados em requisições HTTP POST, PUT ou DELETE para enviar dados no corpo da requisição, em um formato de formulário. Eles são comumente usados para enviar informações em um formato estruturado, como enviar dados de um formulário HTML para um servidor.
4. Parâmetros de cabeçalho (Header Parameters): São utilizados para enviar informações adicionais na requisição HTTP, especificadas nos cabeçalhos da requisição. Eles podem conter dados como autenticação, tipo de conteúdo, preferências de idioma, entre outros.
5. Parâmetros de corpo (Body Parameters): São utilizados em requisições HTTP POST, PUT ou DELETE para enviar dados mais complexos no corpo da requisição, geralmente em formato JSON ou XML. Eles são úteis para enviar objetos ou estruturas de dados mais complexas, como um JSON contendo informações detalhadas de um usuário.

Esses são apenas alguns exemplos dos tipos de parâmetros mais comuns utilizados em Web Services. A escolha do tipo de parâmetro depende do método de comunicação utilizado, das necessidades da aplicação e das convenções adotadas na API ou serviço em questão.

## HTTP Status Code

Os códigos de status HTTP são códigos numéricos que indicam o resultado de uma requisição HTTP entre um cliente (por exemplo, um navegador da web) e um servidor web. Esses códigos são parte do protocolo HTTP e são retornados como parte da resposta do servidor para informar o cliente sobre o status da requisição.

Aqui estão alguns exemplos dos principais grupos de códigos de status HTTP:

1. Códigos de Informação (Informational): Começam com o número 1 (por exemplo, 100, 101). São usados para informar o cliente de que a requisição foi recebida e está sendo processada.
2. Códigos de Sucesso (Success): Começam com o número 2 (por exemplo, 200, 201, 204). Indicam que a requisição foi bem-sucedida e foram retornadas as informações solicitadas pelo cliente.
3. Códigos de Redirecionamento (Redirection): Começam com o número 3 (por exemplo, 301, 302, 304). Indicam que o cliente precisa tomar alguma ação adicional para completar a requisição, como redirecionar para outra URL.
4. Códigos de Erro do Cliente (Client Error): Começam com o número 4 (por exemplo, 400, 401, 404). Indicam que houve um erro na requisição feita pelo cliente, como uma solicitação inválida ou falta de autorização.
5. Códigos de Erro do Servidor (Server Error): Começam com o número 5 (por exemplo, 500, 502, 503). Indicam que ocorreu um erro no servidor ao processar a requisição, geralmente por um problema interno ou falha temporária.

## Verbos HTTP

Os verbos HTTP, também conhecidos como métodos HTTP, são comandos que indicam a ação que deve ser realizada em um recurso específico. Eles são usados para descrever a intenção da requisição HTTP e determinam o tipo de operação que será executada no servidor. Os principais verbos HTTP são:

1. GET: É usado para solicitar a obtenção de um recurso do servidor. O servidor irá retornar o conteúdo solicitado na resposta. Esse verbo não deve ter efeitos colaterais no servidor, ou seja, não deve alterar nenhum dado.
2. POST: É usado para enviar dados ao servidor para criação de um novo recurso ou para a execução de uma ação. Geralmente, é usado para submeter formulários, enviar dados de login, enviar dados para serem processados, etc.
3. PUT: É usado para atualizar completamente um recurso no servidor. O cliente envia os dados atualizados e o servidor substitui o recurso pelo novo conteúdo enviado.
4. PATCH: É usado para atualizar parcialmente um recurso no servidor. O cliente envia apenas as partes do recurso que desejam ser alteradas, e o servidor aplica essas alterações.
5. DELETE: É usado para solicitar a exclusão de um recurso no servidor. O servidor irá remover o recurso especificado na requisição.
6. HEAD: É semelhante ao GET, mas o servidor não retorna o corpo da resposta, apenas os cabeçalhos. É útil para verificar a existência ou verificar os metadados de um recurso sem receber seu conteúdo completo.
7. OPTIONS: É usado para obter informações sobre os métodos HTTP que o servidor suporta para um recurso específico. Isso é útil para descobrir quais ações são permitidas para um determinado recurso.
8. TRACE: É usado para obter um loop-back da requisição, permitindo que o cliente veja o que está sendo recebido pelo servidor. É mais usado para fins de depuração e geralmente não é habilitado em produção.

## Niveis de Maturidade do REST

Os níveis de maturidade do REST são um modelo para avaliar o quão bem uma API REST implementa os princípios do REST. O modelo foi desenvolvido por Leonard Richardson, e é baseado em quatro níveis de maturidade:

![Niveis de Maturidade do REST](/assets/niveis.png)

- Nivel 0 (The Swamp of POX):
  - Todas as informações são salvas em um único endpoint;
  - Usa apenas os verbos GET e POST;
  - Essa API não é considerada REST.
  
- Nivel 1 (Resources):
  - Uma URL é criada para cada recurso que será consumido;
  - Para representar cada recurso fazemos uso de substantivos no plural.

- Nivel 2 (HTTP Verbs):
  - Se encarrega de garantir que os [verbos HTTP](#verbos-http) sejam usados de forma correta;
  - Leva em consideração o retorno correto dos [status code](#http-status-code) de cada endpoint após cada operação.

- Nivel 3 (Hypermedia Controls):
  - Referido pela sigla [HATEOS](#hateos) (Hypertext As The Engine Of Application State);
  - Fornece aos seus clientes links que indicarão como poderá ser feita a navegação entre seus recursos;
  - Quem for consumir a API precisará saber apenas a rota principal e a resposta dessa requisição terá todas as demais rotas possíveis.
 
## HATEOS

HATEOAS é um acrônimo para Hypermedia as the Engine of Application State. É uma restrição do estilo de arquitetura REST que enfatiza a utilização de hipermídia para dar aos clientes a capacidade de navegar pelo estado da aplicação sem depender de conhecimento específico da aplicação.

Em uma API REST, os recursos são representados como objetos JSON ou XML. Esses objetos podem conter links para outros recursos, que podem ser acessados ​​realizando novas solicitações HTTP. Os clientes podem usar esses links para navegar pela API sem precisar saber nada sobre a estrutura da API ou o nome dos recursos.

HATEOAS é uma abordagem poderosa para o desenvolvimento de APIs REST. Ele torna as APIs mais flexíveis, escaláveis e fáceis de usar. Também torna as APIs mais tolerantes a mudanças, pois os clientes não precisam ser atualizados quando a estrutura da API muda.

Aqui estão alguns benefícios de usar HATEOAS:

  - **Flexibilidade:** Permite que os clientes naveguem pela API de forma independente, sem depender de conhecimento específico da API. Isso torna as APIs mais flexíveis e tolerantes a mudanças.
  - **Escalabilidade:** Permite que os clientes naveguem pela API sem precisar armazenar nenhuma informação no estado local. Isso torna as APIs mais escaláveis, pois podem lidar com mais clientes sem exigir mais recursos de hardware.
  - **Facilidade de uso:** Torna as APIs mais fáceis de usar, pois os clientes não precisam saber nada sobre a estrutura da API ou o nome dos recursos. Isso torna as APIs mais acessíveis a um público mais amplo.
  - **Tolerância a mudanças:** Torna as APIs mais tolerantes a mudanças, pois os clientes não precisam ser atualizados quando a estrutura da API muda. Isso torna as APIs mais duradouras e fáceis de manter.

Se você estiver desenvolvendo uma API REST, eu recomendo usar HATEOAS. É uma abordagem poderosa que pode tornar suas APIs mais flexíveis, escaláveis, fáceis de usar e tolerantes a mudanças.

## Documentação Swagger

O Swagger é um software criado em 2011, que possui um conjunto de ferramentas construídas em torno de uma especificação chamada OpenAPI, que ajuda a projetar, construir, documentar e consumir APIs.

Aqui estão alguns benefícios de usar a documentação Swagger:

  - Melhor documentação: a documentação Swagger fornece uma documentação abrangente e precisa da API. Isso facilita para os desenvolvedores entenderem como usar a API.
  - Geração de código: a documentação Swagger pode ser usada para gerar código cliente para diferentes linguagens e plataformas. Isso facilita para os desenvolvedores começarem a usar a API rapidamente.
  - Teste: a documentação Swagger pode ser usada para testar a API. Isso facilita para os desenvolvedores garantir que a API esteja funcionando conforme o esperado.
  - Automação de implantação: a documentação Swagger pode ser usada para automatizar o processo de implantação da API. Isso facilita para os desenvolvedores implantar a API em um ambiente de produção.

## Autenticação

A autenticação é o processo de verificar a identidade de um usuário. Em APIs REST, a autenticação é usada para verificar a identidade de um usuário antes de permitir que ele acesse recursos.

Existem vários métodos de autenticação que podem ser usados em APIs REST, incluindo:

  - Autenticação de base de dados: este é o método de autenticação mais comum. Ele envolve o armazenamento de nomes de usuário e senhas em uma base de dados. Quando um usuário faz login, o nome de usuário e a senha são verificados na base de dados.
  - Autenticação de token: este método de autenticação envolve o uso de tokens para representar a identidade de um usuário. Os tokens são gerados pelo servidor e são enviados para o cliente. O cliente usa o token para fazer solicitações ao servidor.
  - Autenticação de OAuth: este método de autenticação é um padrão aberto para a autorização de aplicativos de terceiros. Ele envolve o uso de um servidor de autorização para autorizar aplicativos de terceiros a acessar recursos em nome de um usuário.

O método de autenticação mais adequado para uma API REST depende das necessidades específicas da API. Se a API precisa proteger recursos confidenciais, é importante usar um método de autenticação seguro, como a autenticação de base de dados ou a autenticação de token.

Aqui estão algumas dicas para autenticar APIs REST:

  - Use um método de autenticação seguro.
  - Armazene senhas com segurança.
  - Use tokens expirados.
  - Monitore suas APIs para atividades suspeitas.

## Versionamento

O versionamento é o processo de atribuir versões aos recursos de uma API REST. Isso permite que os clientes usem diferentes versões da API ao mesmo tempo, sem se preocupar com a incompatibilidade.

  - Versionamento de recurso: este método envolve o uso de diferentes URIs para diferentes versões da API. Por exemplo, a versão 1 da API pode estar em `/api/v1`, enquanto a versão 2 da API pode estar em `/api/v2`.
  - Versionamento de cabeçalho: este método envolve o uso de um cabeçalho HTTP para especificar a versão da API que o cliente está usando. Por exemplo, o cabeçalho `X-API-Version` pode ser usado para especificar a versão da API que o cliente está usando.

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


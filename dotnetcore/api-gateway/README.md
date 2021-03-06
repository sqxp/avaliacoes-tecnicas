# dotnetcore-api-gateway
## contextualização
#### **o que é um api gateway?**
![](https://raw.githubusercontent.com/sqxp/avaliacoes-tecnicas/master/dotnetcore/api-gateway/assets/api-gateway.png)

de maneira simples, um api gateway é um barramento que serve como abstração para requisições à um grupo de apis; ou seja, ele faz o roteamento para um ou mais apis, podendo inclusive abstrair protocolos de comunicação entre estes apis.

## objetivo
existem muitos frameworks que podem ser utilizados para criar um api gateway (como por exemplo [ocelot](https://github.com/ThreeMammals/Ocelot) para dotnetcore), porém o objetivo aqui é criar um api gateway na sua forma mais simples; ou seja, este api gateway deve executar **apenas a funcionalidade de roteamento**.

## instruções
#### 1. a solução deve ser desenvolvida utilizando aspnetcore
* use sua conta do [github](https://github.com/login) (caso não possua, crie uma)
* crie um **fork** do repositório [sq-dotnetcore-api-gateway](https://github.com/sqxp/sq-dotnetcore-api-gateway) para implementar sua solução
* após finalizada a implementação solicite um [pull request](https://help.github.com/en/articles/about-pull-requests)

#### 2. utilizar os apis [sq-pessoas-api](https://github.com/sqxp/sq-pessoas-api) e [sq-medalhas-api](https://github.com/sqxp/sq-medalhas-api)
* estes apis já estão codificados e funcionais
* estes apis utilizam [graphql](https://github.com/graphql-dotnet/graphql-dotnet) como forma de consulta às informações.

#### 3. a solução deve ser conteinerizada com uso do [docker](https://www.docker.com)
* deve conter um arquivo shell ou batch para construir a imagem

#### 4. deve conter um orquestrador de containers, para isto vamos usar o [docker-compose](https://docs.docker.com/compose/)
* deve então conter o arquivo docker-compose.yml, neste arquivo deve conter todos os containers necessários para **subir** a solução.

#### 5. a solução deve ter uma documentação README.MD contendo instruções de como subir a solução
* o **fork** criado no item 1, já contém o arquivo README.MD, você deve então escrever a documentação nele
* veja este [exemplo](https://github.com/sqxp/sq-pessoas-api/blob/master/README.md) de documentação

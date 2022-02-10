# API de Exemplo

Para facilitar o desenvolvimento do projeto, criamos uma API de exemplo que deve ser utilizada para o consumo e a persistência de dados.

## Instalação das Dependências

Para instalar as dependências ([JSON Server](https://github.com/typicode/json-server) e [JSON Server Auth](https://github.com/jeremyben/json-server-auth)) para a execução da API, utilize um dos comandos abaixo:
```
# NPM
npm install
```

## Execução da API

Para executar a API, basta executar o seguinte comando:

```
npm start
```

Com isso, a API estará disponível para acesso no endereço ```http://localhost:3004/``` podendo ser acessada externamente dentro da sua rede local pelo IP da sua máquina. Exemplo: ```http://192.168.0.13:3004/```.

## Serviços Disponíveis

Abaixo são listados os serviços disponibilizados pela API para o desenvolvimento das funcionalidades da aplicação.
```
# Usuários
GET     /users
POST    /users

# Autenticação JWT
POST    /login

# Campanhas
GET 	/campanha

# Grupos de Atendimento
GET     /grupos-atendimento

# Disponibilidade de agendamentos
GET     /agendamento-disponibilidade

# Agendamentos
GET     /agendamentos
GET     /agendamentos/{id}
POST    /agendamentos
PUT     /agendamentos/{id}
PATCH   /agendamentos/{id}

# Transparência
GET     /transparencia
```

## Filtros

Utilize os campos desejados para busca nos parâmetros da URL (_querystring_) para realizar uma busca nos dados retornados.

Exemplo:
```
GET     /agendamento-disponibilidade?municipio=Natal
GET     /agendamento-disponibilidade?localizacao=Via Direta
```

## Paginação

Utilize ```_page``` e ```_limit``` (opcional) para paginar os dados retornados. Por padrão, a paginação é feita de 10 em 10 itens.

Exemplo:
```
GET     /agendamento-disponibilidade?_page=2
GET     /agendamento-disponibilidade?_page=2&_limit=5
```

## Ordenação

Utilize ```_sort``` e ```_order``` para ordernar os dados retornados. Exemplo:
```
GET     /agendamento-disponibilidade?_sort=data&_order=asc
GET     /agendamento-disponibilidade?_sort=data,localizacao&_order=desc,asc
```

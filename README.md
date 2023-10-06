![logo](https://github.com/jeanmatheuss/SB-2023-python/blob/main/imgs/logo.jpg?raw=true)

# **Projeto 1**: Explorando IA Generativa em Pipeline de ETL com Python

[Link do notebook](https://github.com/jeanmatheuss/SB-2023-python/blob/main/bootcamp-santander23.ipynb)
---

## Contexto
Como cientista de dados no Santander, nossa tarefa era melhorar o envolvimento dos clientes por meio de mensagens de marketing altamente personalizadas.    
O objetivo é utilizar  a Inteligência Artificial Generativa para criar mensagens que ressoem com cada cliente individualmente.

Aqui estão as estapas que seguiremos:
1. Extração e Obtenção de Dados dos Clientes
2. Geração de Mensagens Personalizadas
3. Atualização de Dados dos Clientes

### 1. Extração de Dados
Faremos a extração de um arquivo .json de uma [API SDW](https://sdw-2023-prd.up.railway.app/swagger-ui/index.html#/) contendo os clientes fictícios do banco Santander.  
Salvando essa lista em uma variável para ser atualizada conforme a mensagem gerada.

### Transformação de Dados
O arquivo .json fornecido pela API tem o seguinte formato:

```json
[
  {
    "id": 0,
    "name": "string",
    "account": {
      "id": 0,
      "number": "string",
      "agency": "string",
      "balance": 0,
      "limit": 0
    },
    "card": {
      "id": 0,
      "number": "string",
      "limit": 0
    },
    "features": [
      {
        "id": 0,
        "icon": "string",
        "description": "string"
      }
    ],
    "news": [
      {
        "id": 0,
        "icon": "string",
        "description": "string"
      }
    ]
  }
]

```
Onde:
- **id**: Um `int` com o id de cada cliente;
- **name**: Uma `string` com o nome do cliente;
- **account**: Um `dict` com as informações de id da conta (*id*), número da conta (*number*), agência (*agency*), saldo (*balance*) e limite (*limit*);
- **card**: Um `dct` com as informações de id da conta (*id*), número do cartão (*number*), limite do cartão (*limit*);
- **features**: Um `dict` contendo as informações e características do cliente;
- **news**: Um `dict` que contém as mensagens personalizadas para o cliente.


### 2. Geração de Mensagens Personalizadas

Para a geração de mensagens usamos o ChatGPT e sua API da OpenAI, assim ele gera uma mensagem personalizada com base no nome e no limite do cliente.

>[Documentação da API da OpenAI](https://platform.openai.com/docs/api-reference/chat)

### 3. Atualização dos Dados dos clientes

Agora com a mensagem personalizada precisamos envia-la de volta a API de banco de dados dos clientes, atualizando a mensagem no banco de dados. E em caso ocorra tudo certo, será feito um 'print' com a mensagem:  
 ```"User {user} updated: True!" ```,   
 caso contrário:   
 ```"User {user} updated: False! Error: {error_code}"```  
 informando o erro.



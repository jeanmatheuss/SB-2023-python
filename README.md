![logo](https://github.com/jeanmatheuss/SB-2023-python/blob/main/imgs/logo_bootcamp.jpeg?raw=true)

# **Projeto 1**: Explorando IA Generativa em Pipeline de ETL com Python

[Link do notebook]()
---

## Contexto
Como cientista de dados no Santander, nossa tarefa era melhorar o envolvimento dos clientes por meio de mensagens de marketing altamente personalizadas.    
O objetivo é utilizar  a Inteligência Artificial Generativa para criar mensagens que ressoem com cada cliente individualmente.

Aqui estão as estapas que seguiremos:
1. Extração de Dados
2. Obtenção de Dados  dos Clientes
3. Transformação de Dados
4. Geração de Mensagens Personalizadas
5. Atualização de Dados dos Clientes

### Extração de Dados
Faremos a extração de um arquivo .json de uma [API](https://sdw-2023-prd.up.railway.app/swagger-ui/index.html#/) contendo os clientes fictícios do banco Santander.

### Transformação de Dados
O arquivo .json  tem o seguinte formato:

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
Para extrair e alterar as informações vamos utilizar o pacote *pandas* do python.

### Geração de Mensagens Personalizadas

### Atualização dos Dados dos clientes




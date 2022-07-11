# Cliente-online
Integração com whatsapp Opa Suite

#Serviços de Integração

<!--ts-->
   * [Login](#Login)
   * [Boleto](#Boleto)
   * [Instalação](#instalacao)
   * [Como usar](#como-usar)
      * [Pre Requisitos](#pre-requisitos)
      * [Local files](#local-files)
      * [Remote files](#remote-files)
      * [Multiple files](#multiple-files)
      * [Combo](#combo)
   * [Tests](#testes)
   * [Tecnologias](#tecnologias)
<!--te-->

#### **Dados**
```php
URL_API: http://l1.whmsam.com.br/api/
```

##### **Headers:**
```json
Content-Type: application/json
```


# Login

#### **Dados**
```php
URL: URL_API/auth/login
```

#### **Method: POST**

##### **Headers:**

```json
Content-Type: application/json
```


##### **Request**

```json
{ 
        "codigo": "15b803aea398e8dcf3ac8e5971e4dcc2",
        "usuario": "96aC#f56A_sS31f#dF37"
}
```


##### **Response**
```json
{ 
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sMS53aG1zYW0uY29tLmJyXC9hcGlcL2F1dGhcL2xvZ2luIiwiaWF0IjoxNjUxMTY4MDkxLCJleHAiOjE2NTExNzUyOTEsIm5iZiI6MTY1MTE2ODA5MSwianRpIjoidlJ0UFB2Q3NWQTB6ZmdiOSIsInN1YiI6NywicHJ2IjoiMjNiZDVjODk0OWY2MDBhZGIzOWU3MDFjNDAwODcyZGI3YTU5NzZmNyJ9.rnppVsJB6957l_zeuwc9mpXj9a0zbmRitTk-YzMDGa0",
        "token_type": "bearer",
        "expires_in": 7200
}
```



# Boleto

#### **Dados**
```php
URL: URL_API/boleto 
```

#### **Method**
```json
Method: GET
```

#### **Authorization**
```json
  Type: Bearer Token
  Token: required
```

##### **Headers:**
```json
  Content-Type: application/json
```

##### **Body**

```json
{ 
    "sigla": "bar",
    "cpf_cnpj": "40200310020"
}
```


##### **Request**
```json
{ 
        "codigo": "15b803aea398e8dcf3ac8e5971e4dcc2",
        "usuario": "96aC#f56A_sS31f#dF37"
}
```


##### **Response**
```json
{ 
        "objeto": "boleto",
        "itens": [
          {
            "modulo": "condominio",
            "id": 1582245,
            "valor": "376.16",
            "vencimento": "2022-05-10",
            "condominio": {
            "id": 293,
            "nome": "GALERIA NOSSA SENHORA DO ROSÁRIO"
          },
          "unidade": {
            "id": 9679,
            "nome": "713A"
          },
         "link": "https://clienteonline.samisistemas.com.br/TCPDF/examples/ImprimirBoletoEmail.php?p=bar4952548269786648N"
        }
        ],
        "total": 1
}
```


##### **Exemplo de request boleto locação**
```json
{
  "sigla": "bar",
  "cpf_cnpj": "74932640900"
}
```


##### **Exemplo de request boleto locação**
```json
{
  "objeto": "boleto",
  "itens": [
   {
      "modulo": "locacao",
      "id": 1584991,
      "valor": "523.55",
      "vencimento": "2022-05-02",
      "contrato": 7810,
      "link": "https://clienteonlinelocacao.samisistemas.com.br/TCPDF/examples/ImprimirBoletoEmail.php?p=bar2158548272159394L"
  }
],
"total": 1
}
```

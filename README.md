# Cliente Online
Integração com whatsapp Opa Suite

#Serviços de Integração

<!--ts-->
   * [Login](#Login)
   * [Boleto](#Boleto)
      * [Recuperar boleto pelo id](#Boleto-id)
   * [Pessoa](#Pessoa)
   
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

##### **Request**

```json
{ 
        "codigo": "SOLICITAR",
        "usuario": "SOLICITAR"
}
```


##### **Response**
```json
{ 
        "access_token": "RETORNO_TOKEN",
        "token_type": "bearer",
        "expires_in": 7200
}
```

#


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

##### **Body**

```json
{ 
    "sigla": "SOLICITAR",
    "cpf_cnpj": "SOLICITAR"
}
```


##### **Request**
```json
{ 
        "codigo": "SOLICITAR",
        "usuario": "SOLICITAR"
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
  "sigla": "SOLICITAR",
  "cpf_cnpj": "SOLICITAR"
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

# Boleto-id


#### **Dados**
```php
URL: URL_API/boleto/{id}
```

#### **Method: GET**


##### **Body**

```json
{ 
        sigla: (string) required
}
```

##### **Request**

```json
{ 
        "sigla": "SOLICITAR"
}
```


##### **Response**
```json
{ 
        "objeto": "boleto",
        "item": {
          "modulo": "condominio",
          "id": 1565045,
          "valor": "460.03",
          "vencimento": "2022-09-03",
          "condominio": {
          "id": 98,
          "nome": "PRINCIPE REGENTE"
          },
          "unidade": {
          "id": 2352,
          "nome": "301"
          },
          "link": "https://clienteonline.samisistemas.com.br/TCPDF/examples/ImprimirBoletoEmail.php?p=bar1955548068238855E"
        }
}
```



# Pessoa


#### **Dados**
```php
URL: URL_API/pessoa
```

#### **Method: GET**

#### **Authorization**
```json
  Type: Bearer Token
  Token: required
```

##### **Body**

```json
{ 
        sigla: (string) required
}
```

##### **Request**

```json
{ 
       "sigla": "SOLICITAR",
       "cpf_cnpj": "SOLICITAR",
        "telefone": "SOLICITAR"
}
```


##### **Response**
```json
{ 
        "objeto": "pessoa",
        "id": "",
        "nome": "NEWTON RIBEIRO DA ROSA",
        "fantasia": "",
        "cpf_cnpj": "11643639803",
        "telCelular": "5186232347",
        "telResidencial": "5135412347",
        "telComercial": "",
        "email": "testedasami@gmail.com",
        "senha": "",
        "status": true
}
```

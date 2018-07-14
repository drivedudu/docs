# REGEX
---

#### Selecionar toda a linha

> ^(.+)$

---

#### Toda palavra do inicio da linha

> \w.+

---

#### Variavél de resultado da seleção do regex

> **$&** ou **\1**

?>Exemplo  
concatenar *lixo* com *( )* então (**$&**) fica (lixo).

***

#### Caracter de inicio e final da linha

> Inicio: **^** 	final : **$**

---

#### Caracter para Nova linha

> \n

---

#### Capturar tudo após o Caracter mas não incluí-lo na saída

```bash
(?<=Caracter).*$
```

---

| classe POSIX | similar | significa |
|:------------:|:-------:|:---------:|
|`[:upper:]` |	[A-Z] |   	letras maiúsculas e acentuadas|
|`[:lower:]` |	[a-z] |   	letras minúsculas e acentuadas|
|`[:alpha:]` |	[A-Za-z] |	maiúsculas/minúsculas e acentuadas|
|`[:alnum:]` |	[A-Za-z0-9] |	letras e números e acentuadas|
|`[:digit:]` |	[0-9] |   	números|
|`[:xdigit:]` |	[0-9A-Fa-f] |	números hexadecimais|
|`[:punct:]` |	[.,!?:...] |	sinais de pontuação|
|`[:blank:]` |	[ \t] |   	espaço e TAB|
|`[:space:]` |	[ \t\n\r\f\v] |	caracteres brancos|
|`[:cntrl:]` |	-       	| caracteres de controle|
|`[:graph:]` |	[^ \t\n\r\f\v] |	caracteres imprimíveis|
|`[:print:]` |	[^\t\n\r\f\v] |	imprimíveis e o espaço|


---

Lista
---

#### Lista simples  

> [0-9A-Z]

?> **Explicação**  
Busca somente os componentes listados.  
Para usar o `-` ou `^` na lista é colocado no final da lista, assim [0-9**-^**]. 
O colchete `[` pode se colocado em qualquer lugar na lista,
O colchete `]`  deve ser colocado no começo da lista.
Então [`]-`] casa um ] ou um -.

---

#### Lista de negação

> [^...]

?> **Explicação**   
 A única diferença é que ela possui lógica inversa, ou seja, busca qualquer coisa, fora os componentes listados.


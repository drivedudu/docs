<input type="text" id="myInput" onkeyup="myFunction()" placeholder="Digite para filtrar...">


<!-- MarkdownTOC autolink="true" bracket="round"  style="unordered" -->

- [COMANDOS](#comandos)
- [Converter fat32 para ntfs sem perda de dados](#converter-fat32-para-ntfs-sem-perda-de-dados)
- [Remover messagem de atualização](#remover-messagem-de-atualiza%C3%A7%C3%A3o)
- [Super usuario nt/Sistema](#super-usuario-ntsistema)
- [CMD Criar usuarios e adicionar em grupos](#cmd-criar-usuarios-e-adicionar-em-grupos)
- [CMD executar com outro usuário](#cmd-executar-com-outro-usu%C3%A1rio)
- [CMD propriedades/relatorios windows](#cmd-propriedadesrelatorios-windows)
- [CMD resultado para clipboard - copia](#cmd-resultado-para-clipboard---copia)
- [CMD Comandos chave office key](#cmd-comandos-chave-office-key)
- [CMD  Copiar mantendo as permissões](#cmd-copiar-mantendo-as-permiss%C3%B5es)
- [CMD Remove updates windows.](#cmd-remove-updates-windows)
- [Limpar cache windows installer](#limpar-cache-windows-installer)
- [Office 2013 Mudar caminho OST Regedit](#office-2013-mudar-caminho-ost-regedit)
- [POWERSHELL Migrar-Listar pastas compartilhadas](#powershell-migrar-listar-pastas-compartilhadas)
- [Limpeza de disco usando cleanmgr](#limpeza-de-disco-usando-cleanmgr)
- [Enable/Disable UAC Windows 7](#enabledisable-uac-windows-7)
- [PSEXEC Remove File Share Remotely](#psexec-remove-file-share-remotely)
- [Adding Printer via Net Use LPT](#adding-printer-via-net-use-lpt)
- [REDES](#redes)
- [Openvpn server em windows](#openvpn-server-em-windows)
- [Obter mac do computador e remoto](#obter-mac-do-computador-e-remoto)
- [Super ping](#super-ping)
- [Obter todas os MACs da rede](#obter-todas-os-macs-da-rede)
- [Obter nome do computador por ip](#obter-nome-do-computador-por-ip)
- [Descobrir servidor de Email](#descobrir-servidor-de-email)
- [Descobrir DNS servidor de hospedagem](#descobrir-dns-servidor-de-hospedagem)
- [Saber sessões abertas no computador](#saber-sess%C3%B5es-abertas-no-computador)
- [Saber em qual Computador Usuário está Logado 6 opções](#saber-em-qual-computador-usu%C3%A1rio-est%C3%A1-logado-6-op%C3%A7%C3%B5es)
- [Descobrir o Domain Controller](#descobrir-o-domain-controller)
- [Visualizar senha salva redes Wi-Fi](#visualizar-senha-salva-redes-wi-fi)
- [REGEX ER-Expressões regulares](#regex-er-express%C3%B5es-regulares)
- [Selecionar toda a linha](#selecionar-toda-a-linha)
- [Toda palavra do inicio da linha](#toda-palavra-do-inicio-da-linha)
- [Variavél de resultado da seleção do regex](#variav%C3%A9l-de-resultado-da-sele%C3%A7%C3%A3o-do-regex)
- [Caracter para Nova linha](#caracter-para-nova-linha)
- [Resulta em uma linha vazia](#resulta-em-uma-linha-vazia)
- [Capturar tudo após o Caracter mas não incluí-lo na saída](#capturar-tudo-ap%C3%B3s-o-caracter-mas-n%C3%A3o-inclu%C3%AD-lo-na-sa%C3%ADda)
- [Metacaracteres](#metacaracteres)
- [Lista simples](#lista-simples)
- [Lista de negação](#lista-de-nega%C3%A7%C3%A3o)
- [Opcional](#opcional)
- [Asterisco](#asterisco)
- [Mais](#mais)
- [Curinga](#curinga)
- [Chaves](#chaves)
- [Circunflexo](#circunflexo)
- [Cifrão](#cifr%C3%A3o)
- [Limites da palavra](#limites-da-palavra)
- [Escape](#escape)
- [Alternativo](#alternativo)
- [Grupo](#grupo)
- [Retrovisor - Backreferences](#retrovisor---backreferences)
- [Quantificadores não-gulosos - lazyness](#quantificadores-n%C3%A3o-gulosos---lazyness)
- [Metacaracteres tipo barra-letra](#metacaracteres-tipo-barra-letra)
- [Metacaracteres - moderno](#metacaracteres---moderno)
- [Modificadores](#modificadores)
- [LINUX](#linux)
- [Terminar um processo](#terminar-um-processo)
- [Encontrar processo executando](#encontrar-processo-executando)
- [Executando via rede e porta](#executando-via-rede-e-porta)

<!-- /MarkdownTOC -->

#### COMANDOS 


#### Converter fat32 para ntfs sem perda de dados
>convert **letra**: /FS:ntfs

---


#### Remover messagem de atualização
> cd /d "%Windir%\System32"  
takeown /F MusNotification.exe  
icacls MusNotification.exe /deny Everyone:(X)  
takeown /F MusNotificationUx.exe  
icacls MusNotificationUx.exe /deny Everyone:(X)  
rem  

?>  ***Desfazer***  
cd /d "%Windir%\System32"  
icacls MusNotification.exe /remove:d Everyone  
icacls MusNotification.exe /grant Everyone:F  
icacls MusNotification.exe /setowner "NT SERVICE\TrustedInstaller"  
icacls MusNotification.exe /remove:g Everyone  
icacls MusNotificationUx.exe /remove:d Everyone  
icacls MusNotificationUx.exe /grant Everyone:F  
icacls MusNotificationUx.exe /setowner "NT SERVICE\TrustedInstaller"  
icacls MusNotificationUx.exe /remove:g Everyone  
rem

---



#### Super usuario nt/Sistema

>psexec -i -s **comando**  

?> ***Sessão em powershell uso em remoto***  
Start-Process -FilePath cmd.exe -Verb Runas -ArgumentList '/k C:\SysinternalsSuite\PsExec.exe -i -s powershell.exe'

<p class="yellow">
 ***Pstool aceitar contrato eula por cmd***  ferramenta-do-pstool /accepteula 
 <p>

---

#### CMD Criar usuarios e adicionar em grupos

>net user **username password** /add
>net localgroup **grupo usuario** /add

[tutorial](https://www.windows-commandline.com/add-user-from-command-line/)

---




#### CMD executar com outro usuário

>runas /noprofile /user:**usuario comando**

---




#### CMD propriedades/relatorios windows

>systeminfo

---




#### CMD resultado para clipboard - copia

>comando | clip

---



#### CMD Comandos chave office key

> * Ativar  
cscript ospp.vbs /inpkey:XXXXX-XXXXX-XXXXX-XXXXX-XXXXX  
cscript.exe ospp.vbs /act  
* Resetar  
cscript.exe ospp.vbs /rearm
* Status da licença - Serial  
cscript ospp.vbs /dstatus
* Remover (usando os 5 últimos characters da licença via /dstatus)
cscript.exe ospp.vbs /unpkey:5 últimos characters

?> ***CAMINHOS***  
2010  
C:\Program Files\Microsoft Office\Office14  
2013  
C:\Program Files\Microsoft Office\Office15  
2016  
C:\Program Files\Microsoft Office\Office16  

---



#### CMD  Copiar mantendo as permissões

> * LOCAL  
robocopy D:\Source E:\Destination /MIR /R:1 /W:1 /COPYALL  
* REDE  
robocopy `\\myserver\e$\data E:\data` /MIR /R:1 /W:1 /COPYALL


---

#### CMD Remove updates windows.

>wusa /uninstall /kb:2952664

?>número do update 2952664 a ser removido


----


#### Limpar cache windows installer

>msiexec /UNREGISTER  
>msiexec /REGSERVER

?>Instalações travadas

!> ***FIX*** **Deletar registros**   
Erros "Outra instalação está em andamento"  
HKEY_LOCAL_MACHINE \Software\Microsoft\Windows\CurrentVersion\Installer\InProgress  
HKEY_LOCAL_MACHINE \System\CurrentControlSet\Control\Session Manager\PendingFileRenameOperations  

---



#### Office 2013 Mudar caminho OST Regedit 

>Windows Registry Editor Version 5.00  
[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\outlook]  
"ForceOSTPath"=string:D:\My Documents\Outlook

?> Talvez precise criar um novo perfil e mova o antigo .ost para esse diretório (o mesmo nome de arquivo e sobrescreva o arquivo .ost existente)

---


#### POWERSHELL Migrar-Listar pastas compartilhadas 

>get-WmiObject -class Win32_Share -computer servername.fqdn.com | Export-Csv -Path "C:\Shares.csv"


---

#### Limpeza de disco usando cleanmgr

>cleanmgr.exe /VERYLOWDISK 

?> liberar espaço em disco dos arquivos antigos

>cleanmgr.exe /AUTOCLEAN 

?> Limpa pasta de instalações do windows e atualizações

---


####  Enable/Disable UAC Windows 7 

Enable
> %windir%\System32\reg.exe ADD HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v EnableLUA /t REG_DWORD /d 1 /f

Disable
> %windir%\System32\reg.exe ADD HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v EnableLUA /t REG_DWORD /d 0 /f


####  PSEXEC Remove File Share Remotely 

Remove  Remotely:

>psexec `\\PCNAME net share SHARENAME /delete`

Map Drive Remotely:

>psexec `\\PCNAME net use S: \\SERVER\SHARE`


#### Adding Printer via Net Use LPT

>NET USE LPT1: `\\server\printername /persistent:yes`

---

REDES
---


#### Openvpn server em windows

!> selecionar OpenVPN RSA certificate management scripts na instalação  
1 Reinciar após instalação  


?> 2 executar um cmd no **Caminhos**  
C:\Arquivos de Programas\OpenVPN\easy-rsa  

>init-config  

?> 3 Editar os parametros  de vars.bat

`C:\Arquivos de Programas\OpenVPN\easy-rsa\vars.bat`  

?> **Paramentros do vars.bat**  
set KEY_COUNTRY=US  
set KEY_PROVINCE=CA  
set KEY_CITY=SanFrancisco  
set KEY_ORG=OpenVPN  
set KEY_EMAIL=mail@host.domain


>vars  
clean-all  

?> 4 criar certificado mestre

>build-ca  


?> 5 gerar chave para servidor

>build-key-server `nome-para-servidor`

?> 6 gerar chave para clientes,

>build-key `nome-do-cliente-usuario`

?> 7 gerar criptografia 

>build-dh


?> 8 os certificados são localizados em C:\Arquivos de Programas\OpenVPN\easy-rsa\keys  
copiar `nome-para-servidor` .crt .key ca.crt dh1024.pem para C:\Arquivos de Programas\OpenVPN\config  
copiar C:\Arquivos de Programas\OpenVPN\samples\server.ovpn para C:\Arquivos de Programas\OpenVPN\config  

?> 9 Editar as linhas do arquivo server.opvn  
ca ca.crt  
cert `server.crt` para nome do servidor no passo 5  
key `server.key`  para nome do servidor no passo 5  
* salvar
* Mudar as mesma linha no arquivos client.ovpn pelo nome gerado no passo 6 e mudar a linha  
remote ip-fixo-do-servidor 1194


<p class="yellow"> solucionar falta de internet ou não acesso aos outros computadores, modificar no servidor vpn  
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters registro IPEnableRouter para 1 
<p>


[fonte](https://community.openvpn.net/openvpn/wiki/Easy_Windows_Guide)


#### Obter mac do computador e remoto
> getmac
* remoto  
>getmac /s `\\pc`

 ---

#### Super ping
> pathping

---

#### Obter todas os MACs da rede
> ping **ip**
 arp -a

---

#### Obter nome do computador por ip
> nslookup **ip** ou **hostname**

---

#### Descobrir servidor de Email
>nslookup  -querytype=mx  domain name

---

#### Descobrir DNS servidor de hospedagem
>nslookup  -querytype=ns domain name

---

#### Saber sessões abertas no computador
> nbtstat -s

---

#### Saber em qual Computador Usuário está Logado 6 opções
> 1 - PsLoggedon  
***PsLoggedon.exe -x `\\servidor` ***  
2 - Qwinsta  
***qwinsta /SERVER:servidor***  
3 - Encerrar sessão com ID via Qwinsta  
***rwinsta ID /SERVER:servidor***  
4 - Windows Logs (EventViewer)  
***Checar eventos com ID 4624 do Log Security***  
5 - Powershell Get-EventLog
Get-EventLog -LogName ***Security*** -InstanceID ***4624*** | Where `{$_.Message -match "Account Name:\s+NOME_Do_USUARIO"}` | Export-Csv usuario.csv

?> SCRIPT - Relatório de Conexões RDP em um Servidor
[BAIXAR](http://www.100security.com.br/tools/relatorio_rdp.ps1)


---

#### Descobrir o Domain Controller
> echo %logonserver%

---


#### Visualizar senha salva redes Wi-Fi 
> netsh wlan show profiles  
netsh wlan show profile name=**nome-da-rede** key=clear


---

===============================================================================================================================================


REGEX ER-Expressões regulares
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

---

#### Caracter para Nova linha

> \n

---

#### Resulta em uma linha vazia

> ^$

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

Metacaracteres
---

#### Lista simples  

` [0-9A-Z]`

?> **Explicação**  
Busca somente os componentes listados.  
Para usar o `-` ou `^` na lista é colocado no final da lista [0-9**-^**]. 
O colchete `[` pode se colocado em qualquer lugar na lista,
O colchete `]`  deve ser colocado no começo da lista.
Então [`]-`] casa um ] ou um -.

---

#### Lista de negação

`[^...]`

?> **Explicação**   
Busca qualquer coisa, fora os componentes listados. ` [^0-9A-Z]` não busca números ou letras maiúsculas


---

#### Opcional 

`?`

?> **Explicação**   
`casas?` tem a letra s marcada como opcional que resulta em casa e casas.  
`casa[sr]?` resulta em casa, casar, casas.

---

#### Asterisco

`*`

?> **Explicação**   
Repetirá o caractere anterior em qualquer quantidade de forma seguida, também mostra no resultado que não tiver o caractere anterior.  
A expressão `#-*[a-zA-Z]` (# seguido de - seguido de letra) resultaria:  

| Lista | Resultado | Dica |
|:-----:|:---------:|:-----|
|#-Novo | #-N 		| começa com `#` seguido de `-` seguido de letra|
|#Novo  | #N 		| começa com `#` seguido de letra, porque `-` é opcional|
|#--Novo| #--N 		| começa com `#` seguido de 1 ou  mais `-` seguido de letra|
|# Novo | Nada 		| começa com `#` seguido de espaço, porém espera-se `-` seguido de letra| 
|#-- Novo| Nada 	| começa com `#` seguido de `--` seguido de espaço, porém espera-se uma letra|

---

#### Mais

`+`

?>?> **Explicação**  
Repetirá o caractere anterior em qualquer quantidade de forma seguida e só mostra resultados que conter o caractere anterior.  
A expressão `#-+[a-zA-Z]` (# seguido de - seguido de letra) resultaria:  

Seguindo exemplo anterior. 

| Lista | Resultado | Dica |
|:-----:|:---------:|:-----|
|#-Novo | #-N 		| começa com `#` seguido de `-` seguido de letra|
|#Novo  | Nada 		| porque `-` é obrigatório |
|#--Novo| #--N 		| começa com `#` seguido de 1 ou  mais `-` seguido de letra|
|# Novo | Nada 		| porque `-` é obrigatório | 

---

#### Curinga

`.*`

?> **Explicação**  
Resultará tudo em uma linha. A expressão sozinha pode resultar até em linhas vazia.  
A expressão `Resul.*` selecionaria toda a linha de cima.

---

#### Chaves

`{minímo,máximo}`

?> **Explicação**  
Funciona de min até max vezes, como 1{1,3} resultado 1, 11 e 111.

| Tipos | Descrição |
|:-----:|:----------|
| {1,6} | de 1 a 6 |
| {6,}	|minímo 6 (6 ou mais) |
| {0,6}	|até 6 |
| {6}	|exatamente 6 |
| {1}	|exatamente 1 |
| {0,1}	|zero ou 1    (igual ao opcional)|
| {0,}	|zero ou mais (igual ao asterisco)| 
| {1,}	|um ou mais   (igual ao mais)|

---

#### Circunflexo

`^`

?> **Explicação**  
Serve para procurar caracteres no começo da linha. Marcador só é especial se estiver no começo da expressão.
Resulta em tudo que começar com letrar `^[a-z]` no inicío da linha.  
Resulta em tudo que contiver letras,^, letras `[a-z]^[a-z]`

---

#### Cifrão

`$`

?> **Explicação**  
 o cifrão marca o fim de uma linha e só funciona no final da expressão.

---

#### Limites da palavra

`\b`

?> **Explicação**  
Marca os limites de uma palavra, onde ela começa e/ou termina. permite que você execute uma pesquisa "somente palavras inteiras" usando uma expressão e não partes de palavras. Expressão `\b4\b` resulta em apenas um 4, o que não resulta em nada para **44 papel a4**.  
O \B é a versão negativa.

---


#### Escape

`\`

?> **Explicação**  
Transforma um caracter especial em literal  ` \.  \[   \]  \?  \+  \{  \} \^  \$ \\ `

---

#### Alternativo 

`|`

?> **Explicação**  
Você pode usar o `|`  para corresponder uma única expressão regular a várias expressões regulares possíveis.
Procurar pelo texto literal cat ou dog. `Cat|Dog`

---

#### Grupo

`(...)`

?> **Explicação**  
Ao colocar parte de uma expressão regular entre parênteses, você pode agrupar essa parte da expressão regular. Isso permite aplicar um quantificador ao grupo inteiro ou restringir a alternância a parte do regex.
Apenas parênteses podem ser usados ​​para agrupamento. Colchetes definem uma classe de caractere e chaves são usadas por um quantificador com limites específicos.  
Exemplos  
`Set(SetValue)?` corresponde a Set ou SetValue.  
`(\.[0-9]){3}`    	.0.6.2, .2.8.9,  
`(www\.)?cade\.com` 	www.cade.com, cade.com  
`boa-(tarde|noite)`	boa-tarde, boa-noite  
`(in|con)?certo` 	incerto, concerto, certo  
`(mini|(su|hi)per)?mercado` minimercador, supermercado, hipermercado, mercado.

---

#### Retrovisor - Backreferences

`\1..\9`

?> **Explicação**  
O retrovisor resulta no mesmo texto de uma ocorrência anterior de um grupo. Suponha que você queira combinar um par de tags HTML de abertura e fechamento e o texto entre. Obrigatório usar com o grupo.  
Exemplo  
<([A-Z][A-Z0-9]\*)\b>.\*?</`\1`>  
```
meu texto com html <B> <I> negrito itálico </I> </B>
Resultando  <B> <I> negrito itálico </I> </B>.
```

#### Quantificadores não-gulosos - lazyness

`.*? .+? .?? .{n,m}? `

?> **Explicação**  
 Precisa acrescentar uma interrogação logo após os quantificadores normais.  pois pesquisa no menor resultado possível.
então só busca se o caractere não estiver precisando.
 
|e.g 	 | resultado | |e.g|resultado sem ? |
|:------:|:---------:| |:--:|:--------------:|
| `1.*?` |   	1    | |  `a.*` 	 | aaaaa 	 |
| `1.+?` |	11 		 | |  `a.+`    |   aaaaa   |
| `\1.??`   | 	1 	 | |   `a.?`   |    aa     |
| `1.{1,3}?` |	11 	 | |  `a.{1,3}`|    aaaa   |

---

#### Metacaracteres tipo barra-letra

| lista | o que é | texto |
|:-----:|:-------:|:-----:|
|	\d	|	[[:digit:]]	|	dígito	|
|	\D	|	[^[:digit:]]	|	não-dígito	|
|	\w	|	[[:alnum:]_]	|	palavra	|
|	\W	|	[^[:alnum:]_]	|	não-palavra	|
|	\s	|	[[:space:]]	|	branco	|
|	\S	|	[^[:space:]]	|	não-branco	|
|	\a	|	alert   	|	alerta (bipe)	|
|	\b	|	backspace	|	caractere Backspace	|
|	\e	|	escape  	|	caractere Esc	|
|	\f	|	form feed	|	alimentação	|
|	\n	|	newline 	|	linha nova	|
|	\r	|	carriage ret	|	retorno de carro	|
|	\t	|	htab    	|	tabulação horizontal	|
|	\v	|	vtab    	|	tabulação vertical	|
|	\a	|	alfabeto        	|	[[:alpha:]]	|
|	\A	|	não-alfabeto    	|	[^[:alpha:]]	|
|	\h	|	cabeça de palavra	|	[[:alpha]_]	|
|	\H	|	não-cabeça de palavra	|	[^[:alpha:]_]	|
|	\l	|	minúsculas      	|	[[:lower:]]	|
|	\L	|	não-minúsculas  	|	[^[:lower:]]	|
|	\u	|	maiúsculas      	|	[[:upper:]]	|
|	\U	|	não-maiúsculas  	|	[^[:upper:]]	|
|	\o	|	número octal    	|	[0-7]	|
|	\O	|	não-número octal	|	[^0-7]	|
|	\B	|	não-borda	|		|
|	\A	|	início do texto	|		|
|	\Z	|	fim do texto	|		|
|	\l	|	torna minúscula	|		|
|	\L	|	torna minúscula até \E	|		|
|	\u	|	torna maiúscula	|		|
|	\U	|	torna maiúscula até \E			|
|	\Q	|	escapa até \E			|
|	\E	|	fim da modificação			|
|	\G	|	fim do casamento anterior			|


?> **Explicação**  
Um barra-LETRA é a negação de um barra-letra.


---

#### Metacaracteres - moderno
 
 `(?<identificador><conteúdo>)`

| lista | Uso |
|:-----:|:---:|
|	(?#texto)	|	 comentário (?#seu nome)pokemon	|
|	(?:ER)	|	um grupo normal () que não é incluído na contagem de grupos, ou seja, não é acessível com retrovisores ou $1 ^(Homer) `(?:J\.)` (Simpson) é o nome completo, mas \1 e \2 contém Homer e Simpson, respectivamente.	|
|	(?=ER)	|	 Homer (?=Simpson) só busca o Homer se for seguido de Simpson. Mas o sobrenome não faz parte do resulado. serviu apenas para checagem.	|
|	(?!ER)	|	só busca um trecho se este não for seguido da ER embutida. Então Homer (?!morreu) busca Homer comeu, mas não do Homer morreu.	|
|	(?<=ER)	|	(? <=a)b (lookbehind positivo) corresponde ao b se somente ao b for segido de a como cabine, mas não corresponde ao cebola.	|
|	(?<!ER)	|	é a negativa. então se (?<!a)b somente difirente de A mas seguido de B, como cebola. O comprimento deve ser limitado	|

---

#### Modificadores

`(?modificador)`

?> **Explicação**  
i: ignorar a diferença entre maiúsculas e minúsculas;  
m: trata o texto como multilinha;  
s: trata o texto como uma única linha;  
x: permite inclusão de espaços e comentários;  
L: levar em conta a localização do sistema (somente Python)  
Maneira de pode usar (?ismx)

---



===============================================================================================================================================



LINUX
---
 
#### Terminar um processo

 >kill PID  
 kill -9 PID

---

#### Encontrar processo executando

>ps -ef | grep nome-do-processo

---

#### Executando via rede e porta

>sudo netstat -plnt

---



===============================================================================================================================================

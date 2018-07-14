# REDES
---
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


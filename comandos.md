# Comandos  {docsify-ignore-all}
---

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



#### Super usuario - nt/Sistema

>psexec -i -s **comando**  

?> ***Sessão em powershell uso em remoto***  
Start-Process -FilePath cmd.exe -Verb Runas -ArgumentList '/k C:\SysinternalsSuite\PsExec.exe -i -s powershell.exe'

<p class="yellow"> ***Pstool aceitar contrato eula por cmd***  
 ferramenta-do-pstool /accepteula
<p>
---



#### - CMD - Criar usuarios e adicionar em grupos

>net user **username password** /add
>net localgroup **grupo usuario** /add

[tutorial](https://www.windows-commandline.com/add-user-from-command-line/)

---




#### - CMD - executar com outro usuário

>runas /noprofile /user:**usuario comando**

---




#### - CMD - propriedades/relatorios windows

>systeminfo

---




#### - CMD - resultado para clipboard - copia

>comando | clip

---



#### - CMD - Comandos chave office key

> * Ativar  
cscript ospp.vbs /inpkey:XXXXX-XXXXX-XXXXX-XXXXX-XXXXX  
cscript.exe ospp.vbs /act  
* Resetar  
cscript.exe ospp.vbs /rearm
* Status da licença - Serial  
cscript ospp.vbs /dstatus
* Remover (usando os 5 últimos characters da licença via /dstatus)
cscript.exe ospp.vbs /unpkey:<last 5 license to be removed>

?> ***CAMINHOS***  
2010  
C:\Program Files\Microsoft Office\Office14  
2013  
C:\Program Files\Microsoft Office\Office15  
2016  
C:\Program Files\Microsoft Office\Office16  

---



#### - CMD -  Copiar mantendo as permissões

> * LOCAL  
robocopy D:\Source E:\Destination /MIR /R:1 /W:1 /COPYALL  
* REDE  
robocopy `\\myserver\e$\data E:\data` /MIR /R:1 /W:1 /COPYALL


---



#### Limpar cache windows installer ( instalações travadas )

>msiexec /UNREGISTER  
>msiexec /REGSERVER

!> ***FIX*** **Deletar registros**   
Erros "Outra instalação está em andamento"  
HKEY_LOCAL_MACHINE \Software\Microsoft\Windows\CurrentVersion\Installer\InProgress  
HKEY_LOCAL_MACHINE \System\CurrentControlSet\Control\Session Manager\PendingFileRenameOperations  

---




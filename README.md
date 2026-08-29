# Qustodio Panel

Interface grafica simples para controlar os servicos do Qustodio (`qengine` e `qupdate`).

Baseado no script `Elevate.cmd` / `MonitorConfig`: fecha, abre, adia o inicio ou elimina os servicos de supervisao, sem precisar mexer na linha de comando.

## Uso

Execute `QustodioPanel.exe`. Se nao estiver como administrador, o programa pede elevacao (UAC) automaticamente.

| Botao        | Acao                                                        |
|--------------|-------------------------------------------------------------|
| Fechar       | Desativa o inicio e para os servicos (`start= disabled`)    |
| Abrir        | Ativa o inicio automatico e inicia os servicos (`start= auto`) |
| Adiar Inicio | Define inicio automatico adiado (`start= delayed-auto`)     |
| Eliminar     | Desativa, para e deleta os servicos (`sc delete`)           |

## Compilar do codigo-fonte

Requer Windows com .NET Framework 4.x (ja incluso no Windows 10/11).

```bat
cd build
"C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe" -nologo -target:winexe -codepage:65001 -optimize+ -win32manifest:app.manifest -win32icon:QustodioPanel.ico -r:System.Windows.Forms.dll -r:System.Drawing.dll -r:System.ServiceProcess.dll -r:System.Management.dll -out:QustodioPanel.exe QustodioPanel.cs
```

O icone pode ser regenerado com `make_icon.ps1` (PowerShell).

## Aviso

Ferramenta para fins de administracao e teste. A remocao dos servicos do Qustodio pode violar politicas da empresa ou contrato de licenca do software de supervisao. Use por sua conta e risco.

## Licenca

[MIT](LICENSE)

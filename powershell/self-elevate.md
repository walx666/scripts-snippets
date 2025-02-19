
# self-elevate a script 

this snippet (and other ones) were found on [https://serverfault.com/questions/11879/gaining-administrator-privileges-in-powershell]

```powershell
#at top of script
if (!
    #current role
    (New-Object Security.Principal.WindowsPrincipal(
        [Security.Principal.WindowsIdentity]::GetCurrent()
    #is admin?
    )).IsInRole(
        [Security.Principal.WindowsBuiltInRole]::Administrator
    )
) {
    #elevate script and exit current non-elevated runtime
    Start-Process `
        -FilePath 'powershell' `
        -ArgumentList (
            #flatten to single array
            '-File', $MyInvocation.MyCommand.Source, $args `
            | %{ $_ }
        ) `
        -Verb RunAs
    exit
}

#example program, this will be ran as admin
$args
Pause
```

## other sources

[https://superuser.com/questions/108207/how-to-run-a-powershell-script-as-administrator]
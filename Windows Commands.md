# Get-WmiObject
This cmdlet is used to get instances of [[WMI System classes]] or information about the available WMI Classes. This cmdlet can be used to start and stop services on local and remote computers, and more. 
## Syntax
```psl
Get-WmiObject [[-Class] <System.String>] [[-Property] <System.String[]>] [-Amended] [-AsJob] [-Authentication {Default | None | Connect | Call | Packet | PacketIntegrity | PacketPrivacy | Unchanged}] [-Authority <System.String>] [-ComputerName <System.String[]>] [-Credential <System.Management.Automation.PSCredential>] [-DirectRead] [-EnableAllPrivileges] [-Filter <System.String>] [-Impersonation {Default | Anonymous | Identify | Impersonate | Delegate}] [-Locale <System.String>] [-Namespace <System.String>] [-ThrottleLimit <System.Int32>] [<CommonParameters>]
```

## Classes

|Class|Description|
|-|-|
|win32_OperatingSystem|There are a variety of ways to find the version and build number of our system. We can easily obtain this information using the win32_OperatingSystem class.|
|Win32_Process|Gives a process listing|
|Win32_Service|Gives a listing of services|
|Win32_Bios|Gives [[BIOS]] Information|

## ComputerName
We can use the ComputerName parameter to get information about remote computers. 


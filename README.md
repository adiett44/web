Get-PnpDevice | Where-Object {$_.InstanceId -like "*DEV_0975*REV_03*"} | Disable-PnpDevice -Confirm:$false




Get-PnpDevice | Where-Object {$_.InstanceId -like "*DEV_0975*REV_03*"} | Enable-PnpDevice -Confirm:$false


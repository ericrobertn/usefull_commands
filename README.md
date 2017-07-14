# usefull_commands

##Copy Group Membershit

Add-ADGroupMember 'GROUP2' -members (Get-ADGroupMember 'GROUP1' | Select -ExpandProperty samaccountname)


##PRTG API CALLS


https://bofi-sd-prtg/api/table.json?content=values&output=json&columns=datetime,value_,coverage&id=40247&noraw=1&usecaption=true&username=prtgsvc&passhash=3075690966

https://bofi-sd-prtg/api/getsensordetails.json?id=40247&username=prtgsvc&passhash=3075690966


##VMWARE GET IPs

get-vm | select Name,@{N="IP Address";E={@($_.guest.IPAddress[0])}}  | Out-GridView
         out-file c:\VM_IP_Addresses.csv


##Find text in file 

find / -iname "*" -type f -print0  |  xargs -0 grep -H "TEXT" | more 

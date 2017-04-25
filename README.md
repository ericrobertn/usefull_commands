# usefull_commands

##Copy Group Membershit

Add-ADGroupMember 'GROUP2' -members (Get-ADGroupMember 'GROUP1' | Select -ExpandProperty samaccountname)


##PRTG API CALLS


https://bofi-sd-prtg/api/table.json?content=values&output=json&columns=datetime,value_,coverage&id=40247&noraw=1&usecaption=true&username=prtgsvc&passhash=3075690966

https://bofi-sd-prtg/api/getsensordetails.json?id=40247&username=prtgsvc&passhash=3075690966

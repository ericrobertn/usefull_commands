# usefull_commands

##Copy Group Membershit

Add-ADGroupMember 'GROUP2' -members (Get-ADGroupMember 'GROUP1' | Select -ExpandProperty samaccountname)

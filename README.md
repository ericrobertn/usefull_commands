################################

################################

##Usefull_commands

##Eric Neudorfer

##       

##Copy Group Membership

Add-ADGroupMember 'GROUP2' -members (Get-ADGroupMember 'GROUP1' | Select -ExpandProperty samaccountname)

##VMWARE GET IPs

get-vm | select Name,@{N="IP Address";E={@($_.guest.IPAddress[0])}}  | Out-GridView

         out-file c:\VM_IP_Addresses.csv


##Find text in file 

find / -iname "*" -type f -print0  |  xargs -0 grep -H "TEXT" | more 


##Find new users

$When = ((Get-Date).AddDays(-90)).Date

Get-ADUser -Filter {whenCreated -ge $When} -Properties whenCreated

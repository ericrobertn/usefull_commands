

## Copy Group Membership

```
Add-ADGroupMember 'GROUP2' -members (Get-ADGroupMember 'GROUP1' | Select -ExpandProperty samaccountname)
```

## VMWARE GET IPs

```
get-vm | select Name,@{N="IP Address";E={@($_.guest.IPAddress[0])}}  | Out-GridView

out-file c:\VM_IP_Addresses.csv
```


## Find text in file 

```
find / -iname "*" -type f -print0  |  xargs -0 grep -H "TEXT" | more 
```


## Find new users

```
$When = ((Get-Date).AddDays(-90)).Date

Get-ADUser -Filter {whenCreated -ge $When} -Properties whenCreated
```
## Get Bash in docker container
```
docker exec -i -t 665b4a1e17b6 /bin/bash #by ID
```

## Stop and remove all containers
```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```

## CMD Ping sweep
```
 for /l %i in (1,1,254) do ping -n 1 -w 100 <first three octets of host network>.%i
```

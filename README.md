$baseDN = "DC=MYMSNGROUP,DC=COM"

$searcher = New-Object DirectoryServices.DirectorySearcher
$searcher.SearchRoot = $searchRoot

# $searcher.Filter = "(&(objectCategory=group)(memberOf=CN=DUO Users,OU=Group,OU=Users,OU=HK,DC=MYMSNGROUP,DC=COM))"
# $searcher.Filter = "(&(member=CN=DUO Users,OU=Group,OU=Users,OU=HK,DC=MYMSNGROUP,DC=COM))"	# Working
# $searcher.Filter = "(&(objectCategory=group)(member=CN=DUO Users,OU=Group,OU=Users,OU=HK,DC=MYMSNGROUP,DC=COM))"	# Working
$searcher.Filter = "(&(objectCategory=group)(member=CN=DUO Users*))"
# $searcher.Filter = "(&(objectCategory=group)(memberOf=CN=DUO Users,OU=Group,OU=Users,OU=HK,DC=MYMSNGROUP,DC=COM))"
# $searcher.Filter = "(&(objectClass=user)(sAMAccountName=*willis*))"
# searcher.Filter = "(&(objectCategory=group))"
# $searcher.Filter = "(&(objectCategory=group)(name=Read-only Domain Controllers))"
# $searcher.Filter = "(&(objectCategory=group)(member=*Willis Chan*))"
# {CN=Denied RODC Password Replication Group,CN=Users,DC=MYMSNGROUP,DC=COM}
# $searcher.Filter = "(&(objectClass=group)(member=*a*))"
# $searcher.Filter = "(&(objectClass=group)(member=CN=$groupName,$baseDN))"
# $searcher.PageSize = 1000

$searchResults = $searcher.FindAll()
$searchResults

# Domain User not able to lookup somehow
# .Properties.samaccountname

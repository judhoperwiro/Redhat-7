## INSTALL IPA CLIENT:
- user: root

execute command:
```
yum install ipa-client
ipa-client-install --mkhomedir
---
Provide the domain name of your IPA server (ex: example.com): dlending.local
Provide your IPA server name (ex: ipa.example.com): kdc2nonprdidm.example.local
Proceed with fixed values and no DNS discovery? [no]: yes
Continue to configure the system with these values? [no]: yes
User authorized to enroll computers: admin
Password for admin@DLENDING.LOCAL: xxxxxx
```

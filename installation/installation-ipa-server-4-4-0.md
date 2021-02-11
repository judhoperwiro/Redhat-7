## INSTALL IPA SERVER:
- user: root

#### 1.) Install Ipa Server
execute command:
```
yum install ipa-server
ipa-server-install --setup-dns


The log file for this installation can be found in /var/log/ipaserver-install.log
==============================================================================
This program will set up the IPA Server.

This includes:
  * Configure a stand-alone CA (dogtag) for certificate management
  * Configure the Network Time Daemon (ntpd)
  * Create and configure an instance of Directory Server
  * Create and configure a Kerberos Key Distribution Center (KDC)
  * Configure Apache (httpd)
  * Configure DNS (bind)

To accept the default shown in brackets, press the Enter key.

Enter the fully qualified domain name of the computer
on which you're setting up server software. Using the form
<hostname>.<domainname>
Example: master.example.com.


Server host name [dc2nonprdidm.example.local]:

Warning: skipping DNS resolution of host dc2nonprdidm.example.local
The domain name has been determined based on the host name.

Please confirm the domain name [example.local]:

The kerberos protocol requires a Realm name to be defined.
This is typically the domain name converted to uppercase.

Please provide a realm name [EXAMPLE.LOCAL]:
Certain directory server operations require an administrative user.
This user is referred to as the Directory Manager and has full access
to the Directory for system management tasks and will be added to the
instance of directory server created for IPA.
The password must be at least 8 characters long.

Directory Manager password:
Password (confirm):

The IPA server requires an administrative user, named 'admin'.
This user is a regular system account used for IPA server administration.

IPA admin password:
Password (confirm):

Checking DNS domain example.local., please wait ...

Do you want to configure DNS forwarders? [yes]:
Following DNS servers are configured in /etc/resolv.conf: 10.0.0.1
Do you want to configure these servers as DNS forwarders? [yes]: no
Enter an IP address for a DNS forwarder, or press Enter to skip:
No DNS forwarders configured
Do you want to search for missing reverse zones? [yes]: yes

The IPA Master Server will be configured with:
Hostname:       dc2nonprdidm.example.local
IP address(es): 10.0.0.1
Domain name:    example.local
Realm name:     EXAMPLE.LOCAL

BIND DNS server will be configured to serve IPA domain with:
Forwarders:       No forwarders
Forward policy:   only
Reverse zone(s):  No reverse zone

Continue to configure the system with these values? [no]: yes

The following operations may take some minutes to complete.
Please wait until the prompt is returned.

Configuring NTP daemon (ntpd)
  [1/4]: stopping ntpd
  [2/4]: writing configuration
  [3/4]: configuring ntpd to start on boot
  [4/4]: starting ntpd
Done configuring NTP daemon (ntpd).
Configuring directory server (dirsrv). Estimated time: 1 minute
  [1/47]: creating directory server user
  [2/47]: creating directory server instance
  [3/47]: updating configuration in dse.ldif
  [4/47]: restarting directory server
  [5/47]: adding default schema
  [6/47]: enabling memberof plugin
  [7/47]: enabling winsync plugin
  [8/47]: configuring replication version plugin
  [9/47]: enabling IPA enrollment plugin
  [10/47]: enabling ldapi
  [11/47]: configuring uniqueness plugin
  [12/47]: configuring uuid plugin
  [13/47]: configuring modrdn plugin
  [14/47]: configuring DNS plugin
  [15/47]: enabling entryUSN plugin
  [16/47]: configuring lockout plugin
  [17/47]: configuring topology plugin
  [18/47]: creating indices
  [19/47]: enabling referential integrity plugin
  [20/47]: configuring certmap.conf
  [21/47]: configure autobind for root
  [22/47]: configure new location for managed entries
  [23/47]: configure dirsrv ccache
  [24/47]: enabling SASL mapping fallback
  [25/47]: restarting directory server
  [26/47]: adding sasl mappings to the directory
  [27/47]: adding default layout
  [28/47]: adding delegation layout
  [29/47]: creating container for managed entries
  [30/47]: configuring user private groups
  [31/47]: configuring netgroups from hostgroups
  [32/47]: creating default Sudo bind user
  [33/47]: creating default Auto Member layout
  [34/47]: adding range check plugin
  [35/47]: creating default HBAC rule allow_all
  [36/47]: adding sasl mappings to the directory
  [37/47]: adding entries for topology management
  [38/47]: initializing group membership
  [39/47]: adding master entry
  [40/47]: initializing domain level
  [41/47]: configuring Posix uid/gid generation
  [42/47]: adding replication acis
  [43/47]: enabling compatibility plugin
  [44/47]: activating sidgen plugin
  [45/47]: activating extdom plugin
  [46/47]: tuning directory server
  [47/47]: configuring directory to start on boot
Done configuring directory server (dirsrv).
Configuring certificate server (pki-tomcatd). Estimated time: 3 minutes 30 seconds
  [1/31]: creating certificate server user
  [2/31]: configuring certificate server instance
  [3/31]: stopping certificate server instance to update CS.cfg
  [4/31]: backing up CS.cfg
  [5/31]: disabling nonces
  [6/31]: set up CRL publishing
  [7/31]: enable PKIX certificate path discovery and validation
  [8/31]: starting certificate server instance
  [9/31]: creating RA agent certificate database
  [10/31]: importing CA chain to RA certificate database
  [11/31]: fixing RA database permissions
  [12/31]: setting up signing cert profile
  [13/31]: setting audit signing renewal to 2 years
  [14/31]: restarting certificate server
  [15/31]: requesting RA certificate from CA
  [16/31]: issuing RA agent certificate
  [17/31]: adding RA agent as a trusted user
  [18/31]: authorizing RA to modify profiles
  [19/31]: authorizing RA to manage lightweight CAs
  [20/31]: Ensure lightweight CAs container exists
  [21/31]: configure certmonger for renewals
  [22/31]: configure certificate renewals
  [23/31]: configure RA certificate renewal
  [24/31]: configure Server-Cert certificate renewal
  [25/31]: Configure HTTP to proxy connections
  [26/31]: restarting certificate server
  [27/31]: migrating certificate profiles to LDAP
  [28/31]: importing IPA certificate profiles
  [29/31]: adding default CA ACL
  [30/31]: adding 'ipa' CA entry
  [31/31]: updating IPA configuration
Done configuring certificate server (pki-tomcatd).
Configuring directory server (dirsrv). Estimated time: 10 seconds
  [1/3]: configuring ssl for ds instance
  [2/3]: restarting directory server
  [3/3]: adding CA certificate entry
Done configuring directory server (dirsrv).
Configuring Kerberos KDC (krb5kdc). Estimated time: 30 seconds
  [1/9]: adding kerberos container to the directory
  [2/9]: configuring KDC
  [3/9]: initialize kerberos container
WARNING: Your system is running out of entropy, you may experience long delays
  [4/9]: adding default ACIs
  [5/9]: creating a keytab for the directory
  [6/9]: creating a keytab for the machine
  [7/9]: adding the password extension to the directory
  [8/9]: starting the KDC
  [9/9]: configuring KDC to start on boot
Done configuring Kerberos KDC (krb5kdc).
Configuring kadmin
  [1/2]: starting kadmin
  [2/2]: configuring kadmin to start on boot
Done configuring kadmin.
Configuring ipa_memcached
  [1/2]: starting ipa_memcached
  [2/2]: configuring ipa_memcached to start on boot
Done configuring ipa_memcached.
Configuring ipa-otpd
  [1/2]: starting ipa-otpd
  [2/2]: configuring ipa-otpd to start on boot
Done configuring ipa-otpd.
Configuring ipa-custodia
  [1/5]: Generating ipa-custodia config file
  [2/5]: Making sure custodia container exists
  [3/5]: Generating ipa-custodia keys
  [4/5]: starting ipa-custodia
  [5/5]: configuring ipa-custodia to start on boot
Done configuring ipa-custodia.
Configuring the web interface (httpd). Estimated time: 1 minute
  [1/21]: setting mod_nss port to 443
  [2/21]: setting mod_nss cipher suite
  [3/21]: setting mod_nss protocol list to TLSv1.0 - TLSv1.2
  [4/21]: setting mod_nss password file
  [5/21]: enabling mod_nss renegotiate
  [6/21]: adding URL rewriting rules
  [7/21]: configuring httpd
  [8/21]: configure certmonger for renewals
  [9/21]: setting up httpd keytab
  [10/21]: setting up ssl
  [11/21]: importing CA certificates from LDAP
  [12/21]: setting up browser autoconfig
  [13/21]: publish CA cert
  [14/21]: clean up any existing httpd ccache
  [15/21]: configuring SELinux for httpd
  [16/21]: create KDC proxy user
  [17/21]: create KDC proxy config
  [18/21]: enable KDC proxy
  [19/21]: restarting httpd
  [20/21]: configuring httpd to start on boot
  [21/21]: enabling oddjobd
Done configuring the web interface (httpd).
Applying LDAP updates
Upgrading IPA:
  [1/9]: stopping directory server
  [2/9]: saving configuration
  [3/9]: disabling listeners
  [4/9]: enabling DS global lock
  [5/9]: starting directory server
  [6/9]: upgrading server
  [7/9]: stopping directory server
  [8/9]: restoring configuration
  [9/9]: starting directory server
Done.
Restarting the directory server
Restarting the KDC
Configuring DNS (named)
  [1/11]: generating rndc key file
WARNING: Your system is running out of entropy, you may experience long delays
  [2/11]: adding DNS container
  [3/11]: setting up our zone
  [4/11]: setting up our own record
  [5/11]: setting up records for other masters
  [6/11]: adding NS record to the zones
  [7/11]: setting up kerberos principal
  [8/11]: setting up named.conf
  [9/11]: setting up server configuration
  [10/11]: configuring named to start on boot
  [11/11]: changing resolv.conf to point to ourselves
Done configuring DNS (named).
Configuring DNS key synchronization service (ipa-dnskeysyncd)
  [1/7]: checking status
  [2/7]: setting up bind-dyndb-ldap working directory
  [3/7]: setting up kerberos principal
  [4/7]: setting up SoftHSM
  [5/7]: adding DNSSEC containers
  [6/7]: creating replica keys
  [7/7]: configuring ipa-dnskeysyncd to start on boot
Done configuring DNS key synchronization service (ipa-dnskeysyncd).
Restarting ipa-dnskeysyncd
Restarting named
Updating DNS system records
Restarting the web server
Configuring client side components
Using existing certificate '/etc/ipa/ca.crt'.
Client hostname: dc2nonprdidm.example.local
Realm: EXAMPLE.LOCAL
DNS Domain: example.local
IPA Server: dc2nonprdidm.example.local
BaseDN: dc=example,dc=local

Skipping synchronizing time with NTP server.
New SSSD config will be created
Configured sudoers in /etc/nsswitch.conf
Configured /etc/sssd/sssd.conf
trying https://dc2nonprdidm.example.local/ipa/json
Forwarding 'schema' to json server 'https://dc2nonprdidm.example.local/ipa/json'
trying https://dc2nonprdidm.example.local/ipa/session/json
Forwarding 'ping' to json server 'https://dc2nonprdidm.example.local/ipa/session/json'
Forwarding 'ca_is_enabled' to json server 'https://dc2nonprdidm.example.local/ipa/session/json'
Systemwide CA database updated.
Adding SSH public key from /etc/ssh/ssh_host_rsa_key.pub
Adding SSH public key from /etc/ssh/ssh_host_ed25519_key.pub
Adding SSH public key from /etc/ssh/ssh_host_ecdsa_key.pub
Forwarding 'host_mod' to json server 'https://dc2nonprdidm.example.local/ipa/session/json'
SSSD enabled
Configured /etc/openldap/ldap.conf
Configured /etc/ssh/ssh_config
Configured /etc/ssh/sshd_config
Configuring example.local as NIS domain.
Client configuration complete.

==============================================================================
Setup complete

Next steps:
        1. You must make sure these network ports are open:
                TCP Ports:
                  * 80, 443: HTTP/HTTPS
                  * 389, 636: LDAP/LDAPS
                  * 88, 464: kerberos
                  * 53: bind
                UDP Ports:
                  * 88, 464: kerberos
                  * 53: bind
                  * 123: ntp

        2. You can now obtain a kerberos ticket using the command: 'kinit admin'
           This ticket will allow you to use the IPA tools (e.g., ipa user-add)
           and the web user interface.

Be sure to back up the CA certificates stored in /root/cacert.p12
These files are required to create replicas. The password for these
files is the Directory Manager password
```

#### 2.) Check status Ipa Server
execute command:
```
service ipa status

Redirecting to /bin/systemctl status  ipa.service
● ipa.service - Identity, Policy, Audit
   Loaded: loaded (/usr/lib/systemd/system/ipa.service; enabled; vendor preset:                                                                              disabled)
   Active: active (exited) since Fri 2018-03-30 15:39:45 ICT; 1min 8s ago
  Process: 25339 ExecStart=/usr/sbin/ipactl start (code=exited, status=0/SUCCESS                                                                             )
 Main PID: 25339 (code=exited, status=0/SUCCESS)

Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting kadmin Service
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting named Service
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting ipa_memcached S...
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting httpd Service
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting ipa-custodia Se...
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting ntpd Service
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting pki-tomcatd Ser...
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting ipa-otpd Service
Mar 30 15:39:45 dc2nonprdidm.example.local ipactl[25339]: Starting ipa-dnskeysyncd...
Mar 30 15:39:45 dc2nonprdidm.example.local systemd[1]: Started Identity, Policy, A...
Hint: Some lines were ellipsized, use -l to show in full.
[root@dc2nonprdidm log]# ps -ef |grep ipa
apache    24133      1  0 15:37 ?        00:00:00 /usr/bin/memcached -d -s /var/run/ipa_memcached/ipa_memcached -u apache -m 64 -c 1024 -P /var/run/ipa_memcached/ipa_memcached.pid
root      24194      1  0 15:37 ?        00:00:00 /usr/bin/python2 /usr/sbin/custodia /etc/ipa/custodia/custodia.conf
ods       25014      1  1 15:39 ?        00:00:01 /usr/bin/python2 /usr/libexecipa/ipa-dnskeysyncd
apache    25081  25072  1 15:39 ?        00:00:02 (wsgi:ipa)      -DFOREGROUND
apache    25082  25072  2 15:39 ?        00:00:02 (wsgi:ipa)      -DFOREGROUND
root      25395  20893  0 15:41 pts/0    00:00:00 grep --color=auto ipa
[root@dc2nonprdidm log]#
[root@dc2nonprdidm log]#
[root@dc2nonprdidm log]#
[root@dc2nonprdidm log]# ipa --version
VERSION: 4.4.0, API_VERSION: 2.213
```

#### 3.) Open port for IPA Server
execute command:
```
firewall-cmd --zone=public --add-port=123/udp --permanent
firewall-cmd --permanent --add-service={ntp,http,https,ldap,ldaps,kerberos,kpasswd,dns}
firewall-cmd --reload
```

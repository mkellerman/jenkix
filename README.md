# jenkix
Zabbix Agent - Jenkins

# Dependencies
## Packages
* ksh
* jq
* curl

### Debian/Ubuntu

    #~ sudo apt install ksh jq curl
    #~

### Red Hat

    #~ sudo yum install ksh curl jq
    #~

# Deploy
The username and the password can be empty if jenkins has the read only option enable.
Default variables:

NAME|VALUE
----|-----
JENKINS_URL|http://localhost:8080
JENKINS_USER|<empty>
JENKINS_PASS|<empty>

*Note: this variables has to be saved in the config file (jenkix.conf) in the same directory than the script.*

## Zabbix

    #~ git clone https://github.com/sergiotocalini/jenkix.git
    #~ sudo ./jenkix/deploy_zabbix.sh "<JENKINS_URL>" "<JENKINS_USER>" "<JENKINS_PASS>"
    #~ sudo systemctl restart zabbix-agent
    
*Note: the installation has to be executed on the zabbix agent host and you have to import the template on the zabbix web. The default installation directory is /etc/zabbix/scripts/agentd/jenkix*

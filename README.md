# Hubzilla for YunoHost

[![Integration level](https://dash.yunohost.org/integration/hubzilla.svg)](https://ci-apps.yunohost.org/jenkins/job/hubzilla%20%28Community%29/lastBuild/consoleFull)

[![Install Hubzilla with YunoHost](https://install-app.yunohost.org/install-with-yunohost.png)](https://install-app.yunohost.org/?app=hubzilla)
<br>
Version: **4.0.1**

### Interesting links

- [YunoHost project](https://yunohost.org)
- [Hubzilla website](http://hubzilla.org)
- [Hubzilla code on Framagit](https://framagit.org/hubzilla/core)
- [Hubzilla addons on Framagit](https://framagit.org/hubzilla/addons)


## Hubzilla
[Hubzilla](http://hubzilla.org) is a powerful platform for creating interconnected websites featuring a decentralized identity, communications, and permissions framework built using common webserver technology.



## This app claims following features:
- [X] Ldap integration
- [X] Multi-instance
- [X] Adeed php.log in the root folder for debugging php, with logrotate applied on it (can be accesssed by **admin->logs** and entering the **php.log**).
- [X] Fail2ban 

## Important Notes

Before installing, read the [Hubzilla installation instructions](https://framagit.org/hubzilla/core/blob/master/install/INSTALL.txt) for important information about

- SSL certificate validation requirement (now with support for [Let's Encrypt!](https://letsencrypt.org)). See Installation section below.
- Dedicated domain (must install under web root like **https://hub.example.com/** not **https://example.com/hub/** )


## Installation

### Register a new domain and add it to YunoHost
Hubzilla requires a dedicated domain, so obtain one and add it using the YunoHost admin panel. **Domains -> Add domain**. As Hubzilla uses the full domain and is installed on the root, you can create a subdomain such as hubzilla.domain.tld. Don't forget to update your DNS if you manage them manually.

#### YunoHost >= 2.5 :
Once the dedicated domain has been added to YunoHost, go again to the admin panel, go to domains then select your domain and click on "Install Let's Encrypt certificate".

### Install the Hubzilla application
Use the YunoHost admin panel to install Hubzilla by entering the GitHub repo address in the custom app URL

		https://github.com/YunoHost-Apps/hubzilla_ynh

Make sure to select your domain from the previous section as the application domain.

**For admin rights**: When installation is complete, you will need to visit your new hub's page and login with the **admin account username** which was entered at the time of installation process. You should then be able to create your first channel and have the admin rights for the hub.

**For normal YunoHost users:** Normal LDAP users can login through Ldap authentication and create there channels.

**If the admin cannot access the admin settings:** If the admin cannot access the admin settings at `https://hubzilla.example.com/admin` or you want to grant admin rights to any other user(s) on the hub, then you have to **manually add 4096** to the **account_roles** under **accounts** for that user in the **database through phpMYAdmin**.

**For logs:**: Go to **admin->logs** and enter the file name **php.log**. 

---
description: MelodyMine Website and Plugin Installation
---

# 💡 Installation

## Installation Video

{% embed url="https://www.youtube.com/watch?v=wERECLih8Oc" %}

## Installation Steps

{% hint style="warning" %}
Before starting the installation, you need two things:

* Having a Linux Server.
* Having a domain connected to the Linux Server.
{% endhint %}

{% hint style="info" %}
If you are using Cloudflare, be sure to turn off the proxied option in your domain settings.
{% endhint %}

{% hint style="info" %}
Make sure to open port `3477` for the `COTURN` server in your firewall settings, both for TCP and UDP protocols.
{% endhint %}

After having these requirements, you can start the installation.

### Step 1: Clone the MelodyMine GitHub repository

```bash
git clone https://github.com/Vallerian/MelodyMine.git
```

### Step 2: Navigate to the path: `MelodyMine/web/docker`

```bash
cd MelodyMine/web/docker
```

### Step 3: Rename the `.env` file

```bash
mv .env.example .env
```

### Step 4: Edit the `.env` file

```bash
nano .env
```

{% hint style="info" %}
Contents of the `.env` file:

```apl
# The domain you have connected to your Linux server, like example.com
DOMAIN=

# The IP address of your Linux server
SERVER_IP= 

# The port you choose for your Next.js (UI) client, make sure this port is open in your firewall.
CLIENT_PORT=

# The port you choose for your WebSocket server, ensure this port is open in your firewall.
SERVER_PORT=

# A random string of characters that you should generate and keep secret, do not share this with anyone else.
SECRET_KEY=

# A random string of characters that you should generate and keep secret, do not share this with anyone else.
PLUGIN_KEY= 

# A random string of characters that you should generate and keep secret, do not share this with anyone else.
CLIENT_KEY= 

# your database config.
DATABASE_HOST=
DATABASE_PORT=
DATABASE_USERNAME=
DATABASE_PASSWORD= 
DATABASE_NAME=
```
{% endhint %}

{% hint style="warning" %}
In the .env file, create a new user for the database and don't use `localhost` and `root`. Instead, use the Server IP and the new user you created along with the password.
{% endhint %}

### Step 5: Save the .env file and exit

Do: `[ctrl + x]` and then `[y]` and `[Enter]`

### Step 6: Install MelodyMine

```bash
sudo sh start.sh
```

{% hint style="info" %}
During the MelodyMine installation, if prompted, answer 'yes' or 'no'. Always choose 'yes' to proceed. If any errors occur during the installation, such as port 80 being busy, pay attention and resolve them adn then run sudo `sh start.sh`.
{% endhint %}

{% hint style="success" %}
After installing MelodyMine, ensure that both the client and server are fully installed and operational.\
\
Server address: `https://[DOMAIN]:[SERVER_PORT]`\
Client address: `https://[DOMAIN]:[CLIENT_PORT]`
{% endhint %}

### Step 7: Download the MelodyMine plugin

Visit the following link to download the latest version of MelodyMine: [https://github.com/Vallerian/MelodyMine/releases](https://github.com/Vallerian/MelodyMine/releases)

### Step 8: Install the MelodyMine plugin

Place the downloaded plugin file into your server folder and restart the server once to initialize the plugin files.

### Step 9: Configure the plugin's database

Navigate to the MelodyMine folder in the plugins folder of your server and open the `mysql.yml` file. Configure it exactly like the database config in the `.env` file.

{% hint style="success" %}
&#x20;**The values below should match:**

* DATABASE\_HOST => 'host'
* DATABASE\_PORT => 'port'
* DATABASE\_USERNAME => 'username'
* DATABASE\_PASSWORD => 'password
* DATABASE\_NAME => 'database'
{% endhint %}

### Step 10: Configure the plugin's settings

Open the `settings.yml` file in the MelodyMine folder within the plugins folder of your server and configure the `initial_configs` similar to the `.env` file.

{% hint style="success" %}
**The values below should match:**

* DOMAIN= 'domain'
* CLIENT\_PORT= 'client\_port'
* SERVER\_PORT= 'server\_port'
* PLUGIN\_KEY= 'plugin\_key'
{% endhint %}

The installation is now complete. You can test MelodyMine by entering your server and using the command `/melodymine start link` to join the voice chat.

{% hint style="info" %}
**If you encounter any issues during the MelodyMine installation, feel free to join the Discord support channel and seek assistance** [**Discord**](https://discord.gg/CBua8YectX)**.**
{% endhint %}

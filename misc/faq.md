# 📄 FAQ

### How can i change the server IP and contact us link in website?

To perform this task, you need to enter the path `web/client/src` and open the file `config.ts`. In this file, you can configure related settings.

{% hint style="info" %}
Please note that when you make changes to the `config.ts` file or any other file in the client, you need to rebuild the Docker image and remove the Docker volume for the client to clear caches.\


To perform this task, follow these commands in sequence after navigating to the directory `web/docker`:

```bash
sudo sh stop.sh
sudo docker rm client
sudo docker rmi docker-client
sudo sh start.sh
```
{% endhint %}

***

### How can add new language to MelodyMine?

To do this task, you need to enter the MelodyMine plugin folder and open the languages folder. In this folder, you can see a list of languages supported by MelodyMine.

&#x20;If the language you want to add is not among these languages, you can't simply add it. Instead, you need to copy the `en_US.yml` file and only modify the messages in this file to your desired language.&#x20;

After completing this task, you can submit a pull request on [MelodyMine's GitHub repository](https://github.com/Vallerian/MelodyMine/pulls) to add the file to the plugin.

&#x20;Alternatively, you can join the MelodyMine [Discord](https://discord.gg/CBua8YectX) server and send the language file directly to the developers for inclusion.

***

### How can I change or stop using port 80 for MelodyMine?

MelodyMine requires using port 80 to obtain an SSL certificate for your domain. This process only happens once.&#x20;

After that, if you restart MelodyMine and the SSL certificate files for your domain are located in the `web/docker/certbot/live` path, port 80 will no longer be occupied by MelodyMine.&#x20;

However, if the SSL files do not exist, it means there is an issue with your domain, and you need to resolve the SSL certificate acquisition problem before proceeding.

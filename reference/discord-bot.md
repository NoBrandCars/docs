# Discord Bot

{% hint style="info" %}
Invite the "No Brand Cars" discord bot [here](https://discord.com/oauth2/authorize?client\_id=1095466017087574056\&scope=bot%20applications.commands%20guilds\&permissions=139586938952)
{% endhint %}

#### Linking FiveM server with the Discord bot

> Enter the following command into the FiveM server console:
>
> linkDiscord <[server id](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID)>

{% embed url="https://www.youtube.com/watch?v=OdlK55LZb60" %}

| Command | Function                                                                           |
| ------- | ---------------------------------------------------------------------------------- |
| auth    | Connects your FiveM server to your Discord server                                  |
| map     | Changes the current map of the Maze Bank Arena ([EasyMapChange](easy-map-change/)) |
| script  | Manages your scripts (EventMode, ...)                                              |

#### Firewall

{% hint style="info" %}
Make sure that the following IP addresses are allowed in the firewall to prevent timeouts
{% endhint %}

<table><thead><tr><th>Server</th><th width="176.33333333333331">IP</th><th>Usage</th></tr></thead><tbody><tr><td>HETZNER NBC-1</td><td>128.140.38.32</td><td>POST requests to FiveM server</td></tr></tbody></table>

<figure><img src="../.gitbook/assets/firewall (1).png" alt=""><figcaption><p>Timeout when performing an action</p></figcaption></figure>

#### Permissions

{% hint style="info" %}
By default, users in the Discord server with administrator rights can use the commands.

[To create / change your own permissions follow these instructions from Discord](https://support.discord.com/hc/en-us/articles/4644915651095-Command-Permissions)
{% endhint %}

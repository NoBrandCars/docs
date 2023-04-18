# Update

## How to update Rocket-Soccer

Login to [Keymaster](https://keymaster.fivem.net/), navigate to your purchases Assets and redownload Rocket-Soccer.

Replace your old ressource with the new one and make sure to check [settings.lua](settings.md) for possible changes.

{% hint style="info" %}
Updates for all our scripts are free of charge!
{% endhint %}

<details>

<summary>Update 1.0.5</summary>

* Most wished change implemented: **50% smaller Octane!** (included for free)
* Readjusted the **jump** function to adapt the new vehicle size
* Readjusted the **drift** function to adapt the new vehicle size
* Readjusted the **boost** function to adapt the new vehicle size
* Implemented choice to choose either **2D- or 3D-text**
* Discord Bot now supports **event-mode**
* Discord Bot now supports **adding** players to queue
* Discord Bot now supports **remove** players from queue
* Optimized reset ball logic to reset ball in case it leaves the playing field

#### Its important to update your [settings.lua](settings.md) from the last update!

</details>

<details>

<summary>Update 1.0.4</summary>

* NPC-PED logic is now handled clientside rather then serverside to prevent despawn of NPC's.
* [Authentification ](../authentication-server.md)added for our own [Discord Bot](../discord-bot.md).
* Fixxed a ConVar error which had no impact on script functionality, but hey now its gone.

#### Its important to update your [settings.lua](settings.md) from the last update!

</details>

<details>

<summary>Update 1.0.3</summary>

* Added more options to the API.
* API now allows for calls to [objects](exports-api-communication.md#spawn-a-object).
* API now allows for calls for [vehicles](exports-api-communication.md#spawn-a-vehicle).
* Added Authentication for API Server.
* Games are now streamable over web.
* The octane car is now included in the ressource.
* Smaller tweaks & fixxes.

</details>

<details>

<summary>Update 1.0.2</summary>

* **Fixxed issue** when a player receives a game-crash when beeing in a round of Rocket-Soccer. _(Round would not end correctly)._
* **Fixed issue** when a player disconnects during in a round of Rocket-Soccer _(Round would end to early)_
* Changed the **default respawn position** (after a round ends) outside of the Arena Map. _(Players would get invisibility sometimes)._
* **Optimized loops** and **improved performance** of the script.

</details>

<details>

<summary>Update 1.0.1</summary>

![](<../../.gitbook/assets/image (10).png>)

Performance improvement from 0.03 to 0.00 ms in idle (Outside [Maze Bank Arena](https://fivem.gabzv.com/package/5567774))

</details>


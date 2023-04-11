---
description: All Functions only accessible at server side
---

# Exports (API Communication)

{% hint style="info" %}
**Good to know:** You can use all functions as event or manupulation of the logic
{% endhint %}

## Functions

#### <mark style="color:red;">Send a notify</mark>

{% tabs %}
{% tab title="Example (1)" %}
```lua
exports["RocketSoccer"]:Notify(source, message)
```
{% endtab %}

{% tab title="Parameters (1)" %}
| Name    | Type   |
| ------- | ------ |
| source  | int    |
| message | string |
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Start a round</mark>

{% tabs %}
{% tab title="Example (2)" %}
```lua
exports["RocketSoccer"]:StartRound(sourceOrange, sourceBlue)
```
{% endtab %}

{% tab title="Parameters (2)" %}
| Name         | Type |
| ------------ | ---- |
| sourceOrange | int  |
| sourceBlue   | int  |
{% endtab %}

{% tab title="Manipulation (2)" %}
{% hint style="info" %}
If the return of the function is <mark style="background-color:orange;">**false**</mark>, the round will not start, but if it is <mark style="background-color:green;">**true**</mark>, it will.
{% endhint %}
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Stop a round</mark>

{% tabs %}
{% tab title="Example (3)" %}
```lua
exports["RocketSoccer"]:StopRound()
```
{% endtab %}

{% tab title="Manipulation (3)" %}
If the return of the function is <mark style="background-color:orange;">**false**</mark>, the round will not stop, but if it is <mark style="background-color:green;">**true**</mark>, it will.
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Get a player name</mark>

{% tabs %}
{% tab title="Example (4)" %}
```lua
exports["RocketSoccer"]:GetPlayerName(source)
```
{% endtab %}

{% tab title="Parameters (4)" %}
| Name   | Type |
| ------ | ---- |
| source | int  |
{% endtab %}

{% tab title="Manipulation (4)" %}
Change the return of the function to a different name (this will be displayed in the DUI)
{% endtab %}

{% tab title="Return (4)" %}
The respective player name (Changeable by "[Manipulation](exports-api-communication.md#manipulation-4)")
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Check if player is allowed to join the queue</mark>

{% tabs %}
{% tab title="Example (5)" %}
```lua
exports["RocketSoccer"]:IsPlayerAllowed(source)
```
{% endtab %}

{% tab title="Parameters (5)" %}
| Name   | Type |
| ------ | ---- |
| source | int  |


{% endtab %}

{% tab title="Manipulation (5)" %}
If <mark style="background-color:green;">true</mark> is returned, the player can be added to the respective queue.

Note that you have to add the player to the queue yourself:&#x20;

```lua
queue[team][source] = true
```
{% endtab %}

{% tab title="Return (5)" %}
<mark style="background-color:green;">true</mark> or <mark style="background-color:orange;">false</mark>
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Add a player to the queue</mark>

{% tabs %}
{% tab title="Example (6)" %}
```lua
exports["RocketSoccer"]:AddPlayerToQueue(source, team, force)
```
{% endtab %}

{% tab title="Parameters (6)" %}
| Name   | Type                                                                                                              |
| ------ | ----------------------------------------------------------------------------------------------------------------- |
| source | int                                                                                                               |
| team   | string (<mark style="background-color:blue;">blue</mark> or <mark style="background-color:orange;">orange</mark>) |
| force  | boolean                                                                                                           |
{% endtab %}

{% tab title="Manipulation (6)" %}
The return is **only** relevant for further processing of the function.

The actual logic is:

```lua
queue[team][source] = true / false
```
{% endtab %}

{% tab title="Return (6)" %}
<mark style="background-color:green;">true</mark> or <mark style="background-color:orange;">false</mark>
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Check if player is in the queue of a team</mark>

{% tabs %}
{% tab title="Example (7)" %}
```lua
exports["RocketSoccer"]:IsPlayerInQueue(source)
```
{% endtab %}

{% tab title="Parameters (7)" %}
| Name   | Type |
| ------ | ---- |
| source | int  |
{% endtab %}

{% tab title="Manipulation (7)" %}
Change the return of the function to change the logic:

<mark style="background-color:green;">true</mark> / <mark style="background-color:orange;">false</mark>
{% endtab %}

{% tab title="Return (7)" %}
<mark style="background-color:green;">true</mark> or <mark style="background-color:orange;">false</mark>
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Remove a player from the queue</mark>

{% tabs %}
{% tab title="Example (8)" %}
```lua
exports["RocketSoccer"]:RemovePlayerFromQueue(source)
```
{% endtab %}

{% tab title="Parameters (8)" %}
| Name   | Type |
| ------ | ---- |
| source | int  |
{% endtab %}

{% tab title="Manipulation (8)" %}
The following line is the deciding logic which a player removes.

Modify these lines to detect manipulation

```lua
queue.blue[source] = nil
queue.orange[source] = nil
```
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Get the current round</mark>

{% tabs %}
{% tab title="Example (9)" %}
```lua
exports["RocketSoccer"]:GetCurrentRound()
```
{% endtab %}

{% tab title="Return (9)" %}
If no round is started, the return value is <mark style="color:yellow;">nil</mark>

Otherwise the <mark style="color:purple;">round model</mark> is returned

```lua
{
    type = 0, -- 0 = Starting - 1 = In Game
    time = Settings.Round.Wait,
    url = Settings.Logo,
    ball = object,
    players = {
        orange = {
            source = playerOrange,
            ped = GetPlayerPed(playerOrange),
            vehicle = carOrange,
            name = Settings.API.GetPlayerName(playerOrange),
            score = 0
        },
        blue = {
            source = playerBlue,
            ped = GetPlayerPed(playerBlue),
            vehicle = carBlue,
            name = Settings.API.GetPlayerName(playerBlue),
            score = 0
        }
    }
}
```
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Spawn a vehicle</mark>

{% tabs %}
{% tab title="Example (10)" %}
```lua
exports["RocketSoccer"]:CreateVehicle(model, vector)
```
{% endtab %}

{% tab title="Parameters (10)" %}
| Name   | Type                                                                                               |
| ------ | -------------------------------------------------------------------------------------------------- |
| model  | int / string                                                                                       |
| vector | table ([vector3](https://docs.fivem.net/docs/scripting-reference/runtimes/lua/functions/vector3/)) |
{% endtab %}

{% tab title="Manipulation (10)" %}
Change the following line to return a different variable on return.

_This can help if there are problems with an anticheat._

Note that the correct data type must be returned (see [Return](exports-api-communication.md#return-10)[ Tab](exports-api-communication.md#return-10)).

```lua
return CreateVehicle(model, vector, true, false)
```
{% endtab %}

{% tab title="Return (10)" %}
An entity of the type [Vehicle](https://docs.fivem.net/docs/scripting-manual/networking/ids/#entities) is returned
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Spawn a Object</mark>

{% tabs %}
{% tab title="Example (11)" %}
```lua
exports["RocketSoccer"]:CreateObject(model, vector)
```
{% endtab %}

{% tab title="Parameters (11)" %}
| Name   | Type                                                                                               |
| ------ | -------------------------------------------------------------------------------------------------- |
| model  | int / string                                                                                       |
| vector | table ([vector3](https://docs.fivem.net/docs/scripting-reference/runtimes/lua/functions/vector3/)) |
{% endtab %}

{% tab title="Manipulation (11)" %}
Change the following line to return a different variable on return.

_This can help if there are problems with an anticheat._

Note that the correct data type must be returned (see [Return](exports-api-communication.md#return-10)[ Tab](exports-api-communication.md#return-10)).

```lua
return CreateObject(model, vector, true, false, false)
```
{% endtab %}

{% tab title="Return (11)" %}
An entity of the type [Object](https://docs.fivem.net/docs/scripting-manual/networking/ids/#entities) is returned
{% endtab %}
{% endtabs %}

## Events

#### <mark style="color:red;">OnExploit</mark>

{% tabs %}
{% tab title="Explanation (12)" %}
Called when trying to tune up your vehicle using the internal trigger and it is not a Rocket Soccer vehicle.
{% endtab %}

{% tab title="Parameters (12)" %}
| Name        | Type                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------- |
| playerPedId | int ([Ped](https://docs.fivem.net/docs/scripting-manual/networking/ids/#ped))               |
| netID       | int ([Network ID](https://docs.fivem.net/docs/scripting-manual/networking/ids/#network-id)) |
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">OnWinning</mark>

{% tabs %}
{% tab title="Explanation (13)" %}
Called when the round ends.

**Reasons:**

* Time expired
* A team leaves the server
{% endtab %}

{% tab title="Parameters (13)" %}
|      |                                                                                                                   |
| ---- | ----------------------------------------------------------------------------------------------------------------- |
| team | string (<mark style="background-color:blue;">blue</mark> or <mark style="background-color:orange;">orange</mark>) |
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">OnGoal</mark>

{% tabs %}
{% tab title="Explanation (14)" %}
Called when a team scores a goal
{% endtab %}

{% tab title="Parameters (14)" %}
|      |                                                                                                                   |
| ---- | ----------------------------------------------------------------------------------------------------------------- |
| team | string (<mark style="background-color:blue;">blue</mark> or <mark style="background-color:orange;">orange</mark>) |
{% endtab %}
{% endtabs %}

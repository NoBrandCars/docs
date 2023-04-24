---
description: All Functions only accessible at server side
---

# Exports (API Communication)

{% hint style="info" %}
**Good to know:** You can use all functions as event or manupulation of the logic
{% endhint %}

## Functions

#### <mark style="color:red;">Add channel to settings</mark>

{% tabs %}
{% tab title="Example (1)" %}
```lua
exports["EasyGPS"]:AddChannel(array)
```
{% endtab %}

{% tab title="Parameters (1)" %}
| Name  | Type                                            |
| ----- | ----------------------------------------------- |
| array | [channel](exports-api-communication.md#channel) |
{% endtab %}

{% tab title="Manipulation (1)" %}
If <mark style="background-color:orange;">false</mark> is returned, the code is interrupted and the channel is not **added**.

If it is set to <mark style="background-color:green;">true</mark>, the complete code will continue and the **channel will be added**.
{% endtab %}

{% tab title="Return (1)" %}
The **index** of the channel in the array (<mark style="color:green;">int</mark>)
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Deactivate a channel from settings</mark>

{% tabs %}
{% tab title="Example (2)" %}
```lua
exports["EasyGPS"]:DeactivateChannel(key)
```
{% endtab %}

{% tab title="Parameters (2)" %}
| Name | Type                                  |
| ---- | ------------------------------------- |
| key  | <mark style="color:green;">int</mark> |
{% endtab %}

{% tab title="Manipulation (2)" %}
If <mark style="background-color:orange;">false</mark> is returned, the code is interrupted and the channel is not **deactivated**.

If it is set to <mark style="background-color:green;">true</mark>, the complete code will continue and the **channel will be deactivated**.
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Modify a channel from settings</mark>

{% tabs %}
{% tab title="Example (3)" %}
```lua
exports["EasyGPS"]:ModifyChannel(key, array)
```
{% endtab %}

{% tab title="Parameters (3)" %}
| Name  | Type                                            |
| ----- | ----------------------------------------------- |
| key   | <mark style="color:green;">int</mark>           |
| array | [channel](exports-api-communication.md#channel) |
{% endtab %}

{% tab title="Manipulation (3)" %}
If <mark style="background-color:orange;">false</mark> is returned, the code is interrupted and the channel is not **changed**.

If it is set to <mark style="background-color:green;">true</mark>, the complete code will continue and the **channel will be changed**.
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Get all channels from settings</mark>

{% tabs %}
{% tab title="Example (4)" %}
```lua
exports["EasyGPS"]:GetChannels()
```
{% endtab %}

{% tab title="Return (4)" %}
Array of [Channels](exports-api-communication.md#channel) (<mark style="color:blue;">channel\[]</mark>)
{% endtab %}
{% endtabs %}

## Events

#### <mark style="color:red;">OnToggle</mark>

{% tabs %}
{% tab title="Explanation (5)" %}
Called when the blip of an entity is set or removed. (Listed after all checks)
{% endtab %}

{% tab title="Parameters (5)" %}
| Name      | Type                                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------------------- |
| entity    | int ([Entity](https://docs.fivem.net/docs/scripting-manual/networking/ids/#entities))                         |
| channelID | int (Index of [channel](exports-api-communication.md#channel) in <mark style="color:blue;">channel\[]</mark>) |
| state     | <mark style="background-color:green;">true</mark> / <mark style="background-color:orange;">false</mark>       |
{% endtab %}
{% endtabs %}

## Channel

```lua
{
    IsPlayerAllowedToShow = function (entity, player)
        return true / false
    end,
    IsPlayerAllowedToToggle = function (entity, player, client)
        return true / false
    end,
    Checker = function (ped)
        return entity, true / false
    end,
    Blip = function (blip)
        -- Manage Blip
    end
}
```

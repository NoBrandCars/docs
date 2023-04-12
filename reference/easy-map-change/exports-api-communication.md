---
description: All Functions only accessible at server side
---

# Exports (API Communication)

{% hint style="info" %}
**Good to know:** You can use all functions as event or manupulation of the logic
{% endhint %}

## Functions

#### <mark style="color:red;">Change the map</mark>

{% tabs %}
{% tab title="Example (1)" %}
```lua
exports["EasyMapChange"]:ChangeMap(map, player)
```
{% endtab %}

{% tab title="Parameters (1)" %}
| Name   | Type                            |
| ------ | ------------------------------- |
| map    | string ([Maps](maps.md))        |
| player | int (source or discord user id) |
{% endtab %}

{% tab title="Manipulation (1)" %}
IIf <mark style="background-color:orange;">false</mark> is returned, the code is interrupted and the **map** is **not changed**.

If it is set to <mark style="background-color:green;">true</mark>, the complete code will continue and the **map will change**.
{% endtab %}

{% tab title="Return (1)" %}
<mark style="background-color:green;">true</mark> or <mark style="background-color:orange;">false</mark>
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Get the current map</mark>

{% tabs %}
{% tab title="Example (2)" %}
```lua
exports["EasyMapChange"]:GetCurrentMap()
```
{% endtab %}

{% tab title="Return (2)" %}
Returns a <mark style="background-color:purple;">string / enum</mark> ([Maps](maps.md))
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Check if player is allowed to use the command</mark>

{% tabs %}
{% tab title="Example (3)" %}
```lua
exports["EasyMapChange"]:IsPlayerAllowed(source)
```
{% endtab %}

{% tab title="Parameters (3)" %}
| Name   | Type |
| ------ | ---- |
| source | int  |


{% endtab %}

{% tab title="Manipulation (3)" %}
If <mark style="background-color:green;">true</mark> is returned, the player can execute the command
{% endtab %}

{% tab title="Return (3)" %}
<mark style="background-color:green;">true</mark> or <mark style="background-color:orange;">false</mark>
{% endtab %}
{% endtabs %}

---
description: To make it easy to implement the script, we provide examples of it
---

# Examples

{% hint style="info" %}
**IsPlayerAllowedToShow**

<mark style="background-color:green;">true</mark> if the player is allowed to see the blip

#### &#x20;IsPlayerAllowedToToggle

<mark style="background-color:green;">true</mark> if the player is allowed to give a blip to an entity in the [channel](exports-api-communication.md#channel)



_These two functions have to be set by yourself (e.g. xPlayer.getJob() == x)_
{% endhint %}

#### <mark style="color:red;">Emergency vehicle</mark>

{% tabs %}
{% tab title="Sprite (1)" %}
<figure><img src="https://docs.fivem.net/blips/radar_police.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Example (1)" %}
```lua
{
    IsPlayerAllowedToShow = function (entity, player)
        return true
    end,
    IsPlayerAllowedToToggle = function (entity, player, client)
        return true
    end,
    Checker = function (ped)
        local vehicle = GetVehiclePedIsIn(ped, false)
        return vehicle, IsVehicleSirenOn(vehicle)
    end,
    Blip = function (blip)
        SetBlipSprite(blip, 41)
        SetBlipDisplay(blip, 4)
        SetBlipScale(blip, 3.0)
        SetBlipAsShortRange(blip, true)
        SetBlipAlpha(blip, 180)
        SetBlipPriority(blip, 100)
        PulseBlip(blip)
    end
}
```
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Emergency helicopter</mark>

{% tabs %}
{% tab title="Sprite (2)" %}
<figure><img src="https://docs.fivem.net/blips/radar_police_heli_spin.png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Example (2)" %}
```lua
{
    IsPlayerAllowedToShow = function (entity, player)
        return true
    end,
    IsPlayerAllowedToToggle = function (entity, player, client)
        return true
    end,
    Checker = function (ped)
        local vehicle = GetVehiclePedIsIn(ped, false)
        return vehicle, GetEntityModel(vehicle) == GetHashKey("polmav")
    end,
    Blip = function (blip)
        SetBlipSprite(blip, 15)
        SetBlipDisplay(blip, 4)
        SetBlipAsShortRange(blip, true)
        SetBlipAlpha(blip, 180)
        SetBlipPriority(blip, 100)
    end
}
```
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Visible parachutes</mark>

{% tabs %}
{% tab title="Sprite (3)" %}
<div align="center">

<figure><img src="https://docs.fivem.net/blips/radar_parachute.png" alt=""><figcaption></figcaption></figure>

</div>
{% endtab %}

{% tab title="Example (3)" %}
```lua
{
    IsPlayerAllowedToShow = function (entity, player)
        return true
    end,
    IsPlayerAllowedToToggle = function (entity, player, client)
        return true
    end,
    Checker = function (ped)
        local state = GetPedParachuteState(ped)
        return ped, state == 2 or state == 1
    end,
    Blip = function (blip)
        SetBlipSprite(blip, 377)
        SetBlipDisplay(blip, 4)
        SetBlipScale(blip, 1.5)
        SetBlipAsShortRange(blip, true)
        SetBlipAlpha(blip, 180)
        SetBlipPriority(blip, 100)
    end
```
{% endtab %}
{% endtabs %}

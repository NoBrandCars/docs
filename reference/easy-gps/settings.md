# Settings

```lua
Settings = {
    API = {
        AddChannel = function(array)
            return true
        end,
        DeactivateChannel = function(key)
            return true
        end,
        OnToggle = function(entity, channelID, state)
            
        end
    },
    Channel = {
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
        },
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
        },
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
        }
    },
    Wait = {
        GamePool = 2000,
        Channel = {
            Idle = 2000,
            Active = 1000
        }
    },
    Console = true
}
```

{% hint style="info" %}
If you have any questions regarding this file / its options make sure to raise a ticket within our [Discord-Server](https://discord.gg/S8Xq7JwNgg).
{% endhint %}

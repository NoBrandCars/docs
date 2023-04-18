# Settings

```lua
Settings = {
    Ball = vec3(-324.1383, -1968.5367, 21.3),            -- Ball Spawn
    Teams = {                                            -- Color for each team. (Vehicle, firework etc will be in that color)
        Orange = {
            r = 243,
            g = 77,
            b = 15
        },
        Blue = {
            r = 15,
            g = 77,
            b = 243
        }
    },
    Peds = {                                            -- Ped Spawn
        Blue = {
            vector = vector4(-293.5027, -1924.0889, 29.1457, 234.9576),
            model = "a_m_y_motox_02"
        },
        Orange = {
            vector = vector4(-286.0806, -1930.2833, 29.1457, 61.4075),
            model = "a_m_y_motox_01"
        }
    },
    Vehicles = {                                        -- Vehicle Spawn
        Blue = {
            vector = vector4(-313.3335, -1977.5653, 20.7550, 53.1432),  -- Spawnpoint for each round
            model = "minioctane",                       -- if you want bigger octane fill in "rroctane"
            invincible = true,                          -- true = no damage to vehicle
            plate = {
                text = "ROCKET",
                index = 1
            }
        },
        Orange = {
            vector = vector4(-335.1695, -1959.1554, 20.7561, 228.0790), -- Spawnpoint for each round
            model = "minioctane",                       -- if you want bigger octane fill in "rroctane"
            invincible = true,                          -- true = no damage to vehicle
            plate = {
                text = "ROCKET",
                index = 1
            }
        }
    },
    API = {                                             -- API to use in your scripts
        Notify = function(source, string)
            TriggerClientEvent("nbc:rocketsoccer:notify", source, string)
        end,
        StartRound = function (sourceOrange, sourceBlue)-- Call function to start a game or manipulate it
            return true
        end,
        StopRound = function ()                         -- Call function to stop a game or manipulate it
            return true
        end,
        GetPlayerName = function(source)                -- Function to get the players name.
            return GetPlayerName(source)
        end,
        IsPlayerAllowed = function(source)              -- Function to check if player is allowed to join the queue.
            if Settings.EventMode then
                return IsPlayerAceAllowed(source, "nbc.admin")
            else
                return true
            end
        end,
        AddPlayerToQueue = function(source, team, force, player) -- Add player to queue
            if Settings.API.IsPlayerAllowed(source) or force then
                queue[team][source] = true
                return true
            end
            
            return false
        end,
        IsPlayerInQueue = function(source)              -- Check if a player is in queue
            return queue.blue[source] or queue.orange[source]
        end,
        RemovePlayerFromQueue = function(source, player)        -- Change logic to remove players or handle this as event
            queue.blue[source] = nil
            queue.orange[source] = nil
        end,
        CreateVehicle = function(model, vector)
            return CreateVehicle(model, vector, true, false)
        end,
        CreateObject = function(model, vector)
            return CreateObject(model, vector, true, false, false)
        end,
        OnExploit = function(playerPedId, netID)

        end,
        OnWinning = function(team)                      -- team can be "blue" or "orange" or nil if all players left the server

        end,
        OnGoal = function(team) -- team can be "blue" or "orange"

        end
    },
    Round = {
        Wait = 5,                                       -- Round Wait Time (in seconds)
        Time = 300                                      -- Round Time (in seconds)
    },
    Lobby = vec3(-282.1134, -1917.9065, 29.9464),
    Language = "en",                                    --Language (en, de, es, sw)
    --Misc...
    Logo = "https://dunb17ur4ymx4.cloudfront.net/webstore/logos/f362f15ca627b0028b886fd69d1c6d30168aebda.png",
    DebugMode = false,                                   --Leave this false! If you need support we will tell you to switch this to true. If true will do extensive loggin in client & server console!
    EventMode = false,                                   --If you wish to disable the queue and allow queue only for Admins.
    Console = true,
    Use3DText = true,
    --Effects
    BoostFX = {
        Active = true,
        CarColors = true,
        Custom = {
            r = 255,
            g = 75,
            b = 125
        }
    }
}
```

{% hint style="info" %}
If you have any questions regarding this file / its options make sure to raise a ticket within our [Discord-Server](https://discord.gg/S8Xq7JwNgg).
{% endhint %}

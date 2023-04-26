# Fxmanifest

```lua
fx_version "cerulean"

lua54 "yes"
game "gta5"

name "EasyMapChange"
author "NoBrandCars"
version "1.0.1"

server_script {
    "http.lua",
    "server.lua"
}

client_script "client.lua"

shared_script {
    "settings.lua",
    "shared.lua"
}
escrow_ignore "settings.lua"

exports {
    "IsPlayerAllowed",
    "GetCurrentMap",
    "ChangeMap"
}
```

{% hint style="info" %}
Do not change anything within the fxmanifest.lua
{% endhint %}

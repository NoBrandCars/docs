# Fxmanifest

```lua
fx_version 'cerulean'

lua54 'yes'
game 'gta5'

name 'EasyGPS'
author 'NoBrandCars'
version '1.0.0'

server_script {
    'http.lua',
    "server.lua"
}

client_script 'client.lua'
shared_script 'settings.lua'
escrow_ignore "settings.lua"

exports {
    "AddChannel",
    "DeactivateChannel",
    "ModifyChannel",
    "GetChannels"
}
```

{% hint style="info" %}
Do not change anything within the fxmanifest.lua
{% endhint %}

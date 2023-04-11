# Fxmanifest

```lua
fx_version 'cerulean'

lua54 'yes'
game 'gta5'

name 'RocketSoccer'
author 'NoBrandCars'
version '1.0.3'

server_script {
    'server.lua',
    'http.lua'
}
client_script 'client.lua'

shared_scripts {
    'settings.lua',
    "languages.lua"
}

files {
    "nui/*.*",
    "nui/sounds/*.*",
    "data/*.*"
}

ui_page "nui/index.html"

escrow_ignore {
    "settings.lua",
    "languages.lua"
}

exports {
    "Notify",
    "StartRound",
    "StopRound",
    "GetPlayerName",
    "IsPlayerAllowed",
    "AddPlayerToQueue",
    "IsPlayerInQueue",
    "RemovePlayerFromQueue",
    "OnExploit",
    "OnWinning",
    "OnGoal",
    "GetCurrentRound"
}

data_file 'VEHICLE_LAYOUTS_FILE'    'data/**/vehiclelayouts.meta'
data_file 'HANDLING_FILE'           'data/**/handling.meta'
data_file 'VEHICLE_METADATA_FILE'   'data/**/vehicles.meta'
data_file 'CARCOLS_FILE'            'data/**/carcols.meta'
data_file 'VEHICLE_VARIATION_FILE'  'data/**/carvariations.meta'
```

{% hint style="info" %}
Do not change anything within the fxmanifest.lua
{% endhint %}

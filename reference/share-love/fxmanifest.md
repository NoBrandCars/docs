# Fxmanifest

```lua
fx_version "cerulean"

lua54 "yes"
game "gta5"

name "ShareLove"
author "NoBrandCars"
version "1.0.0"

server_script "server.lua"
client_script "client.lua"
shared_script "settings.lua"
escrow_ignore "settings.lua"

files {
    "build/**"
}

ui_page "build/index.html"

exports {
    "EmojiMenu",
    "DisplayEmoji"
}

server_exports {
    "DisplayEmoji"
}
```

{% hint style="info" %}
Do not change anything within the fxmanifest.lua
{% endhint %}

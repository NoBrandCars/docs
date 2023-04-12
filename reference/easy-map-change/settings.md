# Settings

```lua
Settings = {
    API = {
        IsPlayerAllowed = function(source)
            return IsPlayerAceAllowed(source, "nbc.admin")
        end,
        ChangeMap = function(map, player)
            return true
        end
    },
    Command = "changemap",
    Standard = "CURLING",
    Console = true
}
```

{% hint style="info" %}
If you have any questions regarding this file / its options make sure to raise a ticket within our [Discord-Server](https://discord.gg/S8Xq7JwNgg).
{% endhint %}

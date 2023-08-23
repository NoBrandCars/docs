# Settings

```lua
Settings = {
    Cooldown = 10000,
    Scale = {
        Distance = 30.0,
        Min = 0.3,
        Max = 1.0
    },
    Vector = vec3(0.0, 0.0, 1.1),
    Style = "apple",
    DefaultEmoji = "1f600",
    DefaultMenuKey = "i",
    Wait = 10,
    API = {
        DisplayEmoji = function (source, emoji, force, emojis)
            return true
        end,
        EmojiMenu = function (state)
            return true
        end
    }
}
```

{% hint style="info" %}
If you have any questions regarding this file / its options make sure to raise a ticket within our [Discord-Server](https://discord.gg/S8Xq7JwNgg).
{% endhint %}

# Language

Languages which are supported by default:

* German&#x20;
* English&#x20;
* Spanish
* Swedish

```lua
Languages = {
    ["de"] = {
        KeyMap = {
            Jump = "Springen in Rocket League",
            Boost = "Boost in Rocket League",
            Drift = "Drift in Rocket League",
            W = "W Taste in Rocket League",
            A = "A Taste in Rocket League",
            S = "S Taste in Rocket League",
            D = "D Taste in Rocket League",
            E = "E Taste in Rocket League"
        },
        YouAreInQueue = "Du bist bereits in einer Warteschlange!",
        NotPermitted = "Du bist nicht befugt der Warteschlange beizutreten!",
        EventMode = "Eventmode ist eingeschaltet! Beitritt nicht möglich!",
        JoinSuccess = "Erfolgreich beitreten",
        LeaveSuccess = "Du hast das Spiel verlassen!",
        Join = "Beitreten",
        Leave = "Verlassen"
    },
    ["es"] = {
        KeyMap = {
            Jump = "Saltar in Rocket League",
            Boost = "Boost in Rocket League",
            Drift = "Drift in Rocket League",
            W = "W Botón in Rocket League",
            A = "A Botón in Rocket League",
            S = "S Botón in Rocket League",
            D = "D Botón in Rocket League",
            E = "E Botón in Rocket League"
        },
        YouAreInQueue = "Ya estás en una cola!",
        NotPermitted = "No estás autorizado a unirte a la cola!",
        EventMode = "El modo de evento está activado! No puede unirse!",
        JoinSuccess = "Únete con éxito",
        LeaveSuccess = "Te fuiste del juego!",
        Join = "Unirse",
        Leave = "Dejar"
    },
    ["sw"] = {
        KeyMap = {
            Jump = "Hoppa in Rocket League",
            Boost = "Boost in Rocket League",
            Drift = "Drift in Rocket League",
            W = "W Knapp in Rocket League",
            A = "A Knapp in Rocket League",
            S = "S Knapp in Rocket League",
            D = "D Knapp in Rocket League",
            E = "E Knapp in Rocket League"
        },
        YouAreInQueue = "Du står redan i kö!",
        NotPermitted = "Du är inte behörig att gå med i kön!",
        EventMode = "Händelseläget är på! Kan inte gå med!", 
        JoinSuccess = "Únete con éxito",
        LeaveSuccess = "Te fuiste del juego!",
        Join = "Gick med",
        TextLeave = "Lämna",
        JoinSuccess = "Har gått med",
        Leave = "Du lämnade spelet!",

    },
    ["en"] = {
        KeyMap = {
            Jump = "Jump in Rocket League",
            Boost = "Boost in Rocket League",
            Drift = "Drift in Rocket League",
            W = "W Key in Rocket League",
            A = "A Key in Rocket League",
            S = "S Key in Rocket League",
            D = "D Key in Rocket League",
            E = "E Key in Rocket League"
        },
        YouAreInQueue = "You are already in a queue!",
        NotPermitted = "You are not authorized to join the queue!",
        EventMode = "Eventmode is on! Can not join!",
        JoinSuccess = "Successfully joined",
        LeaveSuccess = "You left the game!",
        Join = "Join",
        Leave = "Leave"

    }
}

Language = Languages[Settings.Language]
```

{% hint style="info" %}
Language can be set within the [settings.lua](settings.md)
{% endhint %}

{% hint style="info" %}
If you have any questions regarding this file / its options make sure to raise a ticket within our [Discord-Server](https://discord.gg/S8Xq7JwNgg).
{% endhint %}

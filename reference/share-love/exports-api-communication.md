---
description: Some functions can be executed only from client or server side
---

# Exports (API Communication)

{% hint style="info" %}
**Good to know:** You can use all functions as event or manupulation of the logic
{% endhint %}

## Client

#### <mark style="color:red;">Open / Close emoji menu</mark>

{% tabs %}
{% tab title="Example (1)" %}
```lua
exports["ShareLove"]:EmojiMenu(state)
```
{% endtab %}

{% tab title="Parameters (1)" %}
| Name  | Type                                       |
| ----- | ------------------------------------------ |
| state | <mark style="color:purple;">boolean</mark> |
{% endtab %}

{% tab title="Manipulation (1)" %}
If <mark style="background-color:orange;">false</mark> is returned, the menu will **not** open.

If it is set to <mark style="background-color:green;">true</mark>, the menu opens **as usual**.
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Display a emoji</mark>

{% tabs %}
{% tab title="Example (2)" %}
```lua
exports["ShareLove"]:DisplayEmoji(emoji)
```
{% endtab %}

{% tab title="Parameters (2)" %}
| Name  | Type                                                                                                          |
| ----- | ------------------------------------------------------------------------------------------------------------- |
| emoji | <mark style="color:blue;">string</mark> ([unified](https://www.npmjs.com/package/emoji-picker-react#props-1)) |
{% endtab %}

{% tab title="Manipulation (2)" %}
To **protect** the logic from **executors**, the manipulation applies only to the server side and is therefore not invoked in the client
{% endtab %}
{% endtabs %}

## Server

#### <mark style="color:red;">Display a emoji</mark>

{% tabs %}
{% tab title="Example (3)" %}
```lua
exports["ShareLove"]:DisplayEmoji(source, emoji, force, emojis)
```
{% endtab %}

{% tab title="Parameters (3)" %}
| Name   | Type                                                                                                             |
| ------ | ---------------------------------------------------------------------------------------------------------------- |
| source | <mark style="color:green;">int</mark>                                                                            |
| emoji  | <mark style="color:blue;">string</mark> ([unified](https://www.npmjs.com/package/emoji-picker-react#props-1))    |
| force  | <mark style="color:purple;">boolean</mark>                                                                       |
| emojis | <mark style="color:blue;">string\[]</mark> ([unified](https://www.npmjs.com/package/emoji-picker-react#props-1)) |
{% endtab %}

{% tab title="Manipulation (3)" %}
If <mark style="background-color:orange;">false</mark> is returned, the emoji **adds** itself to the current emojis and is displayed.

If it is set to <mark style="background-color:green;">true</mark>, the emoji will **not** be displayed.
{% endtab %}
{% endtabs %}

#### <mark style="color:red;">Set emojis of player</mark>

{% tabs %}
{% tab title="Example (4)" %}
```lua
exports["ShareLove"]:SetEmojis(source, emojis)
```
{% endtab %}

{% tab title="Parameters (4)" %}
| Name   | Type                                                                                                             |
| ------ | ---------------------------------------------------------------------------------------------------------------- |
| source | <mark style="color:green;">int</mark>                                                                            |
| emojis | <mark style="color:blue;">string\[]</mark> ([unified](https://www.npmjs.com/package/emoji-picker-react#props-1)) |
{% endtab %}
{% endtabs %}

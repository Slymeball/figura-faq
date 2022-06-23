# The Unofficial Figura FAQ

These frequently asked questions are listed in this document so that they won't be frequently asked again.

## How do I hide the vanilla player model?

There are two different solutions for both the prewrite and rewrite. See below for both versions.

### Prewrite

```lua
for key, value in pairs(vanilla_model) do
	value.setEnabled(false)    
end
```

### Rewrite

```lua
vanilla_model.ALL:setVisible(false)
```

## Why doesn't Optifine work with Figura?

Figura does not support Optifine because working with Optifine has become such a hassle that it isn't worth the time anymore. Instead, try some [Optifine alternatives](https://lambdaurora.dev/optifine_alternatives).

## Figura says there's "not enough space on server." What does this mean?

This is a recurring issue with many people which will be rectified with the rewrite's backend. To fix this, follow the steps below.

First of all, if your avatar is larger than 100kb, you cannot upload it to the backend.

If your avatar is smaller than 100kb and you cannot upload the avatar, try deleting your currently uploaded avatar using the button within the in-game Figura menu. If you still cannot upload your avatar, try executing `?clearavatar` in [#bot-junk](https://discord.com/channels/805969743466332191/824741434078396468)

## What part names should I use for my avatar?

If your avatar uses the proportions of the vanilla avatar, you should be fine using the default names supplied by BlockBench's `Minecraft Skin` option.

If your avatar is smaller or larger than the vanilla avatar, try using the `MIMIC` variations listed below. `MIMIC`ed bones only copy the rotation of the part, while discarding all other information like position shifts.

| Body Part | Mimic Keyword |
| --- | --- |
| Head | `MIMIC_HEAD` |
| Body | `MIMIC_TORSO` |
| Left Arm | `MIMIC_LEFT_ARM` |
| Right Arm | `MIMIC_RIGHT_ARM` |
| Left Leg | `MIMIC_LEFT_LEG` |
| Right Leg | `MIMIC_RIGHT_LEG` |

Consult with the [BlockBench Keywords wiki page](https://github.com/Moonlight-MC/Figura/wiki/Blockbench-Keywords) for more information.

> ⚠️ **Warning:**  
> Using the legacy keywords (`HEAD`, `TORSO`, etc.) is now obsolete. Please do not use them.

## How do I make my avatar glow?

A special texture can be added to your avatar to make some areas emissive. To make an emissive texture, make a copy of your original texture, open an image editor, remove all pixels that you do **NOT** want to glow, and save the new file with the name `texture_emission.png`.

Since the rewrite uses the textures inside of the BlockBench model, you must specify an emissive texture inside of BlockBench instead of the avatar folder.

## How do I make an animated texture?

Using a Lua script, you can change the UV of your model. Check the links below for more information.

> ⚠️ **Warning:**  
> The following resources apply to the prewrite. A rewrite tutorial is coming soon.

- [Tutorial](https://manuel-3.github.io/animated-texture)
- [Example_Download](https://discord.com/channels/805969743466332191/808155531389698079/908426876345811014)
- [`setUV` explanation](https://discord.com/channels/805969743466332191/808155531389698079/924140280909819904)

## Where can I find avatars to download?

You can find avatars from [#avatar-showcase](https://discord.com/channels/805969743466332191/808259850223616030) for prewrite and [#rewrite-avatars](https://discord.com/channels/805969743466332191/976527692549726258) for rewrite and add them into your `/figura/model_files` (for prewrite) or `/figura/avatars` (for rewrite) folder.

> ℹ️ **Tip:**  
> A new way for finding avatars is planned for the rewrite, implementing an avatar browser into the client itself. When it is added, this entry will be updated.

## I don't know how to code in Lua. How do I learn?

Lua has an online manual for learning the syntax of the language, available at [lua.org/manual/5.4](https://www.lua.org/manual/5.4/). If you prefer a quicker read and something made by someone in the Figura community, Manuel_ (an admin) has created a quickstart guide available [here](https://manuel-3.github.io/lua-quickstart).

## I cannot connect to the backend! Is the backend down?

The prewrite backend is very unreliable when it comes to connection and uptime, but there are steps to recify this issue.

First, if you are on 1.19 using the prewrite, you cannot connect to the Figura backend because Mojang changed their authentication servers. If you want to use the Figura backend in 1.19, you will have to use the rewrite.

If you are not playing on 1.19, try checking the status of the backend using the `?backend` command. If the bot displays an :x: trying to connect to the backend you are interested in, it is down and there is nothing you can do to fix it. 

If the bot replied with a :white_check_mark:, this means that you must refresh the connection to the backend. Press the reload button in the in-game Figura menu to retry a connection to the backend. If this fails after a few presses, the backend may be online but refusing connections.

## My avatar always errors on the first line, despite the error occurring on a different line. Why is this?

To save space on the backend, Figura removes newlines and comments in your code. Use a local avatar instead to see what line your script errored on.

> ℹ️ **Info:**  
> While this may be true for the rewrite, I am not certain if it is or not.

## How do I use pings?

To make a pinged function, type `ping.` before the function name to put the function in the `ping` table. For an example, see the code below.

```lua
function ping.toggleHorns(v)
	model.Head[Horns].setEnabled(v)
end
```

> ⚠️ **Warning:**  
> Pings (and most other backend functions) do not exist yet. When they do, check back here.

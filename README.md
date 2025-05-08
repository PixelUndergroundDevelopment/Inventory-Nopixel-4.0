# Inventory-Nopixel-4.0
Inventory Nopixel 4.0 for qb-core framework

# Screenshot 
https://media.discordapp.net/attachments/1217347989975072869/1370025264246951946/FiveM_GTAProcess_2025-05-08_18-37-24.png?ex=681dfef4&is=681cad74&hm=019213b2867941da9ce75de1d94b37bce9dedf990cd31ce7ad14d8c87b49ddae&=&format=webp&quality=lossless&width=1522&height=856

https://media.discordapp.net/attachments/1217347989975072869/1370025444471996537/FiveM_GTAProcess_2025-05-08_18-37-05.png?ex=681dff1f&is=681cad9f&hm=b90fc03129c8b7dd9755f9a6e6afa9b26246d84fa3a3d334ae409cb30d5bd558&=&format=webp&quality=lossless&width=1522&height=856

# Information
```DO NOT CHANGE THE DATA FOLDER DIRECTLY WITHOUT READING THE README FILE. THE SCRIPT WILL NOT WORK. READ THE README FILE AFTER EACH UPDATE.```

📦 PUD Inventory
This script is coded to run smoothly when your inventories change without any problems on any server framework.

🛠️ Installation
1. >Update Config File:
If your previous inventory was Ox, you need to write "ox" in Config.OldInventory. Otherwise, you can leave this section blank.
If you are using qb-core, you need to change qb-inventory export names to qb-inventory.Do the same for lib. You have to write the same thing in lib as you wrote in inventory. Otherwise it will not work properly

2. You need to do the same for lib and weapons script. Open the shared/config.lua files of both and adjust the inventory settings. Make sure you type the inventory name correctly.

2. >Installing Requirements:
You need to install pud-weaponthrowing-1.2 script for Weapon throwing, pud-textui-2 script for fluent texts and pud-uipack script for progressbar to work properly. You also need to install pud-lib-2 for the script to run smoothly. These scripts come as a gift with the PUD Inventory script.

3. >Updating the Data Folder:
If you have used Ox before, you need to replace items and weapons files inside the data folder in this script with their own ox files to convert your data automatically, but stashes.lua, vehicles.lua, crafting.lua, licenses.lua, evidence.lua and animations.lua file should remain completely empty. Check below how to add stashes, the same way you can add and edit crafts from the configuration

🚀 Updates
The script will be continuously updated and new features will continue to be added.

❗️ Important Notes
1. It is recommended not to restart the script while the server is active.

2. It is recommended to check the config file several times before running it. If you need help with the config, please make sure to ask in a respectful way.

3. If you are already using qb-inventory, you do not need to make any changes to your code to organize your inventory, but if you are not using qb-inventory before, you need to make the following changes.



💡Information
1. If you want you can change the script name to qb-inventory and use it. ( Not recommended ) . You are advised not to change your name.If you are going to change it, you need to change the inventory name in the shared/config.lua file of the lib and weapons files. You also need to change the names all over your server package

2. Do not forget to change other exports

3. The phone sim system has not yet been coded, because a special coding system will be made according to the wishes of the customers and the phones they use.


> Sample scripts

1. If you cannot make export settings, I will leave you 2 sample scripts, you can review them and check my export uses.

jim-consumables : https://dosya.co/ixb92iq4e8lz/jim-consumables.zip.html

jim-recycle : https://dosya.co/9dippe1ayl0g/jim-recycle.zip.html

qb-smallresources : https://dosya.co/ipg39fml5b5w/qb-smallresources.zip.html




```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
```!! THIS PLACE IS VERY IMPORTANT```
> Info 
1. If you are using qb-inventory before, make this script name qb-inventory, make everything that says qb-inventory in it qb-inventory and continue to use it that way.

2. If you were using ox_inventory before, rename this script to ox_inventory, change everything with qb-inventory in it to ox_inventory, then replace the items.lua folder in the data folder with your old ox inventory and keep using it that way. 

Also, do not forget to make config adjustments in the scripts such as lib, inventory, throw, weapons.


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
You should change 
```lua
    Player.Functions.RemoveItem

    to 

    exports['qb-inventory']:RemoveItem(source,'armor', 1)
```
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
You should change 
```lua
    Player.Functions.SetInventory(Player.PlayerData.items, true)

    to 

    local items = exports['qb-inventory']:GetPlayerItems(cid)
    exports['qb-inventory']:SetInventory(src, items)
```
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
You should change 
```lua
    Player.PlayerData.items

    to 

    exports['qb-inventory']:GetPlayerItems(cid)
```
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
You should change         
```lua
    Player.Functions.AddItem(name, amount, false, metadata) 

    to 

    exports['qb-inventory']:AddItem(name, amount, false, metadata) 
```
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
You should change         
```lua
    Player.Functions.GetItemBySlot(WeaponData.slot)

    to 

    exports['qb-inventory']:Search(WeaponData.slot)
```
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
You should change         
```lua
    QBCore.Functions.GetPlayer(src).Functions.GetItemByName(item).unique

    to 

    exports.qb-inventory:GetItemByName(src,item).unique
```
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------






If you are using qb and have not changed the magazine names in the config, you can add these to your shared table

```lua
    weapon_pistol_magazine          = { name = 'weapon_pistol_magazine', label = 'Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Pistol Magazine' },
    weapon_pistol_mk2_magazine      = { name = 'weapon_pistol_mk2_magazine', label = 'Pistol Mk II Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Pistol Mk II Magazine' },
    weapon_combatpistol_magazine    = { name = 'weapon_combatpistol_magazine', label = 'Combat Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Combat Pistol Magazine' },
    weapon_appistol_magazine        = { name = 'weapon_appistol_magazine', label = 'AP Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'AP Pistol Magazine' },
    weapon_stungun_magazine         = { name = 'weapon_stungun_magazine', label = 'Taser Magazine', weight = 1000, type = 'weapon', ammotype = nil, image = 'clip_attachment.png', unique = true, useable = false, description = 'Taser Magazine' },
    weapon_pistol50_magazine        = { name = 'weapon_pistol50_magazine', label = 'Pistol .50 Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Pistol .50 Magazine' },
    weapon_snspistol_magazine       = { name = 'weapon_snspistol_magazine', label = 'SNS Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'SNS Pistol Magazine' },
    weapon_heavypistol_magazine     = { name = 'weapon_heavypistol_magazine', label = 'Heavy Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Heavy Pistol Magazine' },
    weapon_vintagepistol_magazine   = { name = 'weapon_vintagepistol_magazine', label = 'Vintage Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Vintage Pistol Magazine' },
    weapon_flaregun_magazine        = { name = 'weapon_flaregun_magazine', label = 'Flare Gun Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_FLARE', image = 'clip_attachment.png', unique = true, useable = false, description = 'Flare Gun Magazine' },
    weapon_marksmanpistol_magazine  = { name = 'weapon_marksmanpistol_magazine', label = 'Marksman Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Marksman Pistol Magazine' },
    weapon_revolver_magazine        = { name = 'weapon_revolver_magazine', label = 'Revolver Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Revolver Magazine' },
    weapon_revolver_mk2_magazine    = { name = 'weapon_revolver_mk2_magazine', label = 'Violence Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'da Violence Magazine' },
    weapon_doubleaction_magazine    = { name = 'weapon_doubleaction_magazine', label = 'Double Action Revolver Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Double Action Revolver Magazine' },
    weapon_snspistol_mk2_magazine   = { name = 'weapon_snspistol_mk2_magazine', label = 'SNS Pistol Mk II Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'SNS Pistol MK2 Magazine' },
    weapon_raypistol_magazine       = { name = 'weapon_raypistol_magazine', label = 'Up-n-Atomizer Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Weapon Raypistol Magazine' },
    weapon_ceramicpistol_magazine   = { name = 'weapon_ceramicpistol_magazine', label = 'Ceramic Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Weapon Ceramicpistol Magazine' },
    weapon_navyrevolver_magazine    = { name = 'weapon_navyrevolver_magazine', label = 'Navy Revolver Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Weapon Navyrevolver Magazine' },
    weapon_gadgetpistol_magazine    = { name = 'weapon_gadgetpistol_magazine', label = 'Perico Pistol Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Weapon Gadgetpistol Magazine' },
    weapon_pistolxm3_magazine       = { name = 'weapon_pistolxm3_magazine', label = 'Pistol XM3 Magazine', weight = 1000, type = 'weapon', ammotype = 'AMMO_PISTOL', image = 'clip_attachment.png', unique = true, useable = false, description = 'Pistol XM3 Magazine' },
```


I have seen people saying that there is a problem with stash not saving in inventory, but this is related to incomplete use.

This is how you open the Stash, which is fine.

TriggerServerEvent('inventory:server:OpenInventory', 'stash', id)


But if you do not add this code later, the stash will not save

TriggerEvent('inventory:client:SetCurrentStash', id)




This is how you can add stash.This is just a simple example

> UPDATE 26.06.2024
```lua
   TriggerEvent('inventory:client:SetCurrentStash', 'launder-' .. menuId)
   TriggerServerEvent('inventory:server:OpenInventory', 'stash', 'launder-' .. menuId , {
        maxweight = 4000000,
        slots = 1})
```

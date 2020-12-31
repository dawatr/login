# Register

By @Shoghicp


#### IMPORTANT
You no longer need to set "hack login" and "hack register" perms with SimpleAuthHelper.

To use account linking you must also update the database if you use MySQL or SQLite:

MySQL:

* `ALTER TABLE Register.Register_players ADD linkedign VARCHAR(16);`

SQLITE:

* `ALTER TABLE Register.Register_players ADD linkedign TEXT;`


Plugin for PocketMine-MP that prevents people from impersonating an account, requiring registration and login when connecting.

	 Register plugin for PocketMine-MP
     Copyright (C) 2014 PocketMine Team <https://github.com/PocketMine/Register>

     This program is free software: you can redistribute it and/or modify
     it under the terms of the GNU Lesser General Public License as published by
     the Free Software Foundation, either version 3 of the License, or
     (at your option) any later version.

     This program is distributed in the hope that it will be useful,
     but WITHOUT ANY WARRANTY; without even the implied warranty of
     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
     GNU General Public License for more details.


## What's New?

This version of Register adds automatic account linking to Register, and removes the obselete antihack protection.

Register2 is compatible with SimpleAuthHelper, and works with these providers: MySQL, YAML and SQLITE

## Commands


* `/login <password>`
* `/register <password>`
* `/unregister <password>` (TODO)
* `/link <otherIGN> <otherpassword>`
* `/unlink`
* For Console: `/unlink <playerIGN>`
* For OPs: `/Register <command: help|unregister> [parameters...]` (TODO)

Allows registering an account |
| Register.command.login | true | Allows logging into an account |
| Register.command.link | true | Allows linking an account |
| Register.command.unlink | true | Allows unlinking an account |


### Events

* Register\event\PlayerAuthenticateEvent
* Register\event\PlayerDeauthenticateEvent
* Register\event\PlayerRegisterEvent
* Register\event\PlayerUnregisterEvent

### Plugin API methods

All methods are available through the main plugin object

* bool isPlayerAuthenticated(pocketmine\Player $player)
* bool isPlayerRegistered(pocketmine\IPlayer $player
* bool authenticatePlayer(pocketmine\Player $player)
* bool deauthenticatePlayer(pocketmine\Player $player)
* bool registerPlayer(pocketmine\IPlayer $player, $password)
* bool unregisterPlayer(pocketmine\IPlayer $player)
* void setDataProvider(Register\provider\DataProvider $provider)
* Register\provider\DataProvider getDataProvider(void)

### Implementing your own DataProvider

You can register an instantiated object that implements Register\provider\DataProvider to the plugin using the _setDataProvider()_ method


    

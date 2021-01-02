# login

By @Shoghicp


#### IMPORTANT
You no longer need to set "hack login" and "hack login" perms with SimpleAuthHelper.

To use account linking you must also update the database if you use MySQL or SQLite:

MySQL:

* `ALTER TABLE login.login_players ADD linkedign VARCHAR(16);`

SQLITE:

* `ALTER TABLE login.login_players ADD linkedign TEXT;`


Plugin for PocketMine-MP that prevents people from impersonating an account, requiring registration and login when connecting.

	 login plugin for PocketMine-MP
     Copyright (C) 2014 PocketMine Team <https://github.com/PocketMine/login>

     This program is free software: you can redistribute it and/or modify
     it under the terms of the GNU Lesser General Public License as published by
     the Free Software Foundation, either version 3 of the License, or
     (at your option) any later version.

     This program is distributed in the hope that it will be useful,
     but WITHOUT ANY WARRANTY; without even the implied warranty of
     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
     GNU General Public License for more details.


## What's New?

This version of login adds automatic account linking to login, and removes the obselete antihack protection.

login2 is compatible with SimpleAuthHelper, and works with these providers: MySQL, YAML and SQLITE

## Commands


* `/login <password>`
* `/login <password>`
* `/unlogin <password>` (TODO)
* `/link <otherIGN> <otherpassword>`
* `/unlink`
* For Console: `/unlink <playerIGN>`
* For OPs: `/login <command: help|unlogin> [parameters...]` (TODO)

Allows logining an account |
| login.command.login | true | Allows logging into an account |
| login.command.link | true | Allows linking an account |
| login.command.unlink | true | Allows unlinking an account |


### Events

* login\event\PlayerAuthenticateEvent
* login\event\PlayerDeauthenticateEvent
* login\event\PlayerloginEvent
* login\event\PlayerUnloginEvent

### Plugin API methods

All methods are available through the main plugin object

* bool isPlayerAuthenticated(pocketmine\Player $player)
* bool isPlayerlogined(pocketmine\IPlayer $player
* bool authenticatePlayer(pocketmine\Player $player)
* bool deauthenticatePlayer(pocketmine\Player $player)
* bool loginPlayer(pocketmine\IPlayer $player, $password)
* bool unloginPlayer(pocketmine\IPlayer $player)
* void setDataProvider(login\provider\DataProvider $provider)
* login\provider\DataProvider getDataProvider(void)

### Implementing your own DataProvider

You can login an instantiated object that implements login\provider\DataProvider to the plugin using the _setDataProvider()_ method


    

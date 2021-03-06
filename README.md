# enc0ded-persistent-vehicles

This mod prevents vehicles from disappearing in OneSync multiplayer servers. It can also respawn vehicles in their previous location after a server restart.

## Requirements
FiveM Version >=2443

OneSync - This mod will not work without OneSync.


## Installation

Download from the releases tab in GitHub. Extract and place the enc0ded-persistent-vehicles folder in your resources folder. Start the resource.

```bash
start enc0ded-persistent-vehicles
```

## Usage

To make a vehicle persistent, pass its entity to the event below in a client script. For example if you are using ESX you can put this in the call back of the ESX.Game.SpawnVehicle function.
```lua
TriggerEvent('persistent-vehicles/register-vehicle', entity)
```
Stop a vehicle from being persistent and allow it to be removed as normal. Does not delete the vehicle.
Call this when a player puts away a vehicle. Also remember to call this on your admin delete vehicle commands.
```lua
TriggerEvent('persistent-vehicles/forget-vehicle', entity)
```
If you enable repopulate on reboot then you need to call the server event below before your server shuts down. This will ensure that the vehicles spawn in the exact same location when the server comes back online. 
```lua
TriggerEvent('persistent-vehicles/save-vehicles-to-file')
```
Alternatively you can stop the resource which will do this automatically.
```lua
StopResource('enc0ded-persistent-vehicles')
```

## Console
Cull persistent vehicles
```bash
pv-cull <number of vehicles>
```
Unpersist vehicles
```bash
pv-forget-all
```
Toggle console debugging messages
```bash
pv-toggle-debugging
```
Save all persistent vehicles to file. Can be called before reboot.
```bash
pv-save-to-file
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Support
[Discord](https://discord.gg/rhQhZWM)

## License
[MIT](https://choosealicense.com/licenses/mit/)

<img src=http://u.cubeupload.com/Owyn/lemmefish.jpg>

# Let-me-Fish
TERA-proxy module that mass-auto-fishes fishes, auto-crafts bait when out of bait, and auto-dismantles fish when inventory gets full.

Emulates human-like behavior mostly, abides human-like delays for actions based on fishing diffculty, retries if something goes wrong, works well even if the game is very limited in CPU resources.

Supports `auto-nego`tiate (with this fork https://github.com/Owyn/auto-nego ), so you would be able to both auto-fish and auto-negotiate

## Usage
Use command `fish` then follow instruction as simple as just throwing your fish-rod and it will auto-continue everything for you

`fish save` - saves your used recipe and list of fishes to auto-dismantle into per-character config file which will be used on next login  
`fish reset` - resets your loaded config  
`fish list` - lists settings used  
`fish reload` - reloads config file (if you edited it manually and want to reload it right now)  

- you can set a different recipe or add fishes to auto-dismantle-list after using `fish` command but before throwing your rod any time


## Installation
put `defs` insides to `node_modules\tera-data\protocol\` folder  
put `opcodes` insides to `node_modules\tera-data\map\` (in Caalis proxy)  

(You might need to do additional manual updates if you'r using Pinkies proxy, but you must be used to that already with it)

## Notes

- Stops when you get 10k fishlets (if you want to auto-discard fishlets - reconsider your fishing life in tera, fishlets are the main purpose for fishing after you upgrade your rod... ofc you could use side modules for that like https://github.com/teralove/no-strongboxes and adding fishlet id there)

- Opcodes are gotten via third-party sources mostly (submitted by users), if there are no opcodes for your region - too bad, you'd have to get em yourself, can't help you here, use https://github.com/Owyn/alex-packet-id-finder or https://github.com/Owyn/debug-logger/

- Yes, you can make it catch fish much faster like other cheating fishers do, even like in 2 sec lol, but server might decide to start checking how long it takes for ppl to actually catch  fish and ban all unreasonably fast fishers, so only way to change this timing is to set `disableAutoUpdate` to `true` in `module.json` and edit top lines in the `index.js` file manually at your very own risk

- Make sure you have some free slots in the inventory before fishing and some bait\fishlets to craft the bait before you start the `fish`
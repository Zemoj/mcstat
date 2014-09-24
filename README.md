# mcstat

PHP class, web page
[Minecraft][] server.

[Minecraft]: http://www.minecraft.net/

## Protocol Support

mcstat supports [Server List Ping][] as seen in `1.7` and later, and `1.5.2`. Server List Ping `1.5.2` works for older Minecraft servers (all the way back to `1.4.2`), while the `1.7` Server List Ping should be used for newer setups. mcstat also supports the UDP full and basic [Query][] protocols.

[Server List Ping]: http://wiki.vg/Server_List_Ping
[Query]: http://wiki.vg/Query

## Usage


### stat.php

`stat.php` is a simple web page that lets users query a given server.
**Note:** `stat.php` shouldn't be used on a public server as it's not
well tested!

![Screenshot of stat.php](https://i.imgur.com/Nc4yVOi.png)

### Usage as a PHP Class

    php > require_once './mcstat.php';
    php > $m = new MinecraftStatus('Uberminecraft.com');
    php > var_dump($m->ping());
    array(6) {
      ["player_count"]=>
      string(4) "2026"
      ["player_max"]=>
      string(4) "5000"
      ["motd"]=>
      string(62) "§aUberminecraft §aCloud §6| §c22 Games§b
    §l1.7 Play Now!"
      ["server_version"]=>
      string(5) "1.7.4"
      ["protocol_version"]=>
      string(1) "8"
      ["latency"]=>
      float(150)
    }



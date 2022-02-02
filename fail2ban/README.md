# **NOTICE**

This folder isn't currently relevant. This has not been updated for the move
from nginx back to Caddy.

# fail2ban
These are some fail2ban files related to my personal nginx setup.

See [nginx](https://github.com/xnaas/nginx/blob/master/nginx/) for more info.

## [fail2ban](https://github.com/xnaas/nginx/blob/master/fail2ban/)

### [action.d/cloudflare-ban.local](https://github.com/xnaas/nginx/blob/master/fail2ban/action.d/cloudflare-ban.local)
This action file is responsible for making sure your *properly* Cloudflare-protected
webserver will send bans to Cloudflare and protect *all* of your sites/domains.

<!-- TODO: Detailed explanation of Cloudflare side of this. -->


### [filter.d/nginx-http-auth.local](https://github.com/xnaas/nginx/blob/master/fail2ban/filter.d/nginx-http-auth.local)
This filter checks for bad
[basicauth](https://nginx.org/en/docs/http/ngx_http_auth_basic_module.html) attempts.

### [filter.d/nginx-post-auth.local](https://github.com/xnaas/nginx/blob/master/fail2ban/filter.d/nginx-post-auth.local)
This filter checks for bad auth attempts made as POST requests. Most applications
with their own login pages use the HTTP POST method for these.

The filter is set to ignore "bad" attempts that come from Plex as you'll end up
banning all of your users automatically all the time if you don't. More research
could probably be done on this in the future, but this is the usability approach.

### [jail.local]()
If you have a static public IP, add that to the `ignoreip` line. The line is set to
ignore the `172.16.0.0/12` (Docker) and `192.168.0.0/16` (standard home LAN) by default.

The purpose of `[name=%(__name__)s]` after `action   = cloudflare-ban` is to provide
additional information that you'll see logged in Cloudflare for banned IPs.

## [LICENSE](https://github.com/xnaas/nginx/blob/master/LICENSE.md)
The [GPL-3.0 License](https://www.gnu.org/licenses/gpl-3.0.en.html) applies to this
repositroy. I've made a number of changes from the original source code. Some are
substantial, some are minor. Regardless, the sources I started working with are primarily
[linuxserver/docker-swag](https://github.com/linuxserver/docker-swag) and
[linuxserver/reverse-proxy-confs](https://github.com/linuxserver/reverse-proxy-confs),
both of which are also licensed under GPL-3.0.

```
github.com/xnaas/nginx
Copyright (C) 2021  xnaas

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

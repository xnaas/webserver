# nginx
These are some nginx files related to my personal nginx setup.

Additional details:

* Uses [linuxserver/docker-swag](https://github.com/linuxserver/docker-swag/)
* Uses `DOCKER_MODS=linuxserver/mods:swag-auto-reload`

See [xnaas/docker-compose.yml](https://github.com/xnaas/docker-compose.yml/) for more
info on overall setup.

## [nginx](https://github.com/xnaas/nginx/blob/master/nginx/)

### [errors.conf](https://github.com/xnaas/nginx/blob/master/nginx/errors.conf)
Included in `nginx.conf` for [http.cat](https://http.cat) error pages/images.

### [nginx.conf](https://github.com/xnaas/nginx/blob/master/nginx/nginx.conf)
This file contains the majority of my nginx config. `proxy.conf` and `ssl.conf`
exist to be `include`d in `nginx.conf` just to keep the line count down and readability up.

### [proxy.conf](https://github.com/xnaas/nginx/blob/master/nginx/proxy.conf)
Mostly borrowed from [linuxserver/docker-swag/blob/master/root/defaults/proxy.conf](https://github.com/linuxserver/docker-swag/blob/master/root/defaults/proxy.conf).

### [ssl.conf](https://github.com/xnaas/nginx/blob/master/nginx/ssl.conf)
Mostly borrowed from [linuxserver/docker-swag/blob/master/root/defaults/ssl.conf](https://github.com/linuxserver/docker-swag/blob/master/root/defaults/ssl.conf).

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

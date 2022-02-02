# fail2ban
These are some fail2ban files related to my personal webserver setup.

See [caddy](https://github.com/xnaas/nginx/blob/master/caddy/) for more info.

## [fail2ban](https://github.com/xnaas/nginx/blob/master/fail2ban/)

### [action.d/cloudflare-ban.local](https://github.com/xnaas/nginx/blob/master/fail2ban/action.d/cloudflare-ban.local)
This action file is responsible for making sure your *properly* Cloudflare-protected
webserver will send bans to Cloudflare and protect *all* of your sites/domains.

<!-- TODO: Detailed explanation of Cloudflare side of this. -->

### [filter.d/caddy-auth.local](https://github.com/xnaas/nginx/blob/master/fail2ban/filter.d/caddy-auth.local)
This filter checks for any HTTP 401 or 403 errors that aren't from Plex.

### [jail.local]()
This is only a snippet of my full fail2ban setup on [my server](https://pcpartpicker.com/user/xnaas/saved/kQ86Mp)
but it gets the point across.

If relevant and you have a static public IP, add that to the `ignoreip` line.

The purpose of `[name=%(__name__)s]` after `action   = cloudflare-ban` is to provide
additional information that you'll see logged in Cloudflare for banned IPs.

# SMFM Admin Page

The links page served at https://admin.radio.sistermidnight.org.

It is a single static page (`index.html`) with the fonts and logo from the main radio site.

## Editing

To add or change a link, edit `index.html`. Each tile is an `<li>` block; copy one and change the `href`, label and description.

To preview locally (the font and logo paths start with `/`, so open it through a server):

```bash
python3 -m http.server 8765
# then open http://localhost:8765
```

## Deploying

Push to `main`. The Hetzner server checks this repo every minute and publishes any new commit to `/var/www/smfm-admin`. No build step is needed.

On the server:

- `systemctl status smfm-admin-deploy.timer`: is the checker running?
- `journalctl -u smfm-admin-deploy -n 20`: recent deploys

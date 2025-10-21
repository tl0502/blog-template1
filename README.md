# HuxBlog Boilerplate

##### This is the boilerplate of [Hux Blog](https://github.com/Huxpro/huxpro.github.io), all documents is over there!

#### [View Boilerplate &rarr;](http://huangxuan.me/huxblog-boilerplate/)

#### [View Live Hux Blog &rarr;](http://huangxuan.me)

## If you like Hux Blog, Please star [huxpro.github.io repo](https://github.com/Huxpro/huxpro.github.io) instead of this! Thank you!

## Backup & Recovery

During an upgrade I consolidated older source backups into the `backup/` folder to avoid duplicate output files.

- Main backups:
	- `backup/about.markdown` — original about page source
	- `backup/index.markdown` — original index/home source
	- `backup/root-backups/` — contains root-level copies and historic `.bak`/`.txt` files if you need them

If you want to restore the about or index page from a backup, run these PowerShell commands from the repository root (they will overwrite the existing files):

```powershell
# Restore about page
Copy-Item -Path "backup/about.markdown" -Destination "about.markdown" -Force

# Restore index page
Copy-Item -Path "backup/index.markdown" -Destination "index.markdown" -Force
```

After restoring, run (in PowerShell):

```powershell
bundle install; bundle exec jekyll build
```

If you prefer I can remove the root-level lightweight placeholder files (`about.markdown` and `index.markdown`) entirely and keep only the backups under `backup/` — tell me and I will perform that cleanup and prepare a git commit message.
# Shadowkit for desktop

Shadowkit on your computer: **Data** for live network speed and every day's use, **Notify** for
reminders and pins, **Focus** for a stretch of work and then a break, and **System** for the battery
and the disks, kept day by day, and keeping the computer awake for a while. **Desktop** turns GNOME
dark at sunset, keeps quiet hours and sets it up the way Windows or a Mac behaves, **Gems** are
earned by focusing on enough days of a week, and the processor, memory or free space can sit in the top
bar beside the speed. Offline, no account, free, and everything stays on your computer. More at [shadowkit.app/desktop](https://shadowkit.app/desktop).

This repository holds the releases only: the installers and their checksums. The app's source
isn't here.

## Install on Ubuntu or Debian

For Ubuntu 22.04 or newer and Debian 12 or newer, on x86-64, with GNOME or KDE (Keep awake and the
Desktop page need GNOME for now). Windows and macOS come later.

1. Download the `.deb` and `SHA256SUMS` from the [latest release](../../releases/latest).
2. Check the download, in the folder you saved them to:

   ```sh
   sha256sum -c SHA256SUMS
   ```

3. Install it:

   ```sh
   sudo apt install ./shadowkit_*_amd64.deb
   ```

4. Open Shadowkit from your apps. On first start it asks whether to start at login, so Data counts
   and reminders and Focus's breaks arrive with the window closed.

On GNOME, Shadowkit's tray icon (and the speed, the time left or System's values beside it) needs the AppIndicator
extension; Ubuntu ships it, sometimes turned off:

```sh
gnome-extensions enable ubuntu-appindicators@ubuntu.com
```

## Updates

Shadowkit never goes online, so it never looks for updates itself. To hear of a new version,
watch this repository for releases (Watch › Custom › Releases), then install the new `.deb` the
same way: your history, reminders and sessions are kept.

## Uninstall

```sh
systemctl --user disable --now shadowkit-data
sudo apt remove shadowkit
```

Your data stays in `~/.local/share/shadowkit` until you delete that folder. Shadowkit's background
service is `~/.config/systemd/user/shadowkit-data.service`; delete it too to leave nothing behind.

## Privacy

Shadowkit has no account, no analytics and no network code: it never connects to anything, and
its background service is barred from the internet by systemd. See the
[privacy policy](https://shadowkit.app/privacy).

## Questions

[shadowkit.app/contact](https://shadowkit.app/contact).

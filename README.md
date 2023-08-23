# Info
~~This is image is only for my usage, it's not meant for other hardware, other than mine. Please don't fork the repo, as it's not the correct way of doing a custom image, to make one follow https://universal-blue.org/tinker/make-your-own/~~

- basically fuck you alx, this is foss motherfucker

## Installation

> **Warning**
> This is an experimental feature and should not be used in production, try it in a VM for a while!

To rebase an existing Silverblue/Kinoite installation to the latest build:

- First rebase to the image unsigned, to get the proper signing keys and policies installed:
  ```
  sudo rpm-ostree rebase ostree-unverified-registry:ghcr.io/alxhr0/lunatic-ublue:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  sudo rpm-ostree rebase ostree-image-signed:docker://ghcr.io/alxhr0/lunatic-ublue:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```


This repository builds date tags as well, so if you want to rebase to a particular day's build:

```
sudo rpm-ostree rebase ostree-image-signed:docker://ghcr.io/alxhr0/lunatic-ublue:20230403
```

This repository by default also supports signing 

The `latest` tag will automatically point to the latest build. That build will still always use the Fedora version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.

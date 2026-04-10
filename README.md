# Ubuntu Autoinstall - FSLab

Automated Ubuntu installation config for the FSLab workstation.

## What It Does

Installs Ubuntu with everything pre-configured. No clicking "Next" 47 times.

## User

- **Name:** FSLab
- **Username:** fslab
- **Hostname:** Ubuntu-FSLab
- **Timezone:** America/Porto_Velho
- **Keyboard:** BR layout
- **Locale:** pt_BR.utf8

## What Gets Installed

### APT Packages
git, wget, curl, nodejs, npm, libreoffice, gimp

### Snaps
VS Code, Insomnia, Postman, Spotify, Firefox, Docker

### Extras
- Proprietary codecs ✅
- Third-party drivers ✅
- All updates on install ✅

## How to Use

1. Put `autoinstall.yaml` on a USB stick or serve it over HTTP
2. Boot the Ubuntu installer
3. Point the kernel boot param to the file:

```
autoinstall ds=nocloud-net;s=http://YOUR_SERVER/
```

Or for local USB (label the partition `cidata`):

```
autoinstall ds=nocloud;
```

4. Go grab a coffee. Come back to a fully set up machine.

## Password

The password is hashed in the file. If you need to change it, generate a new hash:

```bash
openssl passwd -6 'your_new_password'
```

Then replace the `password` field in the yaml.

## After Install

The machine reboots automatically when done. Log in with `fslab` and your password. Everything should be ready to go.

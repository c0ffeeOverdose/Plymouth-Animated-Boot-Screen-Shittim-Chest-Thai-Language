# Shittim Chest Animated Boot Screen Shell Script

This is a shittim chest themes?
nah I just want share The theme I'm using


## Instructions 

1. Install Plymouth themes:

`sudo apt install plymouth-themes`

2. Go to the plymouth themes folder

`
cd /usr/share/plymouth/themes
`

3. Create new theme folder

`
sudo mkdir ./shittim-chest
`

4. Move into your new theme folder.

`
cd shittim-chest
`

3. Clone this repo contents into the folder.

`
sudo git clone https://github.com/c0ffeeOverdose/Plymouth-Animated-Boot-Screen-Shittim-Chest-Thai-Language.git .
`
The dot at the end will clone the contents of the template folder into your new theme folder. 

### Installation
1. Install the theme using this script:

```
 sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/shittim-chest/shittim-chest.plymouth 100
```

2. Select the default theme.
`sudo update-alternatives --config default.plymouth`
And select the number for your theme (I can't say this for sure but if the theme you want is under 0 for the auto mode, then I would select that as I think it boots in faster than manual)

3. Update the initramfs image.

`
sudo update-initramfs -u
`

4. Now reboot.

If you want to install this on < Ubuntu 16.04, change the path from /usr/share/plymouth to /lib/plymouth/ . You need to do this on the eionix-cat.plymouth file also.

Also other possible perks:

I found some scripts that are supposed to improve the transitions etc between Plymouth and the other parts of the start up process. I don't know if they worked for me or not. I had trouble getting the plymouth-gdm thing working as it seems that it's primarily something to do with pre-gdm3 versions and I'm on Ubuntu 18.04

Anyway:

- Edit the file /etc/initramfs-tools/conf.d/splash and add this line:

`
FRAMEBUFFER=y
`

- To enable smooth transition you have to disable your display manager unit, e.g.

`
systemctl disable gdm.service
`

- Enable the respective DM-plymouth Unit (GDM, LXDM, SLiM units provided), e.g.

`
systemctl enable gdm-plymouth.service
` 
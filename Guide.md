'''console
root@archiso ~ # ls /usr/share/kbd/keymaps/**/*.map.gz
'''

'''console
# loadkeys de-latin1
'''
'''console
# ip link 
'''
'''console
# ping archlinux.org
'''
'''console
# timedatectl set-ntp true
'''
'''console
# fdisk -l
'''
'''console
# cfdisk
	select dos
	select freespace
		size
		enterloadke
		select primary
		select bootable
		select write
		yes
	select freespace
		size
		enter
		select primary
		select write 
		yes
	optional for home [select freespace
		size
		enter
		select primary
		select write 
		yes]
'''
'''console
# mkfs.ext4 /dev/sda1
'''
'''console
# mkswap /dev/sda2
'''
'''console
# swapon /dev/sda2
[# mkfs.ext4 /dev/sda3 ]
'''
'''console
# mount /dev/sda1 /mnt
[mkdir /mnt/home
mount /dev/sda3 /mnt/home]
'''
'''console
# nano /etc/pacman.d/mirrorlist
'''
'''console
# pacstrap /mnt base base-devel linux linux-firmware nano man-db man-pages texinfo
'''
'''console
# genfstab -U /mnt >> /mnt/etc/fstab
'''
'''console
# arch-chroot /mnt /bin/bash
'''
'''console
# ln -sf /usr/share/zoneinfo/Region/City /etc/localtime
# hwclock --systohc
'''
'''console
# nano /etc/locale.gen
'''
'''console
# locale-gen
'''
'''console
# nano /etc/locale.conf
	LANG=en_US.UTF-8
'''
'''console
# nano /etc/vconsole.conf
	KEYMAP=de-latin1
'''
'''console
# nano /etc/hostname
	myhostname
'''
'''console
# nano /etc/hosts
	127.0.0.1	localhost
	::1		localhost
	127.0.1.1	myhostname.localdomain	myhostname
'''
'''console
# passwd
'''
'''console
# pacman –S grub os-prober
'''
'''console
# grub-install /dev/sda
# grub-mkconfig –o /boot/grub/grub.cfg
'''
'''console
# exit
# reboot
'''
'''console
# ip link
	find interface "enp0s3" (in my case)
'''
'''console
# nano /etc/systemd/networnaok/enp0s3.network
	[Match]
	name=en*
	[Network]
	DHCP=yes
'''
'''console
# systemctl restart systemd-networkd
# systemctl enable systemd-networkd
'''
'''console
# nano /etc/resolv.conf
	nameserver 8.8.8.8
	nameserver 8.8.4.4
'''
'''console
# pacman -S  xorg-server sudo bash-completion
'''
'''console
# EDITOR=nano visudo
	Recommendation 1 : Create new group called sudo and uncomment this line : 		# %sudo ALL=(ALL) ALL

	Recommendation 2 : Just use wheel group, to do so uncomment this line:
	# %wheel ALL=(ALL) ALL

'''
'''console
# useradd -m -g wheel -s /bin/bash username
'''
'''console
# passwd username
'''
'''console
# pacman -S plasma konsole networkmanager net-tools ntp
'''
'''console
# systemctl enable ntpd
'''
'''console
# reboot
'''
'''console
# uname -r
# sudo pacman -S linux-lts
# sudo pacman install linux-lts-headers
'''
'''console
# pacman -S ttf-freefont
'''

'''console
# sudo systemctl enable sddm
'''


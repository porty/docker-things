FROM porty/archlinux

RUN pacman -S --noconfirm --noprogressbar samba

RUN useradd -u 1000 -M shorty

ADD smb.conf /etc/samba/smb.conf

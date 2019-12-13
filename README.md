udev-drivesync
==============

exec rsync script upon usb drive mounting

append to /etc/udev/rules.d/local.rules

    ## if we have a valid ID_FS_LABEL_ENC, and it's USB, try udev-drivesync
    ENV{ID_FS_LABEL_ENC}=="?*", ACTION=="add", SUBSYSTEMS=="usb", \
      RUN+="/usr/local/sbin/udev-drivesync %k &"

copy udev-drivesync into /usr/local/sbin/

copy the .rsync files and uuid.list into /etc/drivesync/

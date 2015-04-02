# Apr 2nd 2015 by Wojciech Furmankierwicz wfurmank@redhat.com

# A fix for iscsi service: target.service losing (refusing to apply) config after reboot,
# because of detecting LVM header on served devices

# This is /usr/bin/targetctlfix script, a fix for targetd.service losing config after reboot.
# Tested on RHEL 7.1 with:
#   python-rtslib-2.1.fb50-1.el7.noarch
#   targetcli-2.1.fb37-3.el7.noarch
#   targetd-0.7.1-1.el7.noarch

# Instructions:
# Configure iscsi targets with targetcli so you have /etc/target/saveconfig.json correctly populated.
# Place this script into /usr/bin/targetctlfix file
# Replace all /usr/bin/targetctl commands with /usr/bin/targetctlfix in /usr/lib/systemd/system/target.service
# Reboot the system

## Autorun at boot
Once you cloned this repo under `/opt` run the following commands:

	$ sudo cp docker-compose@.service /lib/systemd/system
	$ sudo systemctl daemon-reload

In order to be able to manage the files in your shared folder, `owner:group` have to match the ones set in the container `smbuser:smbshare`
respectively `UID 100` and `GUID 101`.

To do so run:

	$ sudo groupadd -g 101 smb
	$ sudo gpasswd -A $USER smb

NB: For the changes to take effect you need to either logout/reboot your system or start a new login shell

	$ sudo systemctl start docker-compose@SambaSharesVM.service
	$ sudo systemctl enable docker-compose@SambaSharesVM.service

If you get the following error message: 
docker-compose not found, make sure it's under `/usr/bin/docker-compose`. 
If not, install it (according to your distro) or create a symbolic link for it
`ln -s $(which docker-compose) /usr/bin/docker-compose`.


## Autorun at boot
After you have cloned this repo in `/opt` run the following command:

    $sudo cp docker-compose@.service /lib/systemd/system
    $sudo systemctl daemon-reload
    $sudo systemctl start docker-compose@SambaSharesVM.service
    $sudo systemctl enable docker-compose@SambaSharesVM.service

If docker-compose can't be found, check if is in `/usr/bin/docker-compose`. If not, install it or create a symbolic link `ln -s $(which docker-compose) /usr/bin/docker-compose`.
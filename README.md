Rename `.env.example` to `.env`, change it according to your preferences, then start the container with `docker-compose up -d`. It will automatically start at boot since `restart: unless-stopped` is the default.

To make the permission work, add a new group on your host system with the `101` GID, then add yourself ot it, as below.

    $sudo groupadd -g 101 smb
    $sudo gpasswd -a $USER smb

Now you can change the owner and permissions of the shared folders on the host system.

    $sudo chown 100:101 /pathname/to/shared_foleder
    $sudo chmod -R 775 /pathname/to/shared_foleder
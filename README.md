# Manual setup

## Traefik
Run the following commands:
```sh
sudo mkdir /var/traefik
sudo touch /var/traefik/acme.json
sudo chown -R gitlab-runner:gitlab-runner /var/traefik
```

## Docker

### Multi Arch Support
While building Python images for AMD64 I got errors maybe due to the missing support to this type of platform.
If you run the following commands
```sh
docker buildx inspect --bootstrap
sudo apt install -y qemu-user-static
docker buildx inspect --bootstrap
```
You will notice that after installing **qemu-user-static**, the numbers of supported platforms changed.

For more details check this:
https://stackoverflow.com/questions/71239969/multi-arch-docker-build-python-arm64-command-lsb-release-a-returned-no 

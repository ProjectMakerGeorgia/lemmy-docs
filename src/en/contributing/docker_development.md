# Docker Development

## Dependencies
### Debian-based distro

```bash
sudo apt install git docker-compose
sudo systemctl start docker
git clone https://github.com/ProjectMakerGeorgia/lemmy
```

### Arch-based distro

```bash
sudo pacman -S git docker-compose
sudo systemctl start docker
git clone https://github.com/ProjectMakerGeorgia/lemmy
```

## Running

```bash
cd docker/dev
./docker_update.sh
```

and go to http://localhost:1236

*Note: many features (like docs and pictures) will not work without using an nginx profile like that in `ansible/templates/nginx.conf`.

To speed up the Docker compile, add the following to `/etc/docker/daemon.json` and restart Docker.
```
{
  "features": {
    "buildkit": true
  }
}
```

If the build is still too slow, you will have to use a [local build](local_development.md) instead.

# Self-Hosted Media Server

This repository contains the configuration files for a self-hosted media server setup using Docker and docker-compose. It includes several popular services for media management, downloading, and streaming.

## Services Included

- Prowlarr: Indexer manager/proxy
- Sonarr: TV show management and automation
- Radarr: Movie management and automation
- Bazarr: Subtitle management and download
- qBittorrent: BitTorrent client
- Jellyfin: Media server
- Filebrowser: Web file manager
- Audiobookshelf: Audiobook and podcast server
- Readarr: Book management and automation

## Prerequisites

- Docker
- docker-compose
- Sufficient storage space for media files and downloads

## Setup Instructions

1. Clone this repository:

```bash:
git clone https://github.com/LedoKun/docker-compose-collection.git
cd docker-compose-collection
```

2. Copy the example environment file and modify it according to your needs:

```bash:
cp env.example .env
```

Edit the `.env` file to set your desired paths, ports, and other configurations.

3. Create the necessary directories as specified in your `.env` file.

4. Start the services:

```bash:
docker-compose up -d
```

## Configuration

The `docker-compose.yml` file defines all the services and their configurations. The `.env` file contains environment variables used by docker-compose to customize the setup.

Key configuration points:

- `PUID` and `PGID`: Set these to match your user's UID and GID
- `TZ`: Set your timezone
- `CONFIG_ROOT`: Directory for storing service configurations
- `MEDIA_ROOT`: Directory for your media files
- `DOWNLOAD_ROOT`: Directory for downloads

Ports for each service can be customized in the `.env` file.

## Accessing Services

After starting the containers, you can access the services at the following URLs (replace `localhost` with your server's IP if accessing remotely):

- Prowlarr: `http://localhost:9696`
- Sonarr: `http://localhost:8989`
- Radarr: `http://localhost:7878`
- Bazarr: `http://localhost:6767`
- qBittorrent: `http://localhost:8085`
- Jellyfin: `http://localhost:8096`
- Filebrowser: `http://localhost:8088`
- Audiobookshelf: `http://localhost:13378`
- Readarr: `http://localhost:8787`

## Maintenance

- To update all containers: `docker-compose pull && docker-compose up -d`
- To view logs: `docker-compose logs -f [service_name]`
- To stop all services: `docker-compose down`

## Security Considerations

This setup is intended for use in a secure local network. If you plan to expose these services to the internet, please implement proper security measures such as using a VPN or a reverse proxy with authentication.

## License

[MIT License](LICENSE)
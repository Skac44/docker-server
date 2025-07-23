# docker-server
This is a repo dedicated to explain docker server compose stacks and their functionality for a self-hosted server
which conatins various services including media management, file sharing, game hosting, and more
 
## **This server includes torrent-related services (qBittorrent, Transmission, Jackett) for testing purposes only.**
- No copyrighted material is or was distributed/stored.
- These services were configured strictly to:
  - Verify Docker container functionality.
  - Test network performance (port forwarding, etc.).
  - Experiment with automation (Sonarr/Radarr integration).

**No active torrents are maintained, and download directories are empty/monitored.**

# Server Specs 2025-07
- OS: Linux Mint 22.1
- CPU: Intel i7-2600
- GPU: NVIDIA Quadro p400
- Memory: 16GB DDR3 RAM
- Disk Space: 1TB of HDD

# Service Overview
## SWAG (Secure Web Application Gateway)
- Image used: lscr.io/linuxserver/swag
- Purpose: Reverse proxy with automatic Let's Encrypt certificate generation
- Features:
  - Automatic SSL certificate generation using ZeroSSL
  - DNS validation with Cloudflare
  - Wildcard subdomain support
- Configuration:
  - Requires DNS plugin configuration for Cloudflare
  - Needs domain name (site.com) and email for certificate generation

## Nextcloud Stack
### Components:
- Nextcloud image: lscr.io/linuxserver/nextcloud:latest
- MariaDB image: lscr.io/linuxserver/mariadb:latest
- OnlyOffice image: onlyoffice/documentserver
- Purpose: Self-hosted cloud, sharing and office work platform
- Features:
  - Integrated document editing with OnlyOffice
  - MariaDB backend for data storage


## Media Management Stack
### Components:
- Jellyfin: Media server with NVIDIA GPU acceleration
- Sonarr: TV show management
- Radarr: Movie management
- Jackett: Torrent proxy 
- Transmission: Torrent client
- Purpose: Complete media acquisition, organization, and streaming solution
- Features:
  - Hardware-accelerated transcoding
  - Automated download and organization
  - Multiple media libraries (movies, TV shows, cartoons)

## qBittorrent
- Image: lscr.io/linuxserver/qbittorrent:latest
- Purpose: Torrent client with web interface

## Minecraft Server
- Image: itzg/minecraft-server
- Version: PaperMC 1.21.5 (experimental channel)
- Features:
  - Online mode disabled
  - Custom server icon support
  - Whitelist capability



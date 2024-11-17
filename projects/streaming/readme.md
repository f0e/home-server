## directory structure

```
/mnt/user/media/
├── custom
│   └── Prowlarr-Indexers (https://github.com/dreulavelle/Prowlarr-Indexers)
├── media
│   ├── downloading
│   │   ├── blackhole
│   │   │   ├── radarr
│   │   │   └── sonarr
│   ├── local
│   │   ├── books
│   │   ├── movies
│   │   ├── music
│   │   └── tv
│   └── streaming
│       ├── movies
│       └── tv
└── transcodes
    └── streaming-plex
```

### setup

rclone is not included in the docker-compose anymore because I'm running it on bare metal on startup:
```
rclone mount zurg: /mnt/cache/remote/zurg --allow-other --allow-non-empty \
 --cache-dir=/mnt/user/media-local/rclone \
 --dir-cache-time 5s --buffer-size 32M \
 --async-read=true --no-check-certificate --no-traverse --ignore-existing \
 --daemon
```

### example .env

```.env
MEDIA_LOCATION=/mnt/user/media/media
TRANSCODES_LOCATION=/mnt/user/media/transcodes
CUSTOM_LOCATION=/mnt/user/media/custom
CONFIG_LOCATION=/mnt/user/appdata/compose/streaming-server
```

# installation steps

(todo, collecting links atm, will write up later)

https://trash-guides.info/Sonarr/Sonarr-recommended-naming-scheme

https://trash-guides.info/Radarr/Radarr-recommended-naming-scheme

https://github.com/westsurname/scripts#blackhole

https://github.com/dreulavelle/Prowlarr-Indexers

https://trash-guides.info/Radarr/Radarr-collection-of-custom-formats/ disable repack prefer
## directory structure

```
/mnt/user/media/
├── custom
│   └── [Prowlarr-Indexers](https://github.com/dreulavelle/Prowlarr-Indexers)
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
    └── plex-streaming
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

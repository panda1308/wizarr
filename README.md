# Wizarr 

<img src="./screenshots/wizard.png" height="200">

<img src="https://github.com/Wizarrrr/wizarr/actions/workflows/docker-build.yml/badge.svg">

<img src="https://hosted.weblate.org/widgets/wizarr/-/svg-badge.svg">

Wizarr is a automatic user invitation system for Plex. Create a unique link and share it to a user and they will automatically be invited to your Plex Server! They will even be guided to download the Plex client and instructions on how to use your requests software!

### **Discord**
[Join Our Discord Server](https://discord.gg/UfQvvz7eXx)

![alt](./screenshots/welcome.png)


## Major Features Include

- Automatic Invitation to your Plex Server
- Secured invitation environment
- Plug and Play SSO Support*
- Guide user on how to download Plex client
- (Optional!) Requests Integration: Guide users on how to request Movies (Overseerr, Ombi...)

## Planned features

- Discord Bot Integration
- jellyfin support
- Multilingual Support


## A note on SSO (Authelia, Authentik, etc)

As mentionned in the features, Wizarr supports SSO via disabling its inbuilt authentication!
Attention! While setting up Wizarr, you will still be asked for a username and password, but these will be ignored if you enabled `DISABLE_BUILTIN_AUTH`
To Setup, protect the Wizarr App with your SSO provider using Authelia for example or in the case of Authentik, using a Proxy Provider.
However, make sure to whitelist the following paths, or users will not be able to join!
- /join
- /j/*
- /setup*
- /static/*

## Installation

### Docker Compose (recommended)

1. Download Docker-compose file

```
version: "3.8"
services:
  wizarr:
    container_name: wizarr
    image: ghcr.io/wizarrrr/wizarr
    ports:
    - 5690:5690
    volumes:
      - ./data:/data/database
    environment:
      - APP_URL=https://join.domain.com
      - DISABLE_BUILTIN_AUTH=false #Set to true ONLY if you are using another auth provider (Authelia, Authentik, etc)
      - TZ=Europe/London #Set your timezone here
```

2.  **Important** Edit Variables

    APP_URL: Public Facing Url of your Wizarr instance
    DISABLE_BUILTIN_AUTH: Set to true if you want to disable the built in authentication and use SSO instead

3.  Run `docker compose up -d` or for older Docekr versions: `docker-compose up -d`
4.  Access WebUI at http://localhost:5690 and setup your Plex Server


## Translations

We use Weblate to translate Wizarr, help us out by clicking [here](https://hosted.weblate.org/engage/wizarr/)

<img src="https://hosted.weblate.org/widgets/wizarr/-/app/multi-auto.svg" alt="Translation status" />
</a>

## Thank you

A big thank you ❤️ to these amazing people for contributing to this projet!
<a href="https://github.com/wizarrrr/wizarr/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=wizarrrr/wizarr" />
</a>


## License

Wizarr is provided under the 'MIT' license, see [here](./LICENSE.md)

The Translations however are provided under a MIT license.

## Screenshots

*These may be out of date*

#### Light Mode
![alt](./screenshots/share.png)
![alt](./screenshots/tips-light.png)
![alt](./screenshots/invitation.png)
![alt](./screenshots/Download.png)
![alt](./screenshots/request.png)

#### Dark Mode
![alt](./screenshots/download_dark.png)
![alt](./screenshots/tips-dark.png)
![alt](./screenshots/join_dark.png)
![alt](./screenshots/welcome_dark.png)


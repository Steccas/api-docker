<p align="center">
  <a href="https://github.com/Steccas/xbs-api-docker/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://github.com/Steccas/xbs-api-docker/network/members"><img src="https://img.shields.io/github/forks/Steccas/xbs-api-docker.svg?style=for-the-badge"></a>
  <a href="https://github.com/Steccas/xbs-api-docker/issues">
      <img src="https://img.shields.io/github/issues/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://github.com/Steccas/xbs-api-docker/issues">
      <img src="https://img.shields.io/github/issues-closed/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://github.com/Steccas/xbs-api-docker/stargazers">
    <img src="https://img.shields.io/github/stars/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://GitHub.com/Steccas/xbs-api-docker/pull">
    <img src="https://img.shields.io/github/issues-pr/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://GitHub.com/Steccas/xbs-api-docker/pull">
    <img src="https://img.shields.io/github/issues-pr-closed/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://GitHub.com/Steccas/xbs-api-docker/commit">
    <img src="https://img.shields.io/github/last-commit/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://GitHub.com/Steccas/xbs-api-docker">
    <img src="https://img.shields.io/github/repo-size/Steccas/xbs-api-docker.svg?style=for-the-badge">
  </a>
  <a href="https://GitHub.com/Steccas/xbs-api-docker">
    <img src="https://img.shields.io/github/workflow/status/Steccas/xbs-api-docker/Docker.svg?style=for-the-badge">
  </a>
  <a href="https://linkedin.com/in/lucasteccanella">
    <img src="https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555">
  </a>
  <a href="https://www.buymeacoffee.com/steccas" target="_blank">
    <img src="https://cdn.buymeacoffee.com/buttons/lato-yellow.png" alt="Buy Me A Coffee" height="27.8">
  </a>
</p>

# xBrowserSync API for Docker customized

Hi, this is custom version of the [official xBrowserSync Docker](https://github.com/xbrowsersync/api-docker).
I made it to simplify my personal deployment and fit my personal needs.

## Changes made
- [healthcheck.js](healthcheck.js) and [settings.json](settings.json) are going to be copied inside the container by the [dockerfile](dockerfile); so it will not longer be necessary to be mounted as volumes in [docker-compose.yml](docker-compose.yml) unless needed.
- [dockerfile](dockerfile) will build from latest alpine
- [dockerfile](dockerfile) will get latest version of [xBrowserSync API](https://github.com/xbrowsersync/api), CI/CD Will keep the image build fresh, so the API in use will always be updated if you use systems like watchtower.
- [docker-compose.yml](docker-compose.yml) will fetch latest version of the image.
- Removed caddy, so you can integrate the containers with an existing proxy like Traefik or Jwilder's proxy.
- ARM Support

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create.

And this project can be greatly improved!

Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

You can also consider to help with a donation and checking my links ❤️
<br>
<a href="https://linktr.ee/steccas"><img alt="check!" src="https://img.shields.io/badge/check-offers-green?style=for-the-badge&logo=linktree">
</a>
<a href="https://github.com/sponsors/Steccas" target="_blank">
    <img src="https://img.shields.io/badge/sponsor-%23F5F5F5.svg?&style=for-the-badge&logo=github&logoColor=pink" alt="GitHub Sponsor">
</a>
<a href="https://www.buymeacoffee.com/steccas" target="_blank">
    <img src="https://cdn.buymeacoffee.com/buttons/lato-yellow.png" alt="Buy Me A Coffee" height="27.8">
</a>

## Running a production-ready service

  1. Clone the [this repo](https://github.com/Steccas/api-docker):

      ```
      git clone https://github.com/Steccas/api-docker.git
      ```
  
  2. Open the [`.env`](.env) file in a text editor and update the `API_HOSTNAME` value to correspond to the host name that the API service will be exposed over (ensure you have configured your DNS provider to point the desired host name to your host's IP address). Also, change the `DB_USERNAME` and `DB_PASSWORD` values to any of your choosing.

  3. (Optionally) open the [`settings.json`](settings.json) file and include any custom [settings](https://github.com/xbrowsersync/api#3-modify-configuration-settings) values you wish to run on your service. Important: do not change the `db.host` value. And remember in this case to uncomment the volume mounting in [docker-compose.yml](docker-compose.yml).
  
  4. Run the following command to start the containers:

      ```
      docker-compose up -d
      ```

      You can now access your xBrowserSync API service at the value of `API_HOSTNAME` defined in the [`.env`](.env) file.

## Issues and feature requests
Please cosnider that this is just a fork, so if the problem doesn't exists just in this implementation please log Docker-related issues directly in the [api-docker Issues list](https://github.com/xbrowsersync/api-docker/issues), if you have found an issue with the xBrowserSync API itself or wish to request a new feature, do so in the [api Issues list](https://github.com/xbrowsersync/api/issues/).

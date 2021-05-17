# MyBB 1.8 Dockerfile & Docker Compose Recipe

With the recent announcements of the 1.10 branch we've also got some great news for both plugin developers and theme designers. In recent weeks, work has been underway to create an official Docker image for the MyBB 1.8 series. This work has been taken on by a community member who proposed such a solution and set to work on getting it done. Also provided within the repository are two example `docker-compose.yml` files, to be used with Docker Compose or Swarm. Docker is a technology for creating lightweight containers to manage and orchestrate software. It works across multiple platforms, and makes it easy to quickly get a live instance of the current MyBB version running with a variety of different configurations without requiring much effort to install database management systems and such on your machine. Docker is a brilliant tool for developers to quickly prototype ideas in a fresh, consistent environment. You can find out more information on Docker [here](https://docs.docker.com/get-started/).

Developers can immediately download and start using the current MyBB 1.8.13 Docker image from our official Docker Hub registry account (found [here](https://hub.docker.com/r/mybb/mybb/)) by running the following command:
```
docker pull mybb/mybb:latest
```
Alternatively, for those who would like to view the source, make amendments or just generally prefer to build their own images - you can view the official GitHub repository [here](https://github.com/mybb/docker-compose/). Ample instructions for use are provided within the [README.md](https://github.com/mybb/docker-compose/blob/master/README.md) file. This project is far from complete and we do not recommend it for production use, only for development and staging systems. MyBB's current installation and upgrade systems make full automation with Docker a difficult feat to accomplish but we're hoping to include easier ways to do this in the future 1.10 series of releases.

We hope that avid plugin and theme developers make good use of the Docker images that we'll be releasing and improving upon, any and all constructive feedback (and pull requests!) is welcome.

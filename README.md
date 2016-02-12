# Docker Base Image with NVM preinstalled

[![tzenderman/docker-nvm](http://dockeri.co/image/tzenderman/docker-nvm)](https://registry.hub.docker.com/u/tzenderman/docker-nvm/)

You probably already version the packages you use in your project, but have you ever run into an issue where you or other developers on your team can't reproduce an issue exactly the way someone else on the dev team is experiencing it? This really grinds my gears, so I made this image to prevent that situation! With this Docker image, you can version even your project's languages to avoid any silly differences between environments.

Docker Hub Link: https://registry.hub.docker.com/u/tzenderman/docker-nvm/

## Want to use this in your project?

Simply add

`FROM tzenderman/docker-nvm:latest`

to the top of your Dockerfile and that's it. You'll now have nvm pre-installed in your container. Want to manage the node version in your project's repo? Simply add `.nvmrc` to your project's root, next to your `Dockerfile`.

And then manage the install inside your project's Dockerfile like this:

    WORKDIR /code

    COPY .nvmrc /code/.nvmrc
    RUN /bin/bash -l -c "nvm install;" \
        "nvm use;"

Now, when you want to upgrade Node to v5.6.0, simply update your `.nvmrc` to `5.6.0`, rebuild your Docker image, and that's it!

Links:

NVM: https://github.com/creationix/nvm

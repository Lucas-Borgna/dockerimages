# dockerimages
all my dockerfiles to build dockerimages and upload them into dockerhub. Can be used for a GitLab CI image.

## Building Images

Change to directory with Dockerfile

Use the following command to build the image with the Dockerfile settings.

```docker build -t imagename```


## Pushing image to DockerHub

Tag the image to push

```docker tag imagename:tagname username/imagename:tagname```

push the image to docker hub

```docker push username/imagename:tagname```

may require a login to docker hub with ```docker login```

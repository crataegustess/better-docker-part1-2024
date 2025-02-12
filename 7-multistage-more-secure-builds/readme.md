# Exercise 7 - More secure builds - done better

## Problem
When we have to install dependencies from a private registry we will need to authenticate. 
We don't want the credentials stored in version control but importantly, we also don't want our credentials visible in the layers manifest or build logs for the deployment image.

## Principle(s)
- Build variables
- Multi-stage builds

## Detail
We have already used build variables to inject values at build time and set environment variables for use deeper in.

We can also create stages in our dockerfiles. Earlier stages and their layers are discarded. Only the last stage is baked so our credentials won't be stored in a layer we push.

## Exercise

### Hide the credential
- Create a multistage version of your exercise 6 Dockerfile to make sure the build arguments and tokens are not baked into the final image `docker build -t docker-deep-dive/ex7/multistage -f Dockerfile.better --progress=plain --build-arg TOKEN=your-pat-token .`
- Check the layers of the multistage baked image by running `docker history docker-deep-dive/ex7/multistage`
- Run it to check it works `docker run --rm docker-deep-dive/ex7/multistage`
  
Remember to record your results at each stage!

## References
https://docs.docker.com/build/guide/build-args/

https://docs.docker.com/build/building/variables/

https://docs.docker.com/reference/cli/docker/image/history/

https://docs.docker.com/build/building/multi-stage/


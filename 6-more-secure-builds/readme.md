# Exercise 6 - More secure builds

## Problem
When we have to install dependencies from a private registry we will need to authenticate. 
However, we don't want the credentials stored in version control. 

## Principle(s)
- Build variables

## Detail
We can use build variables to inject values at build time and set environment variables for use deeper in.

## Exercise
### Use the credential
- Attempt to build the image using the original file. PS This is expected to fail. `docker build -t docker-deep-dive/ex6/original -f Dockerfile.original --progress=plain .`
- Ensure you have a credential you can use to download the private dependencies from the github package manager (a classic Personal Access Token)
- Create a better dockerfile that uses build arguments and environment variables to get the build to work `docker build -t docker-deep-dive/ex6/better -f Dockerfile.better --progress=plain --build-arg TOKEN=your-pat-token .`
- Run it to check it works `docker run --rm docker-deep-dive/ex6/better`
- Check the layers of the baked image by running `docker history docker-deep-dive/ex6/better`

Remember to record your results at each stage!

## References
https://docs.docker.com/build/guide/build-args/

https://docs.docker.com/build/building/variables/

https://docs.docker.com/reference/cli/docker/image/history/

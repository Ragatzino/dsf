# dsf

In order to know which images are running on a kubernetes cluster, you can list running and defined pods and see their images.

This is good, but on the docker registry side of things, if your image is cached on a node and your pod is running for long, you might not see that there is usage.

And when you have a big community of developers, you might want to avoid to delete images that are built and used, but still want to cleanup your non cache registries.

This is the point of this project.

## Architecture

- 👷 Go API that fetch all declared images, then ping the registries (with potential filtering on the fqdn), save info on some db
- 👷‍♂️ React TS UI that fetch all infos on the api and display it for monitoring purpose, with OIDC / basic auth



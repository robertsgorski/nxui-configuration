# Gitea status updater

This repository holds the project for updating the commit status of the Gitea repository. This is a GitOps feature, it works like this:

- the user pushes kubernetes manifest to the Gitea repository
- the flux source controller reconciliates the sources
- the flux notification controller sends the status as the REST request to this server
- the server updates the commit status using the Gitea API.

So, basically this server translates generic flux notification request to the Gitea format in order to integrate Flux with Gitea.

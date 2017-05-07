# nirask-starbound-server-update-app-build
Docker container for a Starbound Server's deployment verification

This container installs the Travis and Gerrit servers, along with Git, all for use locally.

Somehow monitor the update-app-build directory (git repo) to trigger local pushes to Gerrit-frontended Travis builds when it is updated This will only update from the web app container, so we can be safe to do most of the deploying without guards.

Travis builds will trigger a stop of the server, as well as a backup of the existing files before overwriting them. If any of these fail for any reason, the web app will be notified to report the failure back to the user.

We actively develop ShellHub to add new features and remove bugs, and encourage you to ensure your ShellHub self-hosted instance is using the most up-to-date version.

## Steps

1. Change to ShellHub working directory
2. Stop the instance: `./bin/docker-compose stop`
3. Fetch remote changes: `git remote update origin`
4. Checkout the latest stable release: `git checkout {{ shellhub.latest_version }}`
5. Bring up the instance: `./bin/docker-compose up`

!!! warning "Versions prior to `v0.4.0` don't have `docker-compose` wrapper"

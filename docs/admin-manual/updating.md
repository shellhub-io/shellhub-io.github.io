We actively develop ShellHub to add new features and remove bugs, and encourage you to ensure your ShellHub self-hosted instance is using the most up-to-date version.

## Steps

1. Change to ShellHub working directory
2. Stop the instance: `make stop` (use `./bin/docker-compose stop` if you are running a version prior to `v0.6.0`)
3. Fetch remote changes: `git remote update origin`
4. Checkout the latest stable release: `git checkout {{ shellhub.latest_version }}`
5. [Upgrade MongoDB](#mongodb-upgrading-instructions) (If you're running ShellHub for the very first time, simply skip this step)

6. Bring up the instance: `make start`

## MongoDB upgrading instructions

Starting from ShellHub `v0.6.0`, MongoDB has been updated to 4.4 series.
If you're running ShellHub for the very first time, simply skip the section.
However, if you have been using ShellHub for a while, you have to upgrade the
MongoDB data files before attemping an upgrade ShellHub itself.

Initially, ShellHub was using MongoDB 3.4 series. To upgrade its data files
to 4.4 series, you need to run the MongoDB upgrade script by running the following command:

```make upgrade_mongodb```

!!! warning "Make sure to backup all MongoDB data files before proceeding with upgrade"




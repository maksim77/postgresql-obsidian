<h1 align="center">
  Obsidian + PostgreSQL = ❤️
</h1>

<p align="center">
    An <a href="https://obsidian.md">Obsidian</a> plugin to upload your notes' metadata to your database.
</p>

## Features

-   send the Dataview annotations of a page to a PostgreSQL database
    -   this lets you use SQL queries on your data and integrate it with other tools, such as [Grafana](https://github.com/grafana/grafana/blob/main/README.md)

## Installation

1. Get a PostgreSQL database (see section below)
2. Set your PostgreSQL connection string inside the settings
3. Open the command panel and type "PostgreSQL" to see the list of available commands

### Setting up a PostgreSQL database

-   Follow [this guide](https://www.postgresql.org/download/) to self-host PostgreSQL on your computer or a remote server.
-   You can also use a managed provider
    -   [Amazon RDS](https://aws.amazon.com/fr/rds/postgresql/resources/)
    -   [ElephantSQL](https://www.elephantsql.com/)
    -   [Managed PostgreSQL for Heroku](https://www.heroku.com/postgres)

I personally prefer to self-host PostgreSQL on an offshore server to protect my privacy. However, do note that it takes a bit more knowledge since if you host on a remote server, you will learn how to enable network encryption (SSL) to prevent unauthorized intermediaries from snooping on your data.

I did not try the managed providers that I listed above, but they are from reputable companies and provide way more storage and compute power than you will ever need to host the data generated by this plugin.

### Where is my data stored?

The data produced by `postgresql-obsidian` is made available to you under the `obsidian` database schema.

You can use PostgreSQL views to extract and format the information that you need.

### Why should I send my data to a PostgreSQL database?

Sending the metadata of your notes to a PostgreSQL database will allow you to explore it with other tools, such as [Grafana](https://github.com/grafana/grafana/blob/main/README.md).

Here is a screenshot of the Grafana dashboard I made to monitor my personal health:

![Grafana dashboard of clouedoc's health, made using the data produced by the postgresql-obsidian plugin. It features charts of an ok-ish lifestyle.](./assets/grafana-dashboard.png)

## Contributing

Contributions are what make the open source community such an amazing place to be, learn, inspire, and create. Any contributions you make are **greatly appreciated**!

### Development

1. Open this repository on Gitpod
2. Go to https://gitpod.io and copy your workspace SSH username and host inside `sync.sh`
3. Copy `sync.sh` inside `.obsidian/plugins`
4. Do some modifications on your remote Gitpod development instance
5. Execute `sync.sh` on your local computer (the plugin's files should get copied)
6. Iterate

### TODO

-   [x] overcomplicated development workflow
-   [x] set PostgreSQL URL in the settings
-   [ ] get various information from the current note
    -   [x] Dataview data
    -   [ ] list content
-   [ ] commands
    -   [x] upload current note
    -   [ ] bulk upload
    -   [ ] automatic upload on edit
-   [ ] submit to Obsidian plugin registry

### Useful links

-   [Obsidian API documentation](https://github.com/obsidianmd/obsidian-api)

## Attribution

-   Thanks to [pg](https://github.com/brianc/node-postgres/tree/master/packages/pg) for making it possible to easily connect to a PostgreSQL database from JavaScript.
-   Thanks to the [Rush Stack](https://github.com/microsoft/rushstack) for providing an easy-to-use ESLint configuration.
-   Thanks to the [Dataview Plugin](https://github.com/blacksmithgu/obsidian-dataview) for making it easy to access a note's metadata.

## License

[MIT](LICENSE.txt)

<div style="display: flex; justify-content: center; vertical-align: middle;">
    <img height=50 src="./assets/obsidian.png" class="center">
    <img height=50 src="./assets/postgres.png" class="center">
</div>

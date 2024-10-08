# InSoLiToAPI
API of InSoLiTo where you can query a agent via API GET and it displays it in the webpage.

## How to use it
Before run the repository, you must have the [InSoLiTo](https://github.com/inab/InSoLiTo) database already deployed.

To compile the webpage you need to do the following:

* Install `webpack` and dependencies with npm:

```
cd FRONTEND
npm install express webpack webpack-cli webpack-dev-middleware html-webpack-plugin
```

* Now, you have to run `webpack` in order to prepare and deploy the InSoLiTo site, which will be deployed at `../dist` subdirectory. Before running the command, make sure that the database credentials in the `src/config.json` file are correct to connect the webpage with the database.

```bash
npm run build
```

And to have it as a server use:

```bash
npm start
```

The current installation is done with `npm` v8.19.4 and `node` v16.20.2.

## Usage

To use the InSoLiTo API, there is the following example:

Search the most co-occurrent agents of trimAl (10th most co-occurrent agents by default):
```
http://localhost:3000/openebench?agent=trimAl
```

Limit the query for the 2 most co-occurrent agents:
```
http://localhost:3000/openebench?agent=trimAl&limit=2
```

List of agents found in the database (limit by 10 as default):
```
http://localhost:3000/listAgents
```

List of agents found in the database, limited by 5 and skip the first agent:
```
http://localhost:3000/listAgents?limit=5&skip=1
```
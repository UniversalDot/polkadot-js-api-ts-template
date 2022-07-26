# polkadot-js-api-ts-template

Beloved template to quickly start hacking in top of any substrate based chain with
`@polkadot/api`.

See [`package.json`](./package.json) to see what's up 🔥🔥.


## Install 

First install [ts-node](https://www.npmjs.com/package/ts-node)

```
npm i ts-node
```
then install all npm packages

```
npm install
```
Optionally, in order to verify that you can connect with our node, run:

````
npm run dev
````

## Run

To run **console** in interactive mode, run:

```
npx ts-node -i
```
Then, we import api dependencies and connect with our node by running:
```
import { ApiPromise, WsProvider } from "@polkadot/api";
const provider = new WsProvider("ws://109.235.70.27:9944");
const api = await ApiPromise.create({ provider });
```

After this, we are able to interact with the API via api variable.

Example api calls:

```
(await api.query.profile.profileCount()).toJSON()
```
Returns the number of profiles.

```
(await api.query.task.tasksOwned('5GrwvaEF5zXb26Fz9rcQpDWS57CtERHpNehXCPcNoHGKutQY')).toJSON()
```
Returns the tasks owner by a specified address.

```
 (await api.query.task.tasks.entries()).toString()
```
Returns all entries of Tasks
# BugLess DApp

BugLess is a decentralized bug bounty platform.

## Building

```
sunodo build
```

### Running the Cartesi Node

```
sunodo run
```

### CLI

To interact with the contract, you may use the BugLess CLI.
For all the options, run the command below.

```
go run ./cli help
```

#### Sending dapp address

```
go run ./cli send dapp-address
```

### Sending bounty

```
go run ./cli send bounty \
    -n "Lua Bounty" \
    -d "Description of Lua bounty" \
    -c ./tests/bounties/lua-bounty/lua-5.4.3-bounty_riscv64.tar.xz                  
```

### Sending sponsor

```
go run ./cli send sponsor -b 0 -n "Sponsor Name" -v 1000
```

### Frontend

Before running the frontend, you should have the `CartesiDApp` address stored in the `NEXT_PUBLIC_DAPP_ADDRESS` enviroment variable.
In order to take hold of this address, you may run the command below and manually extract the address next to `CartesiDApp`.

```
sunodo address-book
```

To set the env var automaticaly, run the following command in the repository root directory.

```
export NEXT_PUBLIC_DAPP_ADDRESS=$(sunodo address-book --json | jq -r .CartesiDApp)
```

To run the frontend, execute the commands below.

```shell
cd frontend
npm install
npm run dev
```

Open http://localhost:3000 in Chrome Browser.

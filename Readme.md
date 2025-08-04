# Soroban Token Deployment + React dApp

This repository contains a tutorial for deploying a fungible token on the Stellar network using Soroban smart contracts, followed by building a React decentralized application (dApp) to interact with the token. This project aims to provide a basic understanding of using Stellar's Soroban for token creation and integrating it with a frontend interface.

## Prerequisites

Before starting, make sure you have:

- Basic familiarity with Rust and React.
- A code editor like VSCode.
- Node.js and npm installed.
- Rust and cargo installed.

## Setup Instructions

1. Clone this repository:
   ```
   git clone https://github.com/jamesbachini/Token-dApp.git
   cd Token-dApp
   ```

2. Install dependencies for the dApp:
   ```
   npm install
   ```

3. Install the Stellar CLI tool for working with Soroban smart contracts:
   ```
   cargo install --locked stellar-cli --features opt
   ```

## Deploying the Token Contract

1. Add WebAssembly target support:
   ```
   rustup target add wasm32-unknown-unknown
   ```

2. Build the WebAssembly binary:
   ```
   cargo build --target wasm32-unknown-unknown --release
   ```

3. Deploy the contract to the Stellar testnet:
   ```
   stellar contract deploy --wasm target/wasm32-unknown-unknown/release/soroban_token_contract.wasm --source YOUR_SOURCE --network testnet
   ```
   Save the contract ID from this step for use in the dApp.

## Running the React dApp

1. Start the development server:
   ```
   npm start
   ```
   The dApp will provide an interface for interacting with your deployed token, including transferring tokens between wallets.

2. Connect your Freighter wallet to interact with the token on the Stellar testnet.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Disclaimer

This project is intended for educational purposes only. The code has not been audited and should not be used with real assets on the Stellar mainnet without proper security review.

## Links

- [Website](https://jamesbachini.com)
- [YouTube](https://www.youtube.com/c/JamesBachini?sub_confirmation=1)
- [Substack](https://bachini.substack.com)
- [Podcast](https://podcasters.spotify.com/pod/show/jamesbachini)
- [Spotify](https://open.spotify.com/show/2N0D9nvdxoe9rY3jxE4nOZ)
- [Twitter](https://twitter.com/james_bachini)
- [LinkedIn](https://www.linkedin.com/in/james-bachini/)
- [GitHub](https://github.com/jamesbachini)



----------------------
### Notes

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh


cargo install --locked stellar-cli --features opt

cargo test

cargo build --target wasm32-unknown-unknown --release

stellar keys generate --global james --network testnet

stellar keys address james

stellar contract deploy --wasm target/wasm32-unknown-unknown/release/soroban_token_contract.wasm --source james --network testnet

// https://www.rapidtables.com/convert/number/ascii-to-hex.html

stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- initialize --admin GCJ3YXU54EUG5VFDOJ5QADWE2OPAB7F5ZB3AX6FNNOK24YX2I4NIR4LJ --decimal 7 --name '' --symbol '""'

stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- mint --to GCJ3YXU54EUG5VFDOJ5QADWE2OPAB7F5ZB3AX6FNNOK24YX2I4NIR4LJ --amount

stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- balance --id GCJ3YXU54EUG5VFDOJ5QADWE2OPAB7F5ZB3AX6FNNOK24YX2I4NIR4LJ

stellar keys generate --global alice --network testnet

stellar keys address soheil

stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- transfer --from GAEY2VVMJKBIG4A2ZEMPF7JFSIEXP256VB2OR4JVNMYITNITTMD4W6PB --to GCVGVU2I35R2XWEWVNOG3DAATB4RGVMQOYDHQQI2V4A7YTTLUSSC3HWM --amount 10000000

stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- balance --id GB6XGMHAXJA4OCCY3U6RNYHET3PJDQG5EVEWX4GYH34QW3GE3O7PICGN

stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- transfer --from GAEY2VVMJKBIG4A2ZEMPF7JFSIEXP256VB2OR4JVNMYITNITTMD4W6PB --to GB6XGMHAXJA4OCCY3U6RNYHET3PJDQG5EVEWX4GYH34QW3GE3O7PICGN --amount 10000000


stellar contract invoke --id CCOCB24RH7R2TKF4QVS4J6GBLZ5IZK4FXWQWMQ6GYRGHNUFPW53VJOFU --source-account james --network testnet -- transfer --from GAEY2VVMJKBIG4A2ZEMPF7JFSIEXP256VB2OR4JVNMYITNITTMD4W6PB --to GB6XGMHAXJA4OCCY3U6RNYHET3PJDQG5EVEWX4GYH34QW3GE3O7PICGN --amount 10000000











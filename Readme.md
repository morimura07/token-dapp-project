curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

rustup target add wasm32-unknown-unknown

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

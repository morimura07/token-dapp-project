curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

rustup target add wasm32-unknown-unknown

cargo install --locked stellar-cli --features opt

cargo test

cargo build --target wasm32-unknown-unknown --release

stellar keys generate --global james --network testnet

stellar keys address james

stellar contract deploy --wasm target/wasm32-unknown-unknown/release/soroban_token_contract.wasm --source james --network testnet

// https://www.rapidtables.com/convert/number/ascii-to-hex.html

stellar contract invoke --id CBT34OXXFXV5UBBZ3XCY6PEYQ5NWZOJLDSG3UGCULICW5QPEAU33UW4Y --source-account james --network testnet -- initialize --admin GD6ERVU2XC35LUZQ57JKTRF6DMCNF2JI5TFL7COH5FSQ4TZ2IBA3H55C --decimal 7 --name '4d79546f6b656e' --symbol '"4d5954"'

stellar contract invoke --id CBT34OXXFXV5UBBZ3XCY6PEYQ5NWZOJLDSG3UGCULICW5QPEAU33UW4Y --source-account james --network testnet -- mint --to GD6ERVU2XC35LUZQ57JKTRF6DMCNF2JI5TFL7COH5FSQ4TZ2IBA3H55C --amount 694200000000

stellar contract invoke --id CBT34OXXFXV5UBBZ3XCY6PEYQ5NWZOJLDSG3UGCULICW5QPEAU33UW4Y --source-account james --network testnet -- balance --id GD6ERVU2XC35LUZQ57JKTRF6DMCNF2JI5TFL7COH5FSQ4TZ2IBA3H55C

stellar keys generate --global soheil --network testnet

stellar keys address soheil

stellar contract invoke --id CBT34OXXFXV5UBBZ3XCY6PEYQ5NWZOJLDSG3UGCULICW5QPEAU33UW4Y --source-account james --network testnet -- transfer --from GD6ERVU2XC35LUZQ57JKTRF6DMCNF2JI5TFL7COH5FSQ4TZ2IBA3H55C --to GBSCBWCPVVYKKPNI2PJFQFEHJJAOSQHQJRUW4EOPPZPZNHI5DNXZZ4SR --amount 10000000

stellar contract invoke --id CBT34OXXFXV5UBBZ3XCY6PEYQ5NWZOJLDSG3UGCULICW5QPEAU33UW4Y --source-account james --network testnet -- balance --id GBSCBWCPVVYKKPNI2PJFQFEHJJAOSQHQJRUW4EOPPZPZNHI5DNXZZ4SR


stellar contract invoke --id CBT34OXXFXV5UBBZ3XCY6PEYQ5NWZOJLDSG3UGCULICW5QPEAU33UW4Y --source-account james --network testnet -- transfer --from GD6ERVU2XC35LUZQ57JKTRF6DMCNF2JI5TFL7COH5FSQ4TZ2IBA3H55C --to GBSCBWCPVVYKKPNI2PJFQFEHJJAOSQHQJRUW4EOPPZPZNHI5DNXZZ4SR --amount 10000000

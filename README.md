# ERC721_NFT

Create an ERC_721 NFT and deploy it using foundry tool.

Based on foundry book: 
https://book.getfoundry.sh/tutorials/solmate-nft.html

# ==================================================================

Install Foundry Program : ""https://github.com/foundry-rs/foundry

- Install on Linux
curl -L https://foundry.paradigm.xyz | bash;
foundryup

- Install on Windows
open bash
cd C:\Users\carlo
delete foundry directory 
rm -r foundry

git clone https://github.com/foundry-rs/foundry
cd foundry
# install cast + forge
cargo install --path ./cli --bins --locked --force
# install anvil
cargo install --path ./anvil --locked --force
#==================================================================

Foundry Basic initalization
cd into project directory

forge init --force
forge install foundry-rs/forge-std
forge install Openzeppelin/openzeppelin-contracts
forge install Rari-Capital/solmate 
==================================================================
Create file remappings.txt on the project´s root directory

forge-std/=lib/forge-std/src/
ds-test/=lib/forge-std/lib/ds-test/src/
openzeppelin-contracts/=lib/openzeppelin-contracts/contracts/
solmate/=lib/solmate/src/
gnosis/=lib/safe-contracts/contracts/
==================================================================

Forge Commands
forge build
forge test
forge test --match-test testExploit --match-contract Unstoppable

Compile & deploy
export RPC_URL=https://rinkeby.arbitrum.io/rpc
export PRIVATE_KEY=0x6b...d36a11d2dc
export name=myNFT
export symbol=MNFT
forge create NFT --rpc-url=$RPC_URL --private-key=$PRIVATE_KEY --constructor-args <name> <symbol> 
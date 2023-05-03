How to launch your own token in 5 steps:

1. Buy atleast 200KB RAM from protonresources.com
2. Download proton.token ABI and WASM (right click -> save link as):

    - ABI: https://github.com/ProtonProtocol/proton.token/raw/main/contracts/proton.token/proton.token.abi
    - WASM: https://github.com/ProtonProtocol/proton.token/raw/main/contracts/proton.token/proton.token.wasm

4. Log in at https://proton.bloks.io/wallet/utilities/upload-contract and upload the WASM and ABI

    - For the next few steps, replace tokentester in all URLs and parameters with your own account name

4. Go to https://proton.bloks.io/account/tokentester?loadContract=true&tab=Actions&account=tokentester&scope=tokentester&limit=100&action=create

    - issuer: is "tokentester"
    - maximum_supply: is the maximum # that can ever be minted of your token e.g. 1000000.0000 MEME, notice the .0000 means a precision of 4 decimals

5. Go to https://proton.bloks.io/account/tokentester?loadContract=true&tab=Actions&account=tokentester&scope=tokentester&limit=100&action=issue

    - to: is "tokentester"
    - quantity: is how much you want to issue right now, e.g. "4.0000 MEME"
    - memo: you can leave empty

Then the token should appear in your wallet 🙂

If you would like to upload a logo to Proton Wallet, do the following:

Go to https://proton.bloks.io/account/token.proton?loadContract=true&tab=Actions&account=token.proton&scope=token.proton&limit=100&action=reg

   - tcontract: account name e.g. "tokentester"
   - tname: name of token e.g. "Meme Token"
   - url: url of token e.g. "https://meme.com"
   - desc: description of token e.g. "The Memest of them All"
   - iconurl: token image url e.g. "https://meme.com/token.png"
   - symbol: symbol of token e.g. "4,MEME", 4 is the precision of the MEME token from earlier (remember .0000)


**Important**
It is good practice for token contracts to null out their keys by setting both owner and active keys to eosio@active to prevent further changes to the token contract. This will be required if you want your token to be used directly for buying and selling tokens through NFT marketplace.
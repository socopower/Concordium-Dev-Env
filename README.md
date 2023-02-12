# Concordium-Dev-Env
Setup Development Environment as part of my participation in the Concordium Hackathon carried out through Gitcoin

# Install Rust
In my case I already had Rust on my system, but by going to [Here](https://rustup.rs/). and following their instructions you can install it if you don't have it... I recommend installing the default installation.

To verify that everything installed correctly, you can run: "rustc --version" in your terminal and you should see something like this:

![Captura desde 2023-02-12 03-26-26](https://user-images.githubusercontent.com/41242212/218298504-f0c6480c-75b1-4bd1-964b-bc40d9457332.png)

After verifying that we have Rust installed, we execute the following command in tarminal to install Wasm: "rustup target add wasm32-unknown-unknown"

# Install Cargo-concordium

Now we need to install the Concordium software package, for that, go to: [HERE!!!](https://developer.concordium.software/en/mainnet/net/installation/downloads-testnet.html#cargo-concordium-testnet)

and download it and then, rename the cargo-congordium-v.x.x file to cargo-concordium.

Now we need to run the following command in the directory we have chosen to save it: "sudo chmod +x cargo-concordium"

The next step is add cargo-concordium to our Path, for this the easiest way is to simply move it to the folder ~/.cargo/bin

If you did everything successfully, run: "cargo concordium --help" and you will see something like this: 

![Captura desde 2023-02-12 03-35-12](https://user-images.githubusercontent.com/41242212/218298871-1cc2dfab-1ee1-426a-a468-334e56412fbf.png)

# Install Concordium-client

Go to [HERE!](https://developer.concordium.software/en/mainnet/net/installation/downloads-testnet.html#concordium-node-and-client-download-testnet) and download the client, after downloading the client navigate to the directory you chose and change the package to concordium-client in case it has some version annotation.

then we need to add the package to the PATH, for this I recommend doing the same procedure described in the previous step.

After we have our client in the PATH, we open a terminal in that directory and execute the following commands:

chmod +x concordium-client

concordium-client --help

And if everything is in order, we will see the following:

![Captura desde 2023-02-12 03-46-00](https://user-images.githubusercontent.com/41242212/218299220-37f9e633-6d1a-406c-9332-3175892de76a.png)

# Install Concordium Web Wallet

For this, we need to download and install its [Google Extension](https://chrome.google.com/webstore/detail/concordium-wallet/mnnkpffndmickbiakofclnpoiajlegmg?hl=en-US)

Then, I recommend [this tutorial](https://developer.concordium.software/en/mainnet/net/browser-wallet/setup-browser-wallet.html#setup-bw) to create the account. 

Once the account is established, we need some CCF to pay the Txs, for this, inside the wallet we have a faucet

![Captura desde 2023-02-12 03-58-20](https://user-images.githubusercontent.com/41242212/218299644-2f39a181-449f-4734-8bd0-2956ff6de159.png)

We click the middle button and ask for the tokens.

![Captura desde 2023-02-12 03-59-11](https://user-images.githubusercontent.com/41242212/218299696-f212bd64-694c-429a-b306-fb278cb3e268.png)

Done, we have our wallet created and with some tokens to pay our Txs.

# Export Testnet Wallet and import it into the Concordium Client.

We go to Account Settings> Export Private Key > We introduce our password and click on Export.

After that, a file <YOUR PUBLIC ADDRESS>.export will be created.

Now, to import that wallet to our client, we need to move the <YOUR PUBLIC ADDRESS>.export file to the folder where the client is, in our case, since we moved the client to the path folder, we need to move the .export file to that folder. Once this is done, we open our terminal and execute:

concordium-client config account import <Wallet.export> --name <Your-Wallet-Name>.json

And we will see something like this:

![Captura desde 2023-02-12 03-24-37](https://user-images.githubusercontent.com/41242212/218300033-ad1b1bae-f359-4fdb-b9da-8f7594de23ba.png)

And voila, by completing this step, we already have our DEV ENV configured!!!

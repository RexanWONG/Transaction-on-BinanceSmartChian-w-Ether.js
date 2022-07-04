//TESTNET
const { ethers } = require("ethers"); 
const bsc_jsonRPC_testnet = "https://bsc-dataseed1.ninicoin.io" // json RPC url
const provider = new ethers.providers.JsonRpcProvider(bsc_jsonRPC_testnet) // provider for signing transaction

 
const senderAccount = '0xA3CC972Bc93bAcA679b5245A9f6BF55a13a06Dd1' 
const receiverAccount = '0x3126081ee598F6658eF6b1aA6A067484759DE4cA'
const privateKey = '17f19ddfd2e41c428a5498f486bb377b42e2dd3b5a5ccff41dc8dfc289dd52f8' //just for test purpose - dont share ur private key out
const wallet = new ethers.Wallet(privateKey, provider); // initiating a wallet using private key and provider

 
     
const main = async () => {

    //show senderAccount balance before transfer
    //show receiverAccount balance before transfer
    const senderBalanceBefore = await provider.getBalance(senderAccount)
    const recieverBalanceBefore = await provider.getBalance(receiverAccount)

    console.log(`\nSender balance before: ${ethers.utils.formatEther(senderBalanceBefore)}`)
    console.log(`reciever balance before: ${ethers.utils.formatEther(recieverBalanceBefore)}\n`)

    //Send TBNB
    const transaction = await wallet.sendTransaction({
        to: receiverAccount, 
        value: ethers.utils.parseEther("0.05")    //amount of TBNB to be transfered
    })
 
    //fetch transaction, wait for transaction to be mined
    await transaction.wait()
    console.log(transaction)  

    //show senderAccount balance after transfer
    //show receiverAccount balance after transfer
    const senderBalanceAfter = await provider.getBalance(senderAccount)
    const recieverBalanceAfter = await provider.getBalance(receiverAccount)

    console.log(`\nSender balance after: ${ethers.utils.formatEther(senderBalanceAfter)}`)
    console.log(`reciever balance after: ${ethers.utils.formatEther(recieverBalanceAfter)}\n`)
}

main()
## Hello Ethernaut(Game 0)

This was the introduction level to the Ethernaut game. It was a guide for playing the ethernaut games

## FallBack(Game 1)

The objective was to claim ownership and drain the smart contract balance to zero. First, I looked for places where I could claim ownership and found the contribute function where if I sent ether to the contract and then attempt to send a low level transaction, I could claim ownership.

So I sent 1 ether to the contract by executing the ``` contribute ``` function by using await ``` contract.contribute({ value: 1 }); ``` which incremented my contribution balance and  potentially updating the owner if my contribution surpassed the current owner's .

Then I used the ``` sendTransaction ``` function 
``` await contract.sendTransaction({ to:"game_address", value: 0, from:"my address" }); ```. This updated the ownership to my address and then I executed ``` await contract.withdraw()``` function to drain the contract balance to zero.

## Fallout(Game 2)

The objective was to claim ownership. This contract has an error in the constructor name( it should be ``` Fallout ``` instead of ``` Fal1out ```). So it can be treated as an ordinary function. I called the ```await contract.Fal1out({value:1}) ``` function which had an initialization for setting the contract owner to ```msg.sender``` which helped me claim ownership.
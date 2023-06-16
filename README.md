# wallet
from brownie import *

# Connect to the Ethereum network
network.connect('mainnet')

# List of addresses and the amounts of Ether to collect
addresses_and_amounts = [
    ('0x123...', 1.5),
    ('0x456...', 2.0),
    ('0x789...', 3.0)
]

# The address where the Ether will be collected
collecting_address = accounts[0]

# Collect the Ether from the specified addresses
for address, amount in addresses_and_amounts:
    tx = web3.eth.sendTransaction({'to': collecting_address, 'from': address, 'value': web3.toWei(amount, 'ether')})
    print(f"Sent {amount} Ether from {address} to {collecting_address}")
    print(f"Transaction Hash: {tx.transactionHash.hex()}")

###

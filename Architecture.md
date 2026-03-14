**Project Architecture**



VaultFi follows a simple layered architecture: 



**User Layer**



Users interact through Ethereum wallets (MetaMask).



**Token Layer**



VaultFi operates on an existing ERC-20 token standard.

A MockERC20 token is used during testing.



**Smart Contract Layer**



The core contract (VaultFi.sol) manages



user deposits



interest calculation



withdrawals



reserve funding



vault liquidity monitoring





**Development Layer**



The project uses standard Ethereum development tools:



Solidity – smart contract language



Hardhat – development framework



Ethers.js – contract interaction



OpenZeppelin Contracts – security libraries



dotenv – environment configuration



Interest Model



VaultFi implements a fixed-rate linear interest model.



Interest is calculated as:



Interest = principal × rateBps × elapsedSeconds / (365 days × 10,000)



Where:



principal = deposited tokens



rateBps = annual interest rate in basis points



10,000 basis points = 100%



This design ensures:



deterministic yield



predictable savings behavior



transparent on-chain calculations


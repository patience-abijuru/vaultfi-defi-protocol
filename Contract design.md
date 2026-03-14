**Smart Contract Functions**

Deposit

deposit(uint256 amount)



Process:



User approves token transfer.



User deposits ERC-20 tokens.



Vault records principal and timestamp.



Deposited(address user, uint256 amount)



**Withdraw**

withdraw()



Process:



Contract calculates earned interest.



Total payout = principal + interest.



Vault transfers tokens back to user.



Security:



Protected with ReentrancyGuard



**Earned Interest**



earned(address user)

Returns accrued interest for a user without modifying state.

Useful for front-end dashboards.



**Reserve Funding**

fundReserves(uint256 amount)

**Because VaultFi offers fixed yield, the contract owner must provide interest reserves.**



**Withdrawals are allowed only if:**



**vaultBalance >= principal + interest**



**If reserves are insufficient, the transaction reverts**



**Security Considerations**



VaultFi incorporates several basic smart contract security practices:



ReentrancyGuard to prevent reentrancy attacks



SafeERC20 for secure token transfers



Input validation (non-zero deposits)



Balance checks before withdrawals



State reset before token transfers



Minimal administrative permissions










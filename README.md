
# Goat Trading contest details

- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)

# Q&A

### Q: On what chains are the smart contracts going to be deployed?
Initially Base, Ethereum, Arbitrum, BSC. Blast and other EVM-compatible chains are planned but will need some changes.
___

### Q: Which ERC20 tokens do you expect will interact with the smart contracts? 
Any ERC20 tokens should be able to be used. We are not concerned with problems brought about by token blocklists.
___

### Q: Which ERC721 tokens do you expect will interact with the smart contracts? 
Not ERC721 tokens will interact with the contracts.
___

### Q: Do you plan to support ERC1155?
No.
___

### Q: Which ERC777 tokens do you expect will interact with the smart contracts? 
None.
___

### Q: Are there any FEE-ON-TRANSFER tokens interacting with the smart contracts?

Yes.
___

### Q: Are there any REBASING tokens interacting with the smart contracts?

No.
___

### Q: Are the admins of the protocols your contracts integrate with (if any) TRUSTED or RESTRICTED?
TRUSTED
___

### Q: Is the admin/owner of the protocol/contracts TRUSTED or RESTRICTED?
TRUSTED
___

### Q: Are there any additional protocol roles? If yes, please explain in detail:
There's a treasury that receives protocol fees both for token buybacks and for developers. This system is left manual for now (will start as an EOA/multisig) and the owner is trusted.
___

### Q: Is the code/contract expected to comply with any EIPs? Are there specific assumptions around adhering to those EIPs that Watsons should be aware of?
No.
___

### Q: Please list any known issues/acceptable risks that should not result in a valid finding.
1. Contracts are not set-up for Blast network or zkSync.
2. Temporary LP DOS by minting/burning tokens to an LP. We've added protection to make this less effective if it's a small amount, but otherwise accept that it can be done. If it can be made permanent, cost effective, and can't be defended against with a private RPC then that would be a legitimate bug.
3. Blocklist token problems are understood and not a concern.
4. Tx failures and griefing resulting from MEV protection are known and accepted.
5. DOS during bootstrapping by sending 1 wei of token directly to the pair right before a user attempts to sell their whole token balance.
___

### Q: Please provide links to previous audits (if any).
2 solo audits are still finalizing so no links are available for those yet.

Our other audit is available here https://github.com/inedibleX/goat-trading/blob/main/audits/OxAnmol%20Goat%20Trading%20Audit%20Report.pdf
___

### Q: Are there any off-chain mechanisms or off-chain procedures for the protocol (keeper bots, input validation expectations, etc)?
No.
___

### Q: In case of external protocol integrations, are the risks of external contracts pausing or executing an emergency withdrawal acceptable? If not, Watsons will submit issues related to these situations that can harm your protocol's functionality.
Yes, these are acceptable risks.
___

### Q: Do you expect to use any of the following tokens with non-standard behaviour with the smart contracts?
Besides what was mentioned above (not concerned about blocklists, will use fee-on-transfer, not rebasing, etc.) we don't expect more, but would appreciate feedback if there are important ones that could cause big problems.
___

### Q: Add links to relevant protocol resources
https://goattrading.gitbook.io/goat
___



# Audit scope


[goat-trading @ 4f37c8edf9715c719143a70cc4f63fb92cb2abba](https://github.com/inedibleX/goat-trading/tree/4f37c8edf9715c719143a70cc4f63fb92cb2abba)
- [goat-trading/contracts/exchange/GoatV1ERC20.sol](goat-trading/contracts/exchange/GoatV1ERC20.sol)
- [goat-trading/contracts/exchange/GoatV1Factory.sol](goat-trading/contracts/exchange/GoatV1Factory.sol)
- [goat-trading/contracts/exchange/GoatV1Pair.sol](goat-trading/contracts/exchange/GoatV1Pair.sol)
- [goat-trading/contracts/library/GoatLibrary.sol](goat-trading/contracts/library/GoatLibrary.sol)
- [goat-trading/contracts/library/GoatTypes.sol](goat-trading/contracts/library/GoatTypes.sol)
- [goat-trading/contracts/periphery/GoatRouterV1.sol](goat-trading/contracts/periphery/GoatRouterV1.sol)


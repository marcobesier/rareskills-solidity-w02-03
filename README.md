# On Solidity Events
**Task description:** Revisit the [solidity events tutorial](https://www.rareskills.io/post/ethereum-events). How can OpenSea quickly determine which NFTs an address owns if most NFTs don’t use ERC721 enumerable? Explain how you would accomplish this if you were creating an NFT marketplace.

**Solution:** Most likely, OpenSea maintains their own indexing service by scanning the blockchain (and its entire history) for `Transfer` events of ERC721-compliant token contracts. Under the assumption that the events indeed emit the correct information (which is a reasonable one for the vast majority of contracts), they can thereby determine which NFTs are owned by a specific address.

If _I_ would create an NFT marketplace, I would use the ethers library in combination with a database such as MongoDB to accomplish this task. 

# CrossChainNFT
Cross Chain NFT
Cross Chain NFT
NFT(Non-Fungible Token) is a unique non-interchangeable unit of data stored on Ethereum blockchain, power by smart contracts. we know CryptoPunks and CryptoKitties as first NFT projects and after that a standard introduced as ERC721 for all NFTs living on EVM. after Ethereum, other smart chains as Binance smart, Ethereum layer2 (polygon), etc, used ERC721 as a standard manner to build their internal blockchain NFTs. now, there is a lot of markets in which you can sell your NFT or buy your desired one.

The interface of ERC721 standard includes 9 functions and 3 events you can you can use to interact the NFTs.

FUNCTIONS

balanceOf(owner)
ownerOf(tokenId)
safeTransferFrom(from, to, tokenId)
transferFrom(from, to, tokenId)
approve(to, tokenId)
getApproved(tokenId)
setApprovalForAll(operator, _approved)
isApprovedForAll(owner, operator)
safeTransferFrom(from, to, tokenId, data)
EVENTS

Transfer(from, to, tokenId)
Approval(owner, approved, tokenId)
ApprovalForAll(owner, operator, approved)
You can call transferFrom or safeTransferFrom to transfer your NFT from your wallet address to any other EOA(Externally Owned Account) or Smart Contract Address on the current Blockchain. or you can approve a market place to sell your NFT at any price you want.

But, what if you want to transfer your NFT living on Ethereum to another smart chain like Binance smart or Polygon ?

we can do it for you.

Cross Chain NFT transfers your NFTs from a bockchain to another

how does it work?

there is a crosschain smart contract live on ethereum, binance smart and polygon. you can approve CrossChainNFT on a blockchain like ethereum and then request to transfere your NFT to another one like polygon.

CrossChainNFT is also an ERC721 standardized smart contract but also its interface has 2 functions and 2 events more.

FUNCTIONS

transferCrossChainRequest(contAddr, tokenId, from, to, targetChainId )
wReturnCrossChainRequest(wTokenId, to)
EVENTS

RelayerCallSafeMintWrappedToken(targetChainId, to, chainId, contAddr, tokenId, uri)
RelayerCallRedeem(chainId, contAddr, tokenId, to)
To request a crosschain transfer you should call `transferCrossChainRequest` in CrossChainNFT on Ethereum. CrossChainNFT will transfer your NFT from your address to its address and hold it. this transaction will emit an event on Ethereum and advice offchain relayer to mint a wrapped token coresponding to your NFT on polygon and transfer it to the address you requested. so the relayer will call a function of the CrossChainNFT on polygon and your wNFT will be born there.

wNFT has the same tokenURI as your NFT on Ethereum. you can hold it in your wallet or transfer it to any one else or even sell it on a market place.

whenever you want, you can get back the wNFT on polygon and receive the NFT on Ethereum. it will be happen just like previous step by an event and the relayer. and if the wNFT is owned by an other address, the new owner can transfer it back to Ethereum.

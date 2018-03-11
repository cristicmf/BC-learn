## 区块链资料汇总

### 相关概念
- [术语表](https://github.com/ethereum/wiki/blob/master/%5B%E4%B8%AD%E6%96%87%5D-%E4%BB%A5%E5%A4%AA%E5%9D%8A%E6%9C%AF%E8%AF%AD%E8%A1%A8.md) 

### books
- [精通比特币](https://github.com/bitcoinbook/bitcoinbook)
- [Bitcoin and Cryptocurrency Technologies](https://lopp.net/pdf/princeton_bitcoin_book.pdf)

### 动手搭建一个区块链
- [fisco-bcos](https://github.com/FISCO-BCOS)

### Paper
- [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)
- [ethereum-White-Paper](https://github.com/ethereum/wiki/wiki/White-Paper)

### 学习智能合约
- [智能合约入门](https://github.com/cristicmf/bcos-qucik-start-demo)
- [solidity语法](https://solidity.readthedocs.io/en/v0.4.20/)
- [smart-contract-best-practices](https://github.com/ConsenSys/smart-contract-best-practices)
- [智能合约架构](https://github.com/FISCO-BCOS/Wiki/tree/master/%E6%B5%85%E8%B0%88%E4%BB%A5%E5%A4%AA%E5%9D%8A%E6%99%BA%E8%83%BD%E5%90%88%E7%BA%A6%E7%9A%84%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B8%8E%E5%8D%87%E7%BA%A7%E6%96%B9%E6%B3%95%EF%BB%BF)

#### 智能合约开发工具
- [在线remix](https://remix.ethereum.org/#optimize=false&version=soljson-v0.4.21+commit.dfe3193c.js)
- vscode+solidity

#### 框架
- [truffle](https://github.com/trufflesuite/truffle)
- [zeppelin-solidity](https://github.com/OpenZeppelin/zeppelin-solidity)

---
### 智能合约实践
#### 使用模拟器开发智能合约
##### 1. 开发的客户端 
1. 测试开发：[EtherumJS TestRPC](https://github.com/trufflesuite/ganache-cli)
2. 正式开发[geth](https://github.com/ethereum/go-ethereum)

  - 在自己的私有链条上创建用户
    ```
    geth  --identity "newEth" --rpc --rpcaddr "0.0.0.0" --rpccorsdomain "*" --datadir "cdata"  --port 30303 --rpcapi "personal,db,eth,net,web3" --networkid 999  --rpcport 8549  --targetgaslimit 4712388 console
    ```
  - 创建账号和解锁账号
    ```
    > eth.accounts
    > personal.newAccount("123456")
    > personal.unlockAccount(eth.accounts[0], "123456", 20*(60*1000))
    ```

#### 2. 使用truffle开发框架 
##### 1. [框架一遍truffle API](http://truffleframework.com/)
- 实践MetaCoin,具体的步骤参考官网
```
mkdir MetaCoin
cd MetaCoin
truffle unbox metacoin
```

##### 2. 智能合约交互
[重点理解合约交互](http://truffleframework.com/docs/getting_started/contracts)
##### [solidity API](https://solidity.readthedocs.io/en/v0.4.20/)
##### 3.相关规范 
- [使用包管理](http://truffleframework.com/docs/getting_started/packages-npm)

#### 3.FAQ

###### 3.1. 版本
```
Error encountered, bailing. Network state unknown. Review successful transactions manually.
Error: exceeds block gas limit
```
可能是版本不对

###### 3.2.没有account
```
Error: Expected parameter 'from' not passed to function.
```
there is no account

###### 3.3. 解锁用户
```
Error encountered, bailing. Network state unknown. Review successful transactions manually.
Error: authentication needed: password or unlock
```

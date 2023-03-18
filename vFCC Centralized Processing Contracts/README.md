这个智能合约是一个基于以太坊的智能合约，使用 Solidity 语言编写。该合约可以被用来存储代币，并且记录用户的存款历史记录。

### 该智能合约包含以下函数：

deposit：该函数用于让用户向合约地址存入代币。函数需要两个参数：存款金额和存款 nonce。在调用此函数之前，用户必须先授权代币合约可以转移该用户的代币。调用成功后，存款金额将被记录在用户的存款历史记录中。

transfer：该函数用于允许管理员向其他地址转移代币。该函数需要三个参数：接收地址、转移金额和转移 nonce。只有管理员才能调用此函数。调用成功后，转移金额将从合约地址转移到接收地址，并且转移金额将被记录在合约地址的转移历史记录中。

### 该智能合约还包括以下变量：

freechatCoin：表示该合约将用于存储的代币。

admin：表示合约的管理员地址。

Record：结构体，用于记录用户存款历史记录。其中包含了存款金额、存款 nonce 和转移 nonce。

records：用于记录用户的存款历史记录。该记录是一个映射表，其中 key 是用户的地址，value 是该用户的存款历史记录。

### 该智能合约还增加了以下功能：

允许 0x403dD792F7d10e6Ffb7339F383a3Bf862c84c80f 地址调用合约进行转账。

避免了双花攻击，通过记录存款 nonce 和转移 nonce 来保证了转移的安全性。
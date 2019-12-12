## 概述

本节来把一个典型的 Web2.0 应用升级到 Web3.0 ，看看怎么把这个应用变得”去信任“（ trust-less ）和”去中心化“ （ Decentralization ），来体会一下”可信互联网“思路下的做事方式。

## 要被升级的 Web2.0 应用

先来介绍一下要升级的一个我们自己设想出来的应用，名叫合同网，是一个网站。合同网是一个可以让双方安全的签署一份合同的平台。用户可以起草合约，自己签署之后，发给对方用户，签署，这样合约就生效了。

首先介绍一下这个应用的用户 ID 系统，这是一个典型的 Web2.0 的思路。如果我想使用合同网，首先要填写用户名 ID 和密码这些注册信息，信息保存到合同网的服务器上，以后我就可以用这个 ID 登录并使用合同网了。

签署一份合同的过程是这样。首先由用户一方书写合同，保存到数据库，然后双方用户签字。签字过程就是在这个合同所在的数据库条目中保存双方的 ID 。

安全性是通过信任来保证的。首先，合同相关方面要相信合同网的员工不会去数据库中篡改合同。另外，合同网本身可以通过申请政府拍照，来增加自身可信度。这样，合同网可以受到政府的监督，一旦有违规就会留下永久性的不良记录。另外，合同内容如果不想泄露，那么网站通信过程是需要使用的 HTTPS ，关于 HTTPS 本书后续会有详细的介绍，这里不展开，总之 HTTPS 是需要证书保证安全的，而证书是发证机构颁发的，所以 HTTPS 的安全本身也依赖于对一个机构的信任。

这就是合同网的基本情况了，是非常典型的 Web2.0 思路，目前大多数网站的总体架构都是采用了这个思路。

## 需要升级的点

”可信“的意思是互联网“自带信任”（ built-in trust ），所以可以让之上的 App “去除对信任的依赖”（ trust-less ）。来看看在 Web3.0 思路下，应用如何工作。

基于合同网数据库的 ID 系统，本身就是中心化的和基于信任的。Web3.0 最大的一个特点，就是用户的 ID 是不受任何人控制的。基本思路是这样，用户生成一个足够长的随机数，足够长保证了以后任何人在生成的时候，是不可能跟这个数相等的。这样，这样的随机数就是一个 ID 标识符了。相当于用户名密码条件下的用户名，用来定位这个用户。另外需要的是一个公钥，跟这个 ID 标识符绑定在一起。这样就可以用私钥来证明自己是这个 ID 标识符的拥有者了。绑定的媒介需要满足这几个特性：不被任何私有机构控制，透明和不可篡改。显然区块链就符合这个要求。这个思路已经被标准化了，参考 W3C 的 DID 规范[1]。对于 DID 本书后续会有专门章节讲解。目前只要知道，我们拥有了一个不被任何人把持的身份，可以通过私钥来证明我们是这个身份的主人。所以 Web3.0 思路下，每一个用户，就是一个 DID 。Web3.0 的基本思路是，所有的数据都是用户自己存储。应用跟数据是分离的，合同网作为一个网站，是没有自己的数据库的，因为所有数据都保存到用户自己的存储区域。既然没有数据库，不能记录用户的账户信息以及对应权限，所以也不需要登录。

比如现在要签署合同的双方是小明和小刚，合同先要由小明起草。小明打开合同网，就可以直接在上面按照指引来编辑合同了，合同网会按照小明的要求，把合同保存到小明指定的存储区域，一般是小明自己的私人云存储，然后用自己的私钥签署合同。同时，小明需要知道小刚的 DID ，这样小明就可以通过小刚的公钥把合同和自己的签名加密后发送给小刚，这样小刚就可以签名，然后发送给小明。这样整个过程下来，双方都把合同和双方的数字签名保存到了自己的私人区域。

合同的安全性是不需要基于对网站的信任的。因为合同以及签名都永久的保存到了双方手里，未来即使没有了合同网，合同依然有效。如果需要更高级别的信任，可以把合同和双方签名的哈希，存储到区块链上。

需要注意的一个问题，数字签名保证了合同是某个 DID 签署的。但是 DID 并不绑定小明这个人。Web3.0 下的思潮是数字空间的独立，DID 本身就绑定了数字资产和声誉等资源，所以 DID 本身就可以对违约责任负责。当然，如果合同客观上需要 DID 和小明这个人绑定，也可以采取其他的方式，例如把小明的 DNA 等一些生物信息上链，跟 DID 绑定。

另外，双方进行加密通信的时候，是不需要需要证书的，因为 DID 本身就类似一个通过区块链颁发的证书，上面绑定了发信人的名字，这里就是 DID 的标识和公钥。合同网的网址也可以注册在基于区块链的去中心化的 DNS 上。关于去中心化的证书和 DNS ，后面也会有专门的章节展开。

这就是 Web3.0 版本的合同网的原理了。

## 优劣对比

最后一部分，咱们详细分析一下，Web3.0 版本的合同网都有哪些优势。

首先是应用定位更明确了，只是工具，不提供信任（ Trust-less ）。去中心化的合同网变得只是一个工具了，它的作用是辅助用户完成任务，例如编辑合同，让用户容易找到对方的 DID ，让加密通信过程变得自动化。但是注意，没有这个工具，或者换一个工具，用户一样可以完成工作，数据和应用是分离的，用户有切换的自由。而中心化条件下，用户对合同网是有严重依赖的，应用不但是工具，也提供信任。

第二点是采用了去中心化的 ID ，用户获得了自己的数据的自主权。首先这个 ID 是可以在多个网站上使用的，另外，合同和签名数据是跟这个 ID 绑定的，不会被合同网控制。签署过程是通过私钥产生的数字签名，数字签名之所以可信，是数学上保证的，是无需信任的，可验证的。

第三点是安全性更高了。去中心化条件下，数据都存储到用户本地，即使”合同网“倒闭，合同依然有效。而中心化条件下，数据都存储在合同网的服务器上，黑客只需要拿下一台服务器，就能对所有的合同造成破坏。

证书不需要人为审核了，无需肉身到场，自动化的空间很大。

## 结论

来总结一下。去中心化的合同网是不提供信任的，这样带来的好处很多，例如不用自建数据库，为用户的合同丢失负责，但是问题是原本由合同网或者政府背书的数字证书提供的信任，现在是谁提供的呢？我们可能会觉得是数字签名提供的，因为数字签名是数学上可以验证的，但是其实数字签名本身是不提供最终的信任的，这就是为何 Web2.0 条件下的数字签名过程还是要依赖于证书的，而 Web3.0 条件下，区块链发挥了信任之根的作用。对应合同网的情况，因为 ID 标识和公钥是写到了区块链这个公共的，不能篡改的存储媒介上，才发挥出了类似于传统数字证书的作用，保证了数字签名的最终安全性。所以有人说区块链是 Web3.0 的基石，这个是有道理的。

参考：

- [1] https://www.w3.org/TR/did-core/
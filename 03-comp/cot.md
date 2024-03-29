有一种信任模型叫做信任链（ Chain Of Trust ）我们书中会提到跟它相关的一些术语，例如信任之根，根证书等等。所以这节来看看这些术语都是什么意思。

## Chain Of Trust 信任链

不管是在日常生活中还是在计算机网络条件下，信任往往都是分层的，通常我们看到的信任，仔细想想都是基于一个多层信任形成的链条，这就是本书中所说的信任链。

以日常生活为例。我相信门可以保护我，因为我相信锁，而锁值得相信来自于对钥匙的信任。门，锁，钥匙，就形成一条链。又比如我去一个超市门店买东西，之所以相信门店，是因为信任这个门店背后的公司，而之所以相信这个公司不会欺骗，是因为相信法院会在我的权益受到侵害的时候介入。门店，公司，法院又形成一个信任的链条。

这种分层的链式信任结构的好处是让“信任”这种珍贵的资源可以被放大。我们知道法院要比一家小小的门店可信，但是如果买个东西这样的小事，都需要去法院去登记一下，那么法院就会忙不过来，要知道更高可信度来自更高的安全保证，而更高的安全性保证是有很高成本的。而通过链式结构，把法院的信任传递给门店，是一种非常聪明的做法。

## Root Of Trust 信任之根

信任链是否安全，很大程度上取决与最终极的那个可信任的实体是不是足够值得信任，而这个实体就被称为“信任之根”，也有的资料上成为”信任锚“。

信任之根的是信任的起点，特点是它的信任不依赖任何东西，而是无条件的信任。或者说是自己要保证自己的可信。上面的门的例子中，钥匙是信任之根，如果钥匙被人拷贝了，这个门不管怎么加固也不安全了。在门店的例子中，法院是信任之根，门店出现欺诈可以打电话给公司投诉，公司不行，还可以告到法院，但是法院如果还是不可信，那么就再也没有上一级的可信机构了，所以法院是这条链的信任之根。

## 什么可以作为信任之根？

那计算机语境下，什么适合用来做信任之根呢？肯定都是安全度相对较高的东西。

首先可以把硬件作为软件系统的信任之根。软件系统最怕的是软件被黑客篡改。所以可以让系统的启动加载程序 bootloader 去检查上层软件是否被篡改过。但是 bootloader 本身也是软件，也有被篡改的可能，所以可以在硬件层面上去保证 bootloader 没有被篡改过。可以在系统加电后首先执行一个硬件电路，检查 bootloader 是否被篡改。这里，硬件被认为是安全度更高的存在，因为黑客可以修改软件，但是却很难去修改硬件。

对于计算机通信时候采用的数字证书而言，大组织是信任之根。数字证书一般会采用一个信任链的结构。终端用户的证书，是由中间发证机构（ CA ）来签署的，使用的是中间机构的私钥，而中间机构之所以可信，是因为有更上级的发证机构用自己的私钥来签署一个确认中间机构的证书。最顶端的发证机构会用自己的私钥给自己签署一个证书，这家发证机构就是整个系统的信任之根，而它给自己签发的证书，就叫做“根证书”。

Web2.0 条件下，大部分系统的信任之根都是某个机构的数据库，例如 DNS 的根域名系统基于 ICANN 公司的数据库，网上支付，信任之跟是支付宝的数据库，PKI 系统是基于某个 CA 的数据库。这些数据库都是封闭的，不可验证的。Web3.0 下，我们期待用区块链来做信任之根。

## 结论

信任链是当前我们的肉身世界以及网络世界最主要的信任模型之一。低安全度组织逐级依托高安全度组织来达成可信，分层的信任形成一个信任链条。Web3.0 会以区块链为信任之根，而区块链自身的信任模型却不是 Chain Of Trust ，而是更接近 Web Of Trust ，具体情况后续章节中会展开。

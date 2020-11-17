Web 之父 Tim Berners-Lee 目前的项目 Solid 体现了他本人对下一代互联网的理解。Solid 项目的口号[1]是 

> Re-decentralizing the web 

让 Web 再一次去中心化。从下面的分析中我们也会看到 Tim 的 Web3.0 和本书中的 Web3.0 愿景是高度一致的，但是技术上却有着很多区别。本节通过理解 Solid 项目，分析一下 Tim 的技术路线有哪些不同？本书 Web3.0 思路在这些方面是否具有优势？

## 愿景一致

Solid 和本书的 Web3.0 愿景是完全一致的，都是让用户摆脱大组织的控制，真正拥有自己的数据。

Tim 观察到了当代互联网的过度中心化的问题。他发现 Web 正在被大组织滥用，互联网公司靠占有用户的数据牟利，用户的隐私和数据权益得不到保证。个人不是互联网的主人，而更像是互联网的产品。Web 本来是为个人崛起而生，但是发展到今天，垄断却越来越严重，长尾效应消失。Lee 认为当前 Web 有些基本的设计问题是需要被修复的，他自己给出的答案就是 Solid 项目。2018年 Inrupt 公司成立，专注 Solid 项目的开发。

Solid 是 Social Linked Data 的缩写，只是一套标准，而不是一个具体应用。基于这套标准，任何人都可以构建自己的应用，所以 Solid 代表的也是一个开放的去中心化的系统。根据维基百科上的介绍， Solid 有两个目标：第一，让用户真正拥有自己的数据；第二，更好的保护用户隐私。

通过对 Soild 的简单介绍，可以看到 Solid 和 Web3.0 ，技术路线上也都采用了去中心化，愿景完全相同，都是为了让用户真正持有自己的数据。但是技术细节上差异非常大，我们来分析一下带来的后果。

## 数据存储方式

先来对比一下 Solid 和 Web3.0 保存用户数据方式的异同。

二者的基本思路是一致的，数据都由用户自己存储。Solid 有一个 POD （ personal online data stores ）的概念，我的数据，就存储在我的 POD 中，POD 是一个随时可以访问的数据存储区域，里面的数据要随时允许被授权的应用去调用。Web3.0 思路下，用户的数据是加密后保存到自己的机器或者是云服务上的，默认是不能被应用访问的。用户自己存储数据，意味着 Solid 也遵照”数据和应用分离“的思路，跟 Web3.0 是一致的。

数据存储方式上，Solid 和 Web3.0 区别就比较大了。每个 POD 中的数据，是按照语义网的思路，以 Linked Data 规范来存储。例如，我的 POD 里面有一个图片，你发布了一个对我图片的评论，那么评论和图片之间就会形成连接关系，会按照 Linked Data 特定的规范去注明。例如[4]：

```
<https://mypod.solid/comments/36756>
    <http://www.w3.org/ns/oa#hasTarget>
        <https://yourpod.solid/photos/beach>.
```

加上 Solid 是专门构建社交应用的一套规范，我的直观感觉是 Solid 数据存储数据格式，通用性不是很好，但是也请教了 Solid 中文社区的同学，他们说 Solid 的数据格式也是能适应各种类型的数据的。而 Web3.0 对于数据存储格式没有明确要求，不同行业的数据会按照行业中最流行的协议的标准去存放。例如，社交类的数据会按照一套社交应用协议标准去存放，但是非社交类数据也会有自己的标准格式。对于数据的关系，Web3.0 不仅仅要求注明，而且也要求能证明，或者说能验证，这个在下一部分我们聊信任的时候会深入展开。

总之，我个人认为 Web3.0 的数据存储格式更灵活和普遍适用一些。

## 信任结构

Solid 是为社交场景设计的协议，不能很好的支撑起数字经济的，因为 Solid 不像 Web3.0 这样，有区块链提供的信任基石。

可以这么说，Soild 的思路更倾向于鼓励数据的共享，而 Web3.0 更倾向去数据的确权。Web3.0 是可信互联网，可信的意思是一切都是可以用数学方法验证的。Web2.0 时代，基于平台的应用其实是强大的，因为平台可以提供信任。举个例子来看着意味着什么？你有一张图片发布到了 Twitter 上，我五年前发表了一条评论在下面。那么到了今天，不仅仅是图片和评论的关系大家都可以看到，而且最重要的是如果我说这个评论是我发出的，这个说法是有足够的公信力的。而用 Solid 的思路点对点的存储数据，没有人能确信我是否篡改过数据。你可能会认为，没关系，在图片持有人那里只要保存了这个评论的哈希即可。但是实际上，如果图片持有人想要否认我发过这条评论，他可以自己动手去篡改哈希。所以不管如何，只有两方存在，任何一方说话都说没有公信力的。而平台则扮演了可信的第三方。Web3.0 去掉了平台，融入了区块链，也可以承担起信任之根的角色。Web3.0 的愿景里，也可以有一家公司叫 Twitter ，Twitter 有自己的公钥，是注册在区块链上的，Twitter 会用私钥去签署图片和评论，包括评论的发布时间，这样，五年后我依然可以像大家证明，我发过这条评论。而且这时候的安全性比 Web2.0 更高，即使 Twitter 倒闭，因为区块链上永久记录了 Twitter 的公钥，大家依然可以验证曾经有一家叫 Twitter 的公司签署过评论。可见，Web3.0 的基于区块链的信任，能够让数据的所有权更清晰。用户持有数据，不仅仅代表用户可以完整的保存自己的数据，更应该表示用户可以不依赖于任何人去证明数据的各种属性。因为一旦数据失去了必要的属性，就可能变得毫无价值了。当然，Solid 项目也可以通过 XAdES （ XML Advanced Electronic Signatures ）签名的方式达成类似的做法，所以并不是不能进行确权。

从 ID 系统的构筑，也可以看到 Solid 因为没有区块链而导致的技术上的短板。Solid 的 ID 系统也是去中心化的，是 WebID [2]。WebID 目的也是让用户持有自己的身份，这一点跟 DID 很像，同时，WebID 也是包含公钥的。不同的是，WebID 的信任是基于 Web Of Trust 思想的。用户的 WebID 是自己创建的，存储在自己的服务器上，这就跟我们自己制作一张身份证一样，默认情况下没有信任基础，他人是不会接受的。现实生活中的身份证是基于对中心化组织的信任。数字世界中，有 CA ，也就是发证机构的概念，就是数字世界中提供信任的中心化组织。但是 Web ID 采用了另外一套思路，也就是最早在 PGP 项目中提出的 Web Of Trust 的思路。网络中了解我的人，会直接签署我的 WebID ，表示对我有直接信任，这样我跟我的一些朋友之间又直接的信任链接，我和朋友的朋友之间是间接的信任链接，这样大家就能连成一张”信任之网“，这就是 Web Of Trust ，而这个网上的每个节点，也就是每一个 WebID ，就建立起了去中心化的信任基础。但是 Web Of Trust 这个思路本身是有明显问题的，这就是为何 PGP 虽然提出了 Web Of Trust 思路，但是实际中基本还是采用了基于 CA 的中心化的信任。首先，WebID 的信任是需要人为构建的，如果一个新人进入网络，又没有熟人给他签署信任，那么他的信任该如何构建呢？所以 Web Of Trust 建立的过程是不能自动化的，这个对于构建数字经济是个很大的绊脚石。具体到 WebID ，还有一些明显的技术上的短板，例如一个 WebID 从技术上说就是一个网络资源，例如 https://bblfish.net/#hjs 就是一个 WebID 。可见 WebID 明显依赖于 DNS 和 HTTP 协议。DNS 本身是中心化的系统，Web3.0 会对它进行改革。HTTP 自身是比较适应云计算中心化服务器架构的协议，未来有可能被 IPFS 这样的去中心化协议取代。作为互联网基石的 ID 系统自身基于这些不稳固的基石来构建，显然是不合理的。不过，根据 Solid 中文社区朋友的反馈，Tim Berners-Lee 也正在考虑把 Solid 切换到 DID 了。

总之可以看到，Solid 拿掉了中心提供的信任，但是没有补上区块链提供的信任，带来了很多难以克服的困难。

## 结论

总结起来，Solid 项目的不足恰恰是因为没有强大的信任之根。信任来自可验证，虽然密码学能够提供一定的可验证性，但是一个真正的点对点的系统中，没有第三方，是无法提供最终的信任的。有人说，区块链是一个新的中心和第三方，这个说法不是没有道理。Solid 的目标是实现用户持有数据，但是实际上因为没有信任的支撑，用户只是形式上持有数据，因为个人真正持有数据，不仅仅是形式上的自己存储数据，而是要有能力证明数据的各种属性以及和其他数据的关系，例如一条评论，到底发在了哪里，发布时间是什么，这样才能保证数据的价值，有价值的东西才有确权的必要。Web3.0 可以把数据产权给个人，这个是离不开区块链这个信任之根的。另外，依然是因为 Solid 没有区块链，所以 ID 系统必须采用 Web Of Trust 的思路，通过这个方式提供的信任，是不能自动化的而且对新人也很不友好。
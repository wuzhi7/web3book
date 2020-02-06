# web3book

- 第一章 技术发展的去中心趋势
  - 硬件的去中心化
  - 软件的去中心化
  - 数字世界独立化
- 第二章 为何 Web3.0 是去中心化的？
  - Web 架构的迭代
  - 智能合约全球愿景
  - 数据产权
  - Web 之父的 Web3.0 架构的弱点
  - 要协议不要平台
  - 垄断形成的根源
  - 如何理解隐私？
  - 云计算的去中心化
    
第三章 Web3.0 架构组件
  - 把一个 Web2.0 应用升级到 Web3.0
  - 区块链
  - 去中心化身份
  - 去中心化支付
  - 去中心化的 DNS
    - DNS 的中心化现状
    - 去中心化 DNS 的基本原理
  - 从密码到私钥
    - Web3.0 的基础：人人持有私钥
      - 这个不是技术革命，而是用户个人习惯革命
    - 私钥签名决定一切
      - 区块链上的数字货币，也不过就是一条签名链
      - 签名保证我的确干过某事，我证明其他人的确说过什么话
        - 对自己的淘宝评论签名，也同时签署见证他人的评论
    - 加密通信的基础
      - 配合区块链，实现不依赖于 CA 的加密通信
    - 怕私钥容易丢
      - 用 DID ，绑定多对密钥
  - 去中心化的 CA 和 PKI
    // NOTE: 这个标题过于技术化了，选个亲和的
    - 公钥密码学的局限
    - 数字证书的作用
    - 发证机构 CA 
    - 去中心化 PKI 的实现原理
      - https://github.com/WebOfTrustInfo/rwot1-sf/blob/master/final-documents/dpki.pdf
      - DID 也是一种 PKI https://w3c-ccg.github.io/did-primer/#introduction-0

第四章 区块链--Web3.0 之根
  - 概述
  - 区块链背后的密码学
  - 区块链运行原理
  - 区块链和数据库的区别
  - 区块链为 Web3.0 带来了什么？
  - 女巫攻击

第五章 去中心化身份
  - DID 的技术细节
  - DID 的隐私保护思路
  - VC 可验证声明
  - DID 案例
    - 微软的 Ownyouridentity 项目
    - 比原链的去中心化身份架构
    - 亦来云的去中心化身份架构
    - 波卡的去中心化身份架构
    - 去中心化 ID 基金会

  - 如何证明我评论过你的商品？
    - 给一条评论确权
      - 最简单的方式是数据全部上链，但是没有可操作性
        - 所以可以扩充信任，让区块链仅仅作为信任的根基
      - 淘宝签名
      - 淘宝公钥注册在区块链上
        - 不怕淘宝不承认，不怕淘宝倒闭
        - TTP 可以去掉”信任“，但是第三方真的可以去掉吗？
  - 人性化设计
    - https://tor.us/
    - blockstack 的 ID 命名空间
    - https://sovrin.org/
    - ID As A Service
第六章 去中心化支付
  - 互联网的原生支付层
  - 我如何把数据卖给你？
    - 数据资产通证化
  - 价值捕获问题
    - 有人说区块链之所以会诞生，就是因为程序员很不开心
      - 工作了多年，没有捕获到多少代码带来的财富
      - 程序带来的便利被各行各业捕获，被老板们捕获，大家转到钱之后买房或者租房
        - 价值最终都被房产捕获了
      - 房产能捕获价值
        - 因为人为创造的稀缺性
          - 也可以认为，房地产建设者们越不努力，房子稀缺性就越强
            - 所以房子少，房子破，也一样可以捕获价值
      - Richard Stallman 开发出那么多软件，也没有捕获到什么价值
        - 价值被 Redhat 和各个科技公司捕获了
  - Token 经济
    - 可编程的价值
    - 原生激励
  - 资源定价
    - Hashcash
    - DDos 攻击的防范
  - 比特币
    - 比特币的隐私
    - 硬顶的智慧
    - 基于计算机共识的货币发行
  - 隐私币
    - Grin
    - 门罗币
    - Zcash
  - 稳定币
    - 央行数字货币和人民币的区别
    - 稳定币和法币的区别
    - MakerDAO 和 DAI
    - Defi 去中心化金融
    - USDT 和其他

第七章 去中心化的 DNS 和 PKI
  - NOTE: DNS 和 PKI 在萨博的文章中都被叫做 TTP ，所以本章标题是否可以改为《区块链替代 TTP 》
    - https://nakamotoinstitute.org/trusted-third-parties/
    - 浏览器内置的大 CA 的公钥
      - 这时候浏览器就相当于区块链
      - 是一个去中心化的并且被认为是安全的存储媒介
      - 实际中完全可以把浏览器替换成区块链，把 CA ，替换成任意的具有声誉的 DID 
  - 加密通信原理
    - 公钥和私钥
    - 无秘密加密
    - 数字签名
    - HTTPS 基本原理
    - 混合加密策略
    - 数字证书
    - 发证机构 CA
    - 中间人攻击
    - CA 如何去信任化
    - Web Of Trust
      - https://sovrin.org/
    基于区块链的信任
    案例
    Namecoin 区块链
    IPFS 的去中心化域名服务
    以太坊的去中心化域名服务
    Blockstack 的命名系统
第八章 Web3.0 之上的 App 架构
  - 增加一部分
    - 去中心化电商系统设计
    - 去中心化社交系统设计
    - 去中心化搜索引擎设计
  - DApp 是什么？
    - https://matrix.org/
    - 无平台方的平台
    - 用户自持数据
  - DApp 架构原则
    胖协议
    用户为中心的设计
  - 从 App 到 DApp 
    无大型数据库
    无服务器
    从服务器端代码到智能合约
    去中心化登录认证系统
    可编程代币资产
  - DApp 的分层结构
    - 区块链层
      - 很多 DApp 都会自己就是一个钱包，能够签署交易
    - 存储层
    - 认证层
    - SDK 层
  - DApp 的用户体验优势
    - 退出的自由
    - 定制客户端的自由
  - NOTE: 如果这一章内容太多
    - 可以拆出去一章《不基于信任的数据确权》
      - 确权跟 DID 也是紧密相关的，例如 https://w3c-ccg.github.io/did-primer/ 的 "Selective disclosure." 这部分
      - https://opentimestamps.org/

  - 存储
    - 以 Gaia 为模板讲
      - 方便的完成加密，同步等各种操作
      - 本来“去中心化存储”是一章的内容，
        - 但是 IPFS 是比较独立的系统，有专门的书籍介绍了，本书可以不展开
        - 其他的跟 Web3.0 的主题也没有太直接的关系
  - 如何实现搜索服务？
    - 每个人都存储自己的 Tweet ，那么如何 index 这些数据实现搜索
      - 一种方式是通过一个大型的中心化的服务器，来做搜索服务，不过这里面有中心化的危险
      - 另外一种思路是：每个人只对自己的圈子内的数据感兴趣，所以可以在自己的服务器上来完成 index
   - 加密法院
     - 每个数字世界法人都会充入“信誉准备金”来提高自己的可信度
     - 如果有人提交了此人违约的密码学证据，就可以罚没准备金

第九章 Web3.0 时代的商业模型
  - 比特币模式的商业模式
  - 云服务的去中心化
    - 如何提供 AWS 一样的服务
  - SAAS 模式的去中心化
    - 没有了公司，谁去提供 SAAS 
  - 去中心化经济激励  
    - 商业模型之谈一个字：钱
      - 标准化组织，如何拿到钱，也就是协议开发者如何拿到钱
      - 另外一个就是基于协议开发的应用，如何赚钱？Gmail 采用给用户无限存储空间，获取广告机会
        - https://knightcolumbia.org/content/protocols-not-platforms-a-technological-approach-to-free-speech 的 Business Models 部分
        - https://avc.com/2016/07/the-golden-age-of-open-protocols/

  - 价值捕获
    - 区块链之所以出现，有人说是因为开发者们不开心，因为没有捕获到多少价值
    - Web3.0 要解决价值捕获问题，在协议层面捕获价值：比特币
  - 去中心化的难点
    - 苹果不会允许用户安装任何应用的
    - 真正的去中心化，要求手机的软硬件都是开放自由的
    - 但是 Ubuntu 尝试的失败证明，去中心化条件下做用户体验，是非常难的
    - 但是未来一定是去中心化的世界
  - Web3.0 破局之道
    - 从需要高信用的场景触发
      - 也就是金融领域
        - 区块链上的华尔街：ICO/DEFI
    - 去做一个款去中心化的 IM 直接跟微信竞争，不是好方式
      - 逐步立法，让微信把数据所有权还给用户即可
  - 区块链永动机机制设计
    - 经济模型闭环
    - Blockstack 的经济模型
    - Nervos 的通胀税模型
  - 从信任到验证
  - 去中介化
  - 去中心化的经济学：市场为王
    - 奥派经济学
  - 标准化组织的钱
  - 相信人到相信数学
  - 从监管到验证
  - 信任之根
    - Chain Of Trust
    - 自持数据的权威性
  - 从权威存储到权威签名
  - 时间戳服务器
  - 数据的商业价值
  自处理获取有用结论
  主动发布获取有用服务
  - 售卖特定数据获取收益

  - 零知识证明

第十章 Web3.0 实战 -- Blockstack
  - 创建 Blockstack ID
    - 注册账号
    - 申请 ID
    - 底层原理
      - 给去中心化 ID 一个友好的用户名
    - 单点登录
  - Gaia 数据存储系统
  - React 前端编程框架
    - Hello World
    - 完成登录功能
    - 与 Gaia 交互
  - Clarity 智能合约编程
    为何要图灵不完备
    编写智能合约
    与 React 客户端交互
  - Web3.0 版本的 Twitter
    - https://scuttlebutt.nz/get-started/
    - 数据如何存储
    - 也许更应该做的是微信
    - 朋友关系的建立
    - 实时性
    - 私钥签名授权

第十一章 结语
  - 个人的崛起
    - 个人即机构
    - 机器赋能个人

## 本书主线
- 打破垄断，就要消灭平台公司
  - 消灭平台公司，就要先找到各种技术的去中心化实现
  - 各个关键小节的标题都应该是《 xxx 的去中心化》
    - 例如《云计算的去中心化》
    - 《身份系统的去中心化》，《第三方信任的去中心化》

## Web 和 区块链 的融合

- 用私钥，去加密我们的 Web 数据
  - 并且可以去使用数字资产
- 信息和资产和钱就成为了一类东西
  - 只要你有私钥，这些东西就是你的
    - 注意是直接属于你，而不需要基于第三方
      - 这一点是非常让人激动的

    - 一个人有两百万粉丝，怎么确定不都是机器人呢？刷单造假，有中央权威监督的条件下尚且泛滥，去中心条件下如何避免？
    - 资产是和契约分不开的，有房产证，才能证明这个房子是你的。数字世界中也是一样的到了，书中会提到的可验证证书，就是表明一种授权关系。是数字世界的契约。

  - 技术问题：数据确权不是简单的去中心化能够解决的
    - 一份数据摆在你面前，你怎么能知道数据是谁的呢？没有所有权的东西，怎么可能资产化呢？数据是可以拷贝的，自身是没有稀缺性的，没有稀缺性的东西，谁会去买？

# 协议

互联网的本质是一系列的游戏规则，或者术语叫做协议，W3C https://en.wikipedia.org/wiki/Internet_Engineering_Task_Force 这些协议的制定。

RFC 是允许公开讨论的。

Linux 的网络模块和 Chrome 浏览器是规则的载体。

浏览器直接链接的是 ISP 。

> The terms Internet and World Wide Web are often used interchangeably in everyday speech;

- https://en.wikipedia.org/wiki/Internet

- TCP/IP intro
  - https://www.bilibili.com/video/av5139978?from=search&seid=9702015957132993653

- https://www.youtube.com/watch?v=gkJqMSbI1IA&feature=em-lsp
  - 假名经济
    - 不是真实姓名，但是也是你的长期代号
    - Twitter 上很多人都是用假名，但是这些假名也可以用来构建声誉和信用
    - 中本聪也是个假名

## 写作规范

- 标题要瞄准问题，而不是瞄准技术，用白话，而不是术语
  - 包括文章，部分，段中心，都要清楚，具体，生动，通俗，让书的目录本身就非常亲和友好
  - 好例子《如何证明你是你》 ，坏例子《DID 技术》，太专业
  - 好例子《 Web3.0 要解决什么问题？》，坏例子《一个目标两种技术》，太抽象
  - 好例子《密码学会带给 Web3.0 什么？》，坏例子《区块链背后的密码学》，太宏观
  - 好例子《去掉 Web 自身的中间人》，坏例子《 DNS 和 PKI 的去中心化》，太术语
- 每个小节分三部分
  - 写3000字
  - 开头一段是一个问题，最后一段是对这个问题的答案
    - 中间各个部分是对这个问题的展开回答
- 格式审查要求
  - 不允许有链接，因为小学课本上出现过链接变成黄色网站的情况。
- 选材标准
  - 很多人文政治理念或者故事，都要一笔带过
    - 自由主义
    - 密码朋克运动
    - 数字空间独立思想
    - 如果一个小节的内容，不能画出框图，或者时序图，基本上可以认为这一节不是技术内容
      - 不是技术内容的，不能单独做为一个小节出现
    - 但是《碳基硅基世界解耦》这样的话题，还是非常技术性的，可以写
  - 不要讨论太多超前的区块链技术
    - 多聊清楚 Web2.0 的架构，这样大家才清楚要升级的是哪些组件
    - 区块链的颠覆性体现在哪里
      - POS 还是 POW
      - 公共数据库
- 章节格式
  - 按照《图解密码学》就可以
  - 每章多个小节，小节标题是 11.1， 11.2 这样，除了每章第一小节《概述》之外，其他的每个小节都对应我的一篇 binfo 文章。每个文章的每部分对应 11.1.1 11.1.2 这样的标题，每篇3000字左右，这样全书100节，正好是30万字
    - 每个小节一定要对应一篇文章，保证立意鲜明，言之有物
- 引用格式
  - 暂时参考：https://courses.csail.mit.edu/6.857/2014/files/19-fromknecht-velicann-yakoubov-certcoin.pdf
  - 使用 [1] [2] 这样的序号

- Web3 项目案例
  - https://safenetwork.tech/
  - https://forum.holochain.org/
  - lbry video
- 写作心法
  - 最近发现经常完不成每天3000字的任务
  - 基本上是因为话题太大，拿不下来
  - 所以指定一个四小时截止原则
    - 意思是只给四个小时看材料的时间
    - 所以必须保证这个点足够简单，不然四个小时肯定看不懂
    - 另外再抽出四个小时写作，这样一天8小时，时间能保证，估计文章也就出来了

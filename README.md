# P2P Online Judge

这是一个新开的脑洞，希望大家一起来完善然后有时间开坑。

这个OJ完全去中心化，测试数据、题目、评测记录保留到所有节点间。当然使用这个OJ不是无条件的，你需要做出贡献才可以往上面交题、传题。

做出贡献的方法有两种，提供评测和保有数据。首先你可以设定一个P2POJ可以在你磁盘上占有的配额，然后软件就会自动分配一些测试数据让你保有，一般会采用对于自己的客户端赚贡献最有利的策略。（也就是下载那些评测资源不饱和的数据。）

然后你就可以帮忙评测，机器之间常数的不同我们会先跑个分，然后根据这个跑分换算常数。（当然奇怪的指令集也会通过编译器选项禁用。）帮忙评测会获得一些的贡献点，发放的多少取决于当前网络的压力。

你也可以单纯帮忙保有数据，供其他节点下载。此时其他同样保有该数据的节点为了验证你确实拥有这个数据，一段时间会向你发出一次challenge，内容是要求你响应这题测试数据中随机的一个4k对齐的块，加上challenge发起者ID、目标机器ID、和一个随机字符串的sha1 hash。成功完成这个challenge即可获得保有贡献。当然你也可以选择不接受一些challenge（当然你就不会有来自这个的贡献），假如你的硬盘是上古机械硬盘或者说想丢S3之类的估计会好不少。这时候评测假如遇到无数据也可以按照下面的造假处理。

提交程序到这个网络评测所需要消费的贡献取决于该题的时限和内存限制，如果是传题则需要消费更多，并且也跟测试数据大小有关。评测记录会被下发到很多个节点，所以一个节点的错误或者作弊不会影响到大部分的结果。然后如果三次都是错误的结果就会被拉黑。

整个系统感觉可以基于bitcoin的代码建立，不过如果有类似的python轮子就更好了。

摘要：
     web应用架构反应了定义模块或组件以及它们之间的交互。它是事物一定程度上的抽象。它将一个软件系统分为几个模块以及模块之间的相互协作。本文通过分析WebQQ的构架模式，从整体上把握webQQ实现原理。通过webQQ具体应用，体会架构在编程过程的重要性。
引言：
     首先将webQQ整体分为各个组件模块，定义模块之间的交互。然后根据实际情况将各个组件分为3类，控制器，视图和模块。这便基本完成了MVC架构模式的构建。接下来便根据该mvc图完成其架构图的设计。这个主要是对于底层的设计，体现数据为中心的过程，旨在提供一个快速的查找过程。
项目主要技术依据：
     采用目前较为成熟的架构模式为MVC，这也是目前应用最为广泛的架构模式。控制器（Controler）控制器接受用户的输入并调用模型和视图去完成用户的需求 。视图（View）用户看到并与之交互的界面 模型（Model）企业数据和业务规则 
![alt next](http://b227.photo.store.qq.com/psb?/V10ymuAs4OUe9j/eu2KZjMr0XFIte3QIxu.dpLSl162NaTgu3aYi0JpJqg!/b/dGW2XIfQJwAA&bo=QgGYAAAAAAADAP4!)
Webqq便是基于MVC设计模式设计的，原因如下：
1，MVC设计模式较为成熟。
2，MVC设计模式较为简单，能够很容易的将各个定义模块或组件相分离。
3，其扩展性较好。
基于webqq海量的服务数据存储，以及同时间段成千上万的服务请求，因此数据成为架构的中心，基于以下情况，我们选择以数据库为中心的架构，它针对性较强，直接面对数据，并且较为成熟，且易于实现。其基本架构分为四个部分：
![alt next](http://b267.photo.store.qq.com/psb?/V10ymuAs4OUe9j/vf8wpvRcdX.25MqihaenAc*Avv0mZtfuzkjoFUti4qc!/b/dJPNMp9bLQAA&bo=KwJKAQAAAAADAEc!)   
    
目标：
     提供稳定，快速的响应时间，能够是用户获得一个较好的用户体验。
     保障数据的安全性，以及数据及时备份。
     保证服务器集群发挥相应服务能力。
     清晰的模块化，使得系统能够使用团队开发模式。
结束语：
     架构是一种平衡的艺术，其宗旨是绝不是简单的问题复杂化，也绝不使复杂的问题简单化。如何把握这种平衡很关键，因为架构是系统整体的抽象，一个不好的架构将导致系统效率低下。本文通过webqq架构构造过程，一步步解析定义模块或组件原因，和整体交互之间的思量。本文没有涵盖所有的架构，只基于webqq该项目选择合适的架构加以实现。

架构设计和分析：
首先我们构造webQQ基本架构图，然后再一步步对其具体化，细化，和抽象化。
![alt next](http://b228.photo.store.qq.com/psb?/V10ymuAs4OUe9j/mwJ2.TWNLPL5wVx54IfZ3E7gBnPnL7rs7BtUj1iGNvA!/b/dMbs.YeVAgAA&bo=KwJSAQAAAAADAF8!)
WebQQ界面：用于显示界面信息，是用户与系统的交互，用户可以通过该界面给好友发送消息，访问QQ空间，以及各种小应用。相当于MVC中的view。
WebQQ代理服务器：接收用户请求，并将用户请求分类，发送至底层服务器。相当于MVC中的控制器。
底层服务器：对业务进行计算，并将结果返回给控制器。相当于MVC中的模型。
对于webQQ架构模型进一步细化：
![alt next](http://b268.photo.store.qq.com/psb?/V10ymuAs4OUe9j/vYTwxhS4LnMuKmUVftuYzfn8rvNxb30I6PljJFhUuzE!/b/dHm*wJ8gJwAA&bo=KwJOAQAAAAADAEM!)





细化后的架构主要是服务器的具体化，针对每一个服务器具有特定的功能。由于webQQ功能较多，细化后部件较多，上图只列出具体的几个重要构件。用户发送请求，有服务器接收，服务器根据请求的不同，将请求发生到专门的服务器，专门的服务器根据具体情况更改存储服务器，或通过网络发送消息给用户。
通过以上架构，我们对webQQ有了一定了解。接下来我们对框架进行进一步抽象，以数据为中心的架构出来，抽象化应用，关注与底层数据的管理。
对于数据的管理应用2钟技术，拆分和合并。
拆分是指将不同业务进行分类，和分析存储
合并是指将存储在不同服务器的数据进行合并。
![alt next](http://b266.photo.store.qq.com/psb?/V10ymuAs4OUe9j/qfZubqfCLCai3k1UZ8micc1kAaaUygRp26sdDmrauCg!/b/dG.Zkp52LQAA&bo=KwJBAQAAAAADAEw!)

具体化架构如下：
![alt next](http://b227.photo.store.qq.com/psb?/V10ymuAs4OUe9j/ANBkq5RjTISxGaUlbgYyM1EUA6L5EvDkG6ZMxvPsApc!/b/dMYtWIdlJwAA&bo=YwK.AQAAAAABAPk!)
上述架构很好地体现了拆分和合并的思想，在于根据用户请求区别化处理，以获得更快的响应时间。首先用户发送请求，有接收器接收请求，然后将请求分类，中间的统一调度模块根据请求类别访问不同存储。从而实现高效的查找。其架构过程到此告一段落。我们有简单到复杂一步步构造系统的整体架构，遵循架构的基本思想，清晰的展示了架构构造过程。并且很容易验证架构的简单性和和高效性。






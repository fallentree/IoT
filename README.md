# IoT
实训期间物联网学习

理论上，不论我们使用哪种互联网接入方式，只要我们的设备可以通过TCP/UDP通信访问互联网上对应IP地址的主机，那么当设备与云服务器建立UDP/TCP通信后，只要按照云服务器所规定的通信协议（数据格式）发送/接受消息，我们的设备就能够接入云平台，实现物联网。

### 一些要注意的地方：

学习过程中被注意的新旧知识：

###### QoS、大端小端、目录结构: "sport"和"sport/"有什么区别、tcp/ip协议（复习计网）

##### QoS：用来解决网络延迟和阻塞等问题的一种技术

  QoS（Quality of Service，服务质量）指一个网络能够利用各种基础技术，为指定的网络通信提供更好的服务能力, 是网络的一种安全机制， 是用来解决网络延迟和阻塞等问题的一种技术。 在正常情况下，如果网络只用于特定的无时间限制的应用系统，并不需要QoS，比如Web应用，或E-mail设置等。但是对关键应用和多媒体应用就十分必要。当网络过载或拥塞时，QoS 能确保重要业务量不受延迟或丢弃，同时保证网络的高效运行。

  ##### 为满足用户对不同应用不同服务质量的要求，采用不同的QoS
  
  而当网络发生拥塞的时候，所有的数据流都有可能被丢弃；为满足用户对不同应用不同服务质量的要求，就需要网络能根据用户的要求分配和调度资源，对不同的数据流提供不同的服务质量：对实时性强且重要的数据报文优先处理；对于实时性不强的普通数据报文，提供较低的处理优先级，网络拥塞时甚至丢弃。QoS应运而生。
  
  支持QoS功能的设备，能够提供传输品质服务；针对某种类别的数据流，可以为它赋予某个级别的传输优先级，来标识它的相对重要性，并使用设备所提供的各种优先级转发策略、拥塞避免等机制为这些数据流提供特殊的传输服务。
  
  ###### 配置了QoS的网络环境，增加了网络性能的可预知性，并能够有效地分配网络带宽，更加合理地利用网络资源。
  
  通常QoS提供以下三种服务模型：
  
    Best-Effort service（尽力而为服务模型）
    
    Integrated service（综合服务模型，简称Int-Serv）
    
    Differentiated service（区分服务模型，简称Diff-Serv）
  
  Best-Effort服务模型是一个单一的服务模型，也是最简单的服务模型。对Best-Effort服务模型，网络尽最大的可能性来发送报文。但对延时、可靠性等性能不提供任何保证。
  
  Best-Effort服务模型是网络的缺省服务模型，通过FIFO（first in first out 先入先出）队列来实现。它适用于绝大多数网络应用，如FTP、E-Mail等。
  
  在mqtt协议中，QoS分成了三个级别：
  
  QoS 0：最多分发一次
  
  QoS 1：至少分发一次
  
  QoS 2：只分发一次
  

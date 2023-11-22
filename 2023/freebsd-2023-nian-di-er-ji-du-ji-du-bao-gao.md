# FreeBSD 2023 年第二季度 季度报告

#### 2023年第二季度FreeBSD状态报告

以下是2023年第二季度的状态报告，共有37项内容。

您可能会注意到，与上一季度相比，我们有更多的报告。这是一个好消息，显示出FreeBSD社区的活跃程度，他们一直致力于提供高质量的软件。

特别值得注意的是，夏季已经开始，请不要错过我们的Google Summer of Code学生们分享的令人惊叹的项目。

祝阅读愉快。

Lorenzo Salvadore，代表状态团队。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

这份报告的网页版本可以在此处查看：

https://www.freebsd.org/status/report-2023-04-2023-06/


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

目录

* FreeBSD团队报告
    * FreeBSD核心团队
    * FreeBSD基金会
    * FreeBSD发布工程团队
    * 集群管理团队
    * 持续集成
    * Ports集合
* 项目
    * Cirrus-CI
    * FreeBSD内核中的BATMAN支持
    * LinuxBoot上的FreeBSD支持
    * LLDB内核模块改进
* 用户空间
    * 基础中的OpenSSL 3
    * Linux兼容层更新
    * 服务Jails - 自动监禁rc.d服务
    * 使用ktrace(1)进行安全沙箱
    * NVMe over Fabrics
* 内核
    * 引导性能改进
    * 引导加载程序的CI测试工具
    * FreeBSD内核的物理内存压缩
    * 增加MAXCPU
    * FreeBSD内核的SquashFS端口
    * Pf改进
    * 网络接口API（IfAPI）
    * 使Netgraph无锁
* 架构
    * amd64的SIMD增强
    * 将mfsBSD集成到发布构建工具中
* 云
    * FreeBSD作为Tier 1云初始化平台
    * FreeBSD上的OpenStack
    * FreeBSD在Microsoft HyperV和Azure上
    * FreeBSD在EC2上
* 文档
    * 文档工程团队
* 端口
    * FreeBSD上的KDE
    * FreeBSD上的GCC
    * 木偶
    * FreeBSD上的MITRE Caldera
    * FreeBSD上的Wazuh
* 第三方项目
    * PkgBase.live
    * 容器和FreeBSD：Pot、Potluck和Potman


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD团队报告**

来自各个官方和半官方团队的条目，可以在管理页面找到。

**FreeBSD核心团队**

联系：FreeBSD核心团队 <core@FreeBSD.org>

FreeBSD核心团队是FreeBSD的治理机构。

**DevSummit 202305**

核心团队于5月17日至18日在FreeBSD开发者峰会上进行了状态更新。幻灯片可在https://wiki.freebsd.org/DevSummit/202305 查看。

**FreeBSD 14**

核心团队正在与其他团队合作，确保FreeBSD 14.0-RELEASE将达到最高质量。

核心团队不反对将riscv64sf（64位RISC-V软浮点）标记为在14中不受支持。

**与FreeBSD基金会的会议**

核心团队和FreeBSD基金会继续定期会面，讨论FreeBSD的管理、开发和未来的下一步计划。核心团队与基金会的董事会和雇员进行了两次会议。他们讨论了基金会如何帮助核心团队和项目的整体情况。

**Matrix即时通讯解决方案**

在DevSummit 202305的核心团队更新中，提出了一个新的项目通信解决方案。

目前，由clusteradm在matrix-dev.FreeBSD.org上设置了一个测试实例。所有开发人员都可以使用他们的Kerberos凭据访问该实例，并且可以通过Matrix的联邦功能加入一些公共房间。请注意，此实例仅用于测试和评估，因此不能保证备份或可用性。

核心团队仍在讨论此服务的范围和管理，并从社区中收集反馈。

**行为准则委员会**

行为准则委员会（conduct@）现在由核心团队管理。

**提交权限**

核心批准了Christos Margiolis（christos@）的src提交权限。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD基金会**

链接：

FreeBSD基金会网址：https://www.freebsdfoundation.org

技术路线图网址：https://freebsdfoundation.org/blog/technology-roadmap/

捐赠网址：https://www.freebsdfoundation.org/donate/

基金会合作计划网址：https://freebsdfoundation.org/our-donors/freebsd-foundation-partnership-program/

FreeBSD期刊网址：https://www.freebsdfoundation.org/journal/

基金会新闻和事件网址：https://www.freebsdfoundation.org/news-and-events/


联系人：Deb Goodkin <deb@FreeBSDFoundation.org>

FreeBSD基金会是一家501(c)(3)非营利组织，致力于支持和推广全球范围内的FreeBSD项目和社区。来自个人和公司的捐款用于资助和管理软件开发项目、会议和开发者峰会。我们还向FreeBSD贡献者提供旅行资助，购买和支持硬件以改善和维护FreeBSD基础设施，并提供资源以提高安全性、质量保证和发布工程工作。我们发布营销材料以推广、教育和倡导FreeBSD项目，促进商业供应商与FreeBSD开发人员之间的合作，并最终代表FreeBSD项目执行需要承认的合同、许可协议和其他法律安排的FreeBSD项目。

**祝FreeBSD 30周年快乐！**

在过去的23年中，我们自豪地支持这个卓越的操作系统及其充满活力的社区，并热切期待在未来的许多年里继续支持它们。在此更新中，我们将概述我们在多个领域对FreeBSD的贡献。我们将涉及一些项目开发倡议，其中一些有详细的报告。此外，我们还将展示我们对FreeBSD的倡导，促进社区参与的努力以及我们扩大合作努力的情况。最后，我们将深入探讨我们正在进行的工作，以确保获得更多的资金，使我们能够分配额外的资源来解决项目中的任何空白。

**筹款**

在本季度，我们在与商业FreeBSD用户互动方面取得了重要进展。为了加强与现有和潜在商业用户的合作伙伴关系，我们聘请了Greg Wallace担任合作伙伴和研究总监。他的主要目标是扩大我们与商业用户的合作关系。自从担任这个职务以来，Greg已经开始忙碌地在一个季度内与众多公司会面。这些互动为我们提供了关于FreeBSD如何被使用、用户面临的挑战以及项目可以改进的领域的宝贵见解。通过了解这些方面，我们可以在何处分配我们的资金并认识到FreeBSD的独特优势，做出明智的决策。此外，这个角色还涉及进行研究，以确定目标市场，探索FreeBSD的新机会，并确保我们的声音在相关讨论中被听到。有关Greg的目标和成就的更多详细信息，您可以参考他下面的状态更新。

基金会向所有为支持我们的工作而做出财政贡献的人表示衷心的感谢。除了许多个人的贡献之外，我们很高兴收到来自NetApp和Blackberry的较大捐款。此外，我们收到了来自Tarsnap、iXsystems和LPI的FreeBSD开发者峰会赞助。这些赞助在抵消我们的开支方面提供了巨大的帮助，并使我们能够向与会者提供负担得起的注册费用。

今年我们的预算约为2,230,000美元，其中包括增加用于FreeBSD倡导和软件开发的支出。我们预算的一半以上用于直接与改进FreeBSD和保持其安全性相关的工作。

通过有一个专门负责合作伙伴关系的人，我们可以有效地强调投资我们努力的重要性，并强调项目的长期可行性。

您的支持在我们的使命中起着至关重要的作用，我们深切感谢您对FreeBSD社区的承诺。请考虑为我们的2023年筹款活动捐款！https://www.freebsdfoundation.org/donate/

对于更显赫的商业捐助者，我们有FreeBSD基金会合作计划，该计划于2017年建立。 

**合作计划**

你好，FreeBSD社区。我叫Greg Wallace，我于四月初加入基金会担任合作伙伴和研究总监。这篇博客介绍了我和我的角色。在合作方面，我的重点是与使用FreeBSD的公司建立联系。我已经与几家公司会面，了解他们如何使用FreeBSD。其中一些会议已经引发了关于潜在合作的讨论。我继续了解使用FreeBSD的有趣公司，并与他们联系。

我的目标是与每家使用和构建FreeBSD的公司取得联系，倾听他们的故事。如果您是这样的公司，而我们还没有联系，请在我的日历上安排一次电话。

本季度的一些其他与合作相关的活动：

* 我创建了这些幻灯片，介绍了与基金会合作如何推动FreeBSD的发展。如果您对我如何改进这些幻灯片有任何想法，或者希望我向您的组织展示它们，请给我发送电子邮件，或安排一次电话。并请随意自由地分享演示文稿的全部或部分。

* 我与基金会的同事一起创建了一些行业特定用例幻灯片，用于向行业分析师进行演示。

* 我还正在寻找包括以下机构在内的资助机会：

   * 国家科学基金会安全和值得信赖的网络空间（SaTC）

   * 主权技术基金

   * 下一代互联网。

在研究方面，我的广泛目标是确保该社区的所有专业知识在全球关于计算性能、安全性和能源效率的对话中都能反映出来。作为一个社区，我们在这项工作中有很多可以贡献的东西。

到目前为止，我一直在跟踪和参与以下主题：

* Open Forum Europe

* CHIPS研发。

如果您有研究想法或对在这个领域一起工作感兴趣，请给我发送电子邮件，或安排一次电话。

**操作系统改进**

在2023年第二季度，有339个src提交，155个端口提交，以及20个文档树提交被确认为由FreeBSD基金会赞助。其中一些以及其他由基金会赞助的工作在独立的报告条目中有所描述：

  * 持续集成

  * FreeBSD作为一级cloud-init平台

  * 在基础设施中使用OpenSSL 3

  * FreeBSD上的OpenStack

  * 使用ktrace(1)进行安全沙盒化

  * 用于amd64的SIMD增强

以下是基金会赞助的其他工作的例子：

  * 为fsck_ffs(8)进行的错误修复

  * 为killpg(2)进行的错误修复

  * 对hwpmc的改进

  * 对vmm的改进

  * 对LLVM 16和OpenSSL 3.0的端口修复和解决方法

  * 将kinst端口到RISC-V并进行相关的DTrace工作

  * 将libfido2更新到版本1.9.0

  * 各种LinuxKPI 802.11的改进

  * 各种RISC-V的改进

  * 从版本4.9.3升级tcpdump到版本4.99.4的供应商导入和更新。

当前和过去基金会合同工作的状态可以在基金会项目页面上查看。

基金会技术团队的成员在5月17日至18日在加拿大渥太华举行的开发者峰会上做了演讲。这包括主持GSoC、FreeBSD基金会技术审查和工作流工作组会议。Pierre Pronchery谈到了BSD之间的驱动程序协调，而En-Wei Wu则讨论了在与基金会签订合同的情况下完成的wtap工作。

**持续集成和质量保证**

基金会提供了一个全职员工以及资金来改进FreeBSD项目的持续集成、自动化测试和总体质量保证工作。您可以在专门的报告条目中详细了解有关CI工作的信息。

**倡导**

我们的许多工作都致力于FreeBSD项目的倡导。这可能涉及突出显示有趣的FreeBSD工作、制作文学和视频教程、参加活动或进行演讲。我们制作文学的目标是教导人们FreeBSD的基础知识，帮助他们更轻松地采用或贡献。除了参加和在活动中演讲外，我们鼓励并帮助社区成员组织自己的FreeBSD活动，进行演讲或承办FreeBSD展台。

FreeBSD基金会赞助了世界各地许多与BSD相关的会议、活动和峰会。这些活动可能是与BSD相关的、开源的或面向少数群体的技术活动。我们支持以FreeBSD为重点的活动，以帮助提供一个分享知识、共同开展项目并促进开发人员和商业用户之间合作的场所。这有助于提供一个健康的生态系统。我们支持与FreeBSD无关的活动，以促进和提高对FreeBSD的认识，增加FreeBSD在不同应用程序中的使用，并招募更多的贡献者加入项目。我们很高兴能够再次亲自参加大多数活动。除了参加和计划活动外，我们不断努力开展新的培训计划，并更新我们的操作指南，以便更多人尝试FreeBSD。

查看我们进行的一些宣传和教育工作：

  * 协助组织并参加了于2023年5月17日至18日在加拿大安大略省渥太华举行的开发者峰会

  * 主持了BSDCan，并成为BSDCan于2023年5月17日至20日在加拿大安大略省渥太华举行的布袋赞助商

      * 博客上可以找到旅行报告

  * 在BSDCan庆祝了项目的30岁生日，提供了蛋糕和FreeBSD Journal的30周年特别版的印刷副本

  * 在FOSSY（2023年7月13日至16日，美国俄勒冈州波特兰）上为FreeBSD研讨会和演讲提供支持

  * 为EuroBSDCon 2023（2023年9月14日至17日，葡萄牙科英布拉）提供了我们的银牌赞助

  * 为All Things Open（2023年10月15日至17日，美国北卡罗来纳州罗利）提供了我们的展位

  * 开始筹划FreeBSD秋季供应商峰会

  * 欢迎两位新成员加入团队：Greg Wallace和Pierre Pronchery

  * 发布了4月和6月的通讯

  * 在6月19日及当周通过特别视频和博客文章庆祝了FreeBSD日和项目的30周年

  * 其他博客文章：

      * EuroBSDcon 2023旅行资助申请现已开放 - 注意：申请截止日期为2023年8月2日

      * AsiaBSDcon旅行报告

  * FreeBSD在新闻中：

      * InfoWorld：FreeBSD 30周年快乐！

。

**Legal/FreeBSD IP**

我们通过发布专业制作的FreeBSD Journal来向世界教育有关FreeBSD的知识。正如我们之前提到的，FreeBSD Journal现在是一份免费的出版物。欲了解更多信息并获取最新期刊，请访问https://
www.freebsdfoundation.org/journal/。

您可以在https://www.FreeBSDfoundation.org上找到有关我们如何支持FreeBSD以及我们如何帮助您的更多信息！


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD发布工程团队**

链接：

FreeBSD 13.2-RELEASE计划网址：https://www.freebsd.org/releases/13.2R/schedule/

FreeBSD 14.0-RELEASE计划网址：https://www.freebsd.org/releases/14.0R/schedule/

FreeBSD发布网址：https://download.freebsd.org/releases/ISO-IMAGES/

FreeBSD开发快照网址：https://download.freebsd.org/snapshots/ISO-IMAGES/



联系：FreeBSD发布工程团队 <re@FreeBSD.org>

FreeBSD发布工程团队负责制定和发布FreeBSD官方项目发布的发布计划，宣布代码冻结并维护相应的分支，等等。

在2023年第二季度，该团队继续进行13.2-RELEASE的工作。13.2周期紧随制定的计划进行，最后在四月中旬新增了三个RC构建，最终在四月中旬发布了最终版本。

与项目管理中的各个团队协调，FreeBSD发布工程团队重新考虑了即将发布的14.0-RELEASE的原始计划，主要是由于正在进行的工作。更新后的计划经过讨论并进行了轻微调整以解决一些问题，并最终发布在FreeBSD项目网站上。新计划将14.0-RELEASE定于2023年十月发布。

该团队继续为主要的、stable/13和stable/12分支提供每周的开发快照构建。请注意，未来将不再对stable/12进行快照构建。

赞助商：Tarsnap 赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Cluster Administration Team（集群管理团队）**

链接：

Cluster Administration Team成员网址：https://www.freebsd.org/administration/#t-clusteradm

联系：Cluster Administration Team <clusteradm@FreeBSD.org>

FreeBSD集群管理团队成员负责管理项目依赖的机器，以同步其分布式工作和通信。

在本季度，团队开展了以下工作：

  * 定期支持FreeBSD.org用户帐户。

  * 为所有物理主机和镜像提供定期的磁盘和零部件支持（以及更换）。

  * 在FreeBSD项目管理的镜像中启用https://www.FreeBSD.org和https://docs.FreeBSD.org的镜像。

  * 集群刷新，将所有主机和jails升级到14-CURRENT、13-STABLE和12-STABLE的最新版本。

**正在进行的工作：**

  * 在我们的主要站点进行大规模网络升级。

      * 新的Juniper交换机已经到达我们的主要站点，以替换以前的交换机。我们感谢Juniper的捐赠。

  * 替换我们主要站点和一些镜像中的旧服务器。

      * 除了破损的CI服务器外，我们还有一些带有损坏磁盘和故障电源的旧服务器。这项任务是与FreeBSD基金会以及捐赠者/赞助商共同进行的。

  * 安装新的CI（持续集成）机器，这些机器是从软件包构建器中重新定位的。

  * 审查在FreeBSD集群中运行的服务的备份配置。

**FreeBSD官方镜像概述**

当前位置包括澳大利亚、巴西、德国、日本（两个完整的镜像站点）、马来西亚、南非、台湾、英国（完整的镜像站点）、美国 - 加利福尼亚、新泽西（主站点）和华盛顿。

硬件和网络连接慷慨地由以下提供：

  * Bytemark Hosting

  * BroadBand Tower，Inc的云和SDN实验室

  * 国立阳明交通大学计算机科学系

  * Equinix

  * 澳大利亚互联网协会

  * 互联网系统协会

  * INX-ZA

  * KDDI Web Communications Inc

  * 马来西亚研究与教育网络

  * Metapeer

  * NIC.br

  * Your.Org

  * 365数据中心

法兰克福单服务器镜像是欧洲主要的带宽和使用量镜像。

我们仍在寻找欧洲的额外完整镜像站点（五台服务器），以替换英国完整镜像站点中的旧服务器。

我们看到在全球各地的互联网交换点拥有单一镜像的好模式（澳大利亚、巴西和南非）；如果您知道或在这些交换点工作，并且可以赞助一个单一镜像服务器，请与我们联系。美国（西海岸）和欧洲（任何地方）是首选地点。

请查看完整镜像站点规格的通用镜像布局以及单一镜像站点的小型镜像。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**持续集成**

链接：

FreeBSD Jenkins实例网址：https://ci.FreeBSD.org

FreeBSD CI构建存档网址：https://artifact.ci.FreeBSD.org

FreeBSD Jenkins维基网址：https://wiki.FreeBSD.org/Jenkins

托管的CI维基网址：https://wiki.FreeBSD.org/HostedCI

第三方软件CI网址：https://wiki.FreeBSD.org/3rdPartySoftwareCI

与freebsd-testing@相关的问题网址：https://bugs.freebsd.org/bugzilla/buglist.cgi?bug_status=open&email1=testing%40FreeBSD.org&emailassigned_to1=1&emailcc1=1&emailtype1=equals

FreeBSD CI仓库网址：https://github.com/freebsd/freebsd-ci

dev-ci邮件列表网址：https://lists.FreeBSD.org/subscription/dev-ci


联系人：Jenkins管理员 <jenkins-admin@FreeBSD.org>

联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

联系人：freebsd-testing邮件列表

联系人：IRC #freebsd-ci channel on EFNet

在2023年第二季度，我们与项目贡献者和开发人员合作，满足了他们的测试需求。同时，我们与外部项目和公司合作，通过在FreeBSD上进行更多测试来增强其产品。

重要完成的任务：

  * 添加了FreeBSD-stable-13-amd64-gcc12_build作业。

  * 将主要和stable/13分支的构建环境更改为13.2-RELEASE，将stable/12更改为12.4-RELEASE。

  * 使用gcc12的*-build作业将故障报告发送到dev-ci邮件列表。

  * 在BSDCan 2023开发者峰会上呈现测试/CI状态更新。

正在进行的任务：

  * 设计并实施预提交CI构建和测试（以支持工作流工作组）。

  * 设计并实施使用CI集群构建发布工件，就像发布工程一样。

  * 简化贡献者和开发人员的CI/测试环境设置。

  * 设置CI阶段环境并在其中放置实验性作业。

  * 组织freebsd-ci仓库中的脚本，以便合并到src仓库。

  * 改进硬件测试实验室并增加更多的硬件进行测试。

  * 合并https://reviews.freebsd.org/D38815。

  * 合并https://reviews.freebsd.org/D36257。

待处理或排队的任务：

  * 收集和整理CI任务和想法。

  * 为运行测试的VM客户端设置公共网络访问。

  * 实施使用裸机硬件运行测试套件。

  * 添加对-CURRENT的drm端口构建测试。

  * 计划运行ztest测试。

  * 在其CI管道中帮助更多软件获得FreeBSD支持（维基页面：3rdPartySoftwareCI，HostedCI）。

  * 与托管的CI提供商合作，以获得更好的FreeBSD支持。

请查看与freebsd-testing@相关的问题，了解更多正在进行的工作信息，并随时加入我们的努力！

赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Ports集合**

链接：

关于FreeBSD Ports网址：https://www.FreeBSD.org/ports/

贡献到Ports网址：https://docs.freebsd.org/en/articles/contributing/#ports-contributing

FreeBSD Ports监视网址：http://portsmon.freebsd.org/

Ports管理团队网址：https://www.freebsd.org/portmgr/

Ports Tarball网址：http://ftp.freebsd.org/pub/FreeBSD/ports/ports/



联系人：René Ladan <portmgr-secretary@FreeBSD.org>

联系人：FreeBSD Ports管理团队 <portmgr@FreeBSD.org>


Ports管理团队负责监督Ports Tree的总体方向、构建软件包和人事事务。以下是上个季度的情况。

目前Ports Tree中有超过34,400个端口。目前有3,019个开放的端口PR，其中746个未分配。上个季度主分支有来自151个提交者的10,439次提交，2023Q2分支有来自55个提交者的745次提交。与上个季度相比，这意味着端口数量略有增加，开放PR数量略有减少，端口提交数量有相当大的增加。

在本季度，我们欢迎Tom Judge（tj@）回归，并告别了Steve Wills（swills@）。Steve也是portmgr的一部分。作为portmgr潜水员计划的一部分，我们欢迎Ronald Klop（ronald@）、Renato Botelho（garga@）和Matthias Andree（mandree@）。

Portmgr已经恢复了将子软件包引入Tree的工作，但仍有各种事项需要完善。

在软件方面，pkg已更新到1.19.2，Firefox更新到114.0.2，Chromium更新到114.0.5735.198，KDE Gear更新到23.04.2。在上个季度，antoine@进行了23次exp运行以测试软件包更新，将CPU_MAXSIZE提高到1024，修复了devel/cmake-core的armv7失败，并在USES=meson中添加了--auto-features=enabled。最后，Ports Tree已更新以支持FreeBSD-CURRENT中的LLVM 16和OpenSSL 3。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**Projects（项目）**

这些项目跨足多个类别，涵盖了从内核和用户空间到Ports集合或外部项目的各个领域。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Cirrus-CI**

链接：

FreeBSD Cirrus-CI仓库网址：https://cirrus-ci.com/github/freebsd/

FreeBSD src CI网址：https://cirrus-ci.com/github/freebsd/freebsd-src

FreeBSD doc CI网址：https://cirrus-ci.com/github/freebsd/freebsd-doc


联系人：Brooks Davis <brooks@FreeBSD.org> 联系人：Ed Maste <emaste@FreeBSD.org> 联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>


Cirrus-CI是一个托管的持续集成服务，支持在Linux、Windows、macOS和FreeBSD上进行CI服务的开源项目。它通过支持其他用例来补充我们自己的Jenkins CI基础架构，包括测试GitHub拉取请求和FreeBSD分支。我们在2019年向FreeBSD src树中添加了Cirrus-CI配置，并在2020年向doc中添加了配置。许多其他托管在GitHub上的FreeBSD项目（例如drm-kmod、kyua、pkg和poudriere）也使用了Cirrus-CI。

在过去的季度里，Cirrus-CI配置一直在进行维护更新（迁移到最新的FreeBSD发布镜像）。在src树中，我们添加了一些额外的检查。这些检查确保在需要时更新生成的文件（make sysent和make makeman），并检查缺少的目录。我们添加了使用Clang/LLVM 16工具链包构建的作业，与现在基本系统中的Clang版本相一致。GCC作业现在默认在GitHub镜像上对所有提交运行。

赞助商：DARPA 赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**BATMAN在FreeBSD内核中的支持**

链接：

维基页面网址：https://wiki.freebsd.org/SummerOfCode2023Projects/CallingTheBatmanFreeNetworksOnFreeBSD

源代码（Pull Request）网址：https://github.com/obiwac/freebsd-gsoc/pull/1


联系人：Aymeric Wibo <obiwac@FreeBSD.org>

BATMAN（Better Approach to Mobile Ad-hoc Networking），由Freifunk项目开发和使用，是一种用于（主要是无线）多跳自组织网络的路由协议。Freifunk是一个德国倡议，旨在基于网络中立性原则构建城市规模的开放式Wi-Fi网络。BATMAN的动机是成为一个完全分散的协议；网络中的任何一个节点都不知道整个网络的拓扑结构，也不必关心。

该协议的支持由Linux上的batman-adv内核模块提供，而该项目的目标是将其引入FreeBSD。这包括内核模块本身，以及创建BATMAN网络所需的用户空间网络库和工具。

目前，创建接口并与它们交互已经可以正常工作（在Linux和FreeBSD用户空间中都可以），并且数据包传输（在某种程度上）也可以工作，尽管目前还不完整。对于batadv接口，已经添加了对ifconfig(8)的支持。

导师：Mahdi Mokhtari

赞助商：Google Summer of Code '23计划


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD在LinuxBoot上的支持**

联系人：Warner Losh <imp@bsdimp.com>

链接：

LinuxBoot项目网址：https://www.linuxboot.org/

BSDCan 2023 kboot演讲幻灯片网址：https://docs.google.com/presentation/d/1N5Jp6XzYWv9Z9RhhETC-e6tFkqRHvp-ldRDW_9h2JCw/edit?usp=sharing


LinuxBoot是一个旨在创建清洁、强大、可审计和可重复启动固件的努力。最初是Google的一个特定项目，现在已经发展成为涵盖任何使用Linux启动最终操作系统的引导环境。许多平台现在都支持这个环境，在某些情况下，这是唯一可用的引导环境。此外，一些嵌入式设备的LinuxBoot环境是硬编码的，很难更改，因此能够重新启动到FreeBSD是可取的。

旧的Sony PlayStation 3端口使用了一个名为'kboot'的引导加载程序，用于从其Linux内核引导FreeBSD端口（所有这些都在LinuxBoot项目之前）。该代码已经大大扩展，通过易于替换的适用于各种体系结构的插件变得通用。正常的FreeBSD /boot/loader被构建为一个Linux二进制文件，它读取FreeBSD内核、模块和可调整项。它将它们放入内存中，就好像在预启动环境中运行一样，然后使用kexec_load(2)将该映像加载到Linux内核中，并执行特殊的重启到该映像。对于启用UEFI的系统，它传递UEFI内存表和指向新内核的UEFI运行时服务的指针。

它支持从主机文件系统、主机块设备上任何loader(8)支持的文件系统（包括跨多个设备的池）、ram磁盘映像以及通过网络下载的文件加载文件。可以使用这些的任何组合。例如，可以从主机文件系统加载配置覆盖，同时内核从专用存储（如NVME）或ram磁盘映像中加载。它支持通过stdin/stdout运行的主机控制台。它支持显式位置，例如/dev/nvme0ns1:/boot/loader/gerbil.conf，用于加载文件系统。它支持ZFS引导环境，包括一次性引导功能。

关于kboot、它支持的内容以及一些一般背景的其他详细信息可以在Warner的BSDcan演讲中找到（上面链接的幻灯片中有链接）。

现在，FreeBSD/aarch64可以在LinuxBoot环境中从Linux中引导，支持和功能与loader.efi(8)相当。为GICv3解决方案传递的内存布局正在进行。需要为aarch64内核提供GICv3解决方案的补丁（https://reviews.freebsd.org/D40902）。

FreeBSD/amd64支持正在进行中，可能已经完成80%。由于amd64是一个较早的端口，amd64启动环境对引导加载程序提供内核数据的要求更多。在长模式下，由于内核无法从BIOS环境中访问这些数据，因此所有数据的来源都必须由引导加载程序提供。虽然UEFI和ACPI提供了内核获取这些数据的方式，但由于引导加载程序仍需提供大部分数据，因此共享变得复杂。此外，构建基础设施使得共享变得尴尬。

PowerPC可以构建，但其状态的其他部分尚不清楚。由于作者尝试获取合适的Playstation 3变得耗时，因此获取PowerPC设备变得不切实际。

**需要帮助：**

1. 需要编写loader.kboot(8)。它应该说明如何使用loader.kboot、如何创建映像以及今天有效的用例。

2. 完成amd64支持。

3. 当前的elf架构特定的元数据代码是从efi复制的。需要统一kboot和efi的复制。虽然它们大部分相同，但由于残留的编译时差异，共享变得复杂。此外，构建基础设施使得共享变得尴尬。

4. 增加riscv64支持将是不错的。

5. PowerPC测试（自从重构开始以来一直没有测试过）。

6. 创建一个脚本，将EDK-II映像（比如从QEMU）重新打包为一个在FreeBSD上构建的Linux内核的linux-boot映像，以进行CI测试。

7. 从coreboot LinuxBoot进行测试。

赞助商：Netflix, Inc

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**LLDB内核模块改进**

链接：

GSoC Wiki 项目链接：https://wiki.freebsd.org/SummerOfCode2023Projects/LLDBKernelModuleImprovement

项目代码库链接：https://github.com/aokblast/freebsd-src/tree/lldb_dynamicloader_freebsd_kernel

联系人：洪圣逸 <aokblast@FreeBSD.org>

FreeBSD项目使用LLVM作为其工具链。LLVM项目内附带了一个名为LLDB的调试器。在LLDB中，用户空间的调试功能已经得到了良好的实现。然而，在内核空间中，仍然有一些工作需要完成。其中之一是为LLDB实现内核模块调试功能——即解析由内核核心转储提供的加载模块数据并加载模块对象。目标是为LLDB实现这样的插件，这是一个正在进行中的GSoC项目。

项目代码库包含了我工作的全部代码。

目前，这仍然是一个正在进行中的工作，我仍在对其进行调试。

赞助商：Google Summer of Code '23计划

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**用户空间**

对基本系统和其中的程序产生影响的变更。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**在基础系统中引入OpenSSL 3**

链接：

OpenSSL下载网址：https://www.openssl.org/source/

OpenSSL 3.0已发布！网址：https://www.openssl.org/blog/blog/2021/09/07/OpenSSL3.Final/

openssl-fipsinstall网址：https://www.openssl.org/docs/man3.0/man1/openssl-fipsinstall.html


联系人：Pierre Pronchery <pierre@freebsdfoundation.org>

Pierre被委托将OpenSSL 3引入基础系统。

OpenSSL是用于通用密码学和安全通信的库。它提供了SSL和TLS网络协议的开源实现，这些协议广泛用于诸如电子邮件、即时消息、互联网电话（VoIP）或更为突出的全球网络（即HTTPS）等应用中。假设Apache和nginx Web服务器使用OpenSSL，它们在Web流量中的联合市场份额超过50％，巩固了OpenSSL作为互联网基础设施的领导地位和重要性。

自2016年8月首次发布以来，OpenSSL的1.1分支已被大多数Linux和BSD系统采用，同时通过LTS（长期支持）政策得到上游维护者的支持。然而，官方支持计划在今年9月中旬结束，迫切需要考虑采用其继任者3.0分支进行LTS。

OpenSSL已经在很大程度上超越了其前身SSLeay，现在分布在两千多个文件中，超过50万行代码。或许是因为这个原因，它的构建系统相对复杂，通常需要Perl，而Perl在20多年前的FreeBSD 5.0-RELEASE中已经从基础系统中移除。然而，幸运的是，我们可以以FreeBSD的方式导入和设置OpenSSL 3.0.9，它现在已经是FreeBSD 14.0-RELEASE计划的一部分。

描述OpenSSL 3为一个重大发布是轻描淡写的。首先，其问题多多的许可模型最终得到解决，完全切换到Apache许可证2.0。然后，OpenSSL 3引入了提供程序模块的概念。尽管过时的加密算法已被隔离到一个遗留模块中，但也可以将实现限制为FIPS的标准部分，使用fips模块。后者然后可以受益于一个专门的认证过程，并得到官方验证（例如在写作时的3.0.8版本）。

此外，更新后的库带有版本号提升，因为使用OpenSSL 1.1的应用程序需要重新编译以使用3.0。许多API函数已被弃用，并用更新的、更通用的替代方案替换，但仍然可以显式请求旧的API，并让OpenSSL 3相应地公开它们。在FreeBSD中，已经利用了这种可能性，以帮助过渡，其中许多库和应用程序已经被配置为请求OpenSSL 1.1 API。这些组件将随着时间的推移逐步更新，以使用OpenSSL 3的本机API。

虽然在使用小输入块大小时，更新可能会带来已知的性能影响，但在使用1 KB及以上的块时，影响较小。另一个挑战在于FIPS提供程序模块，目前需要一些手动步骤才能使其正常工作。我们目前正在寻找一种解决方案，以默认情况下使用FreeBSD提供一个功能齐全的FIPS提供程序。

赞助商：FreeBSD基金会




━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Linux兼容层更新**

链接：

Linuxulator状态Wiki页面URL：https://wiki.freebsd.org/Linuxulator

Linux应用程序状态Wiki页面URL：https://wiki.freebsd.org/LinuxApps


联系人：Dmitry Chagin <dchagin@FreeBSD.org>

该项目的目标是提高FreeBSD执行未经修改的linux(4)二进制文件的能力。

截至cbbac5609115，实现了在amd64上通过信号传递保留fpu xsave状态。这使得可以在其上运行具有抢占调度程序的现代golang。

向namei(9)添加了指定替代ABI根路径的新功能。以前，要动态重新查找，每个需要路径名转换的linux(4)系统调用都需要一些丑陋的代码，并使用kern_alternate_path()，它不会正确解析目标中带有/的符号链接。目前，非本机ABI（即linux(4)）在exec时进入该ABI时使用一次pwd_altroot()调用来指定其根目录（例如/compat/ubuntu），并且不考虑路径名转换。这使得可以在不必手动修复此类符号链接的情况下chroot到Ubuntu兼容。

总共修复了超过10个错误；glibc-2.37测试套件报告少于70个失败的测试。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Service Jails - rc.d服务的自动监禁**

链接：

D40369: 使用设置ENV变量的可能性扩展/usr/bin/service URL：https://reviews.freebsd.org/D40369

D40370: 用于自动监禁rc.d服务的基础设施 URL：https://reviews.freebsd.org/D40370

D40371: 自动服务监禁：为自动服务监禁中的服务的完整功能进行一些设置 URL：https://reviews.freebsd.org/D40371


联系人：Alexander Leidinger <netchild@FreeBSD.org>

服务监禁扩展了rc(8)系统，允许自动监禁rc.d服务。服务监禁继承父主机或监禁的文件系统，但默认情况下使用监禁的所有其他限制（进程可见性、受限网络访问、文件系统挂载权限、sysvipc等）。附加配置允许继承父级的IP、sysvipc、内存页面锁定，并使用bhyve虚拟机监视器（vmm(4)）。

如果您想将例如local_unbound放入服务监禁并允许IPv4和IPv6访问，只需更改rc.conf(5)以包含：

local_unbound_svcj_options=net_basic
local_unbound_svcj=YES

尽管这没有使用单独的文件系统和IP/VNET进行手动监禁设置的相同安全好处，但它更容易设置，同时提供监禁的一些安全好处，如隐藏同一用户的其他进程。

链接中的补丁是我在2019年提出的东西的重写。主要区别在于使用ENV变量进行更合理的跟踪，因此需要更改service(8)。

我打算在stable/14的分支之前提交D40369。在14.0发布之前，我不会提交D40370或D40371，并且两者都将受益于更多的关注。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**使用ktrace(1)进行安全沙箱**

链接：
ktrace分支URL：https://github.com/jakesfreeland/freebsd-src/tree/ff/ktrace

联系人：Jake Freeland <jfree@FreeBSD.org>

**使用ktrace(1)的Capsicumization**

本报告介绍了对ktrace(1)的扩展，用于记录未经Capsicum化的程序的能力违规。

Capsicumization的第一步是确定程序引发能力违规的位置。您可以通过查看源代码并删除与Capsicum不兼容的代码来解决此问题，但这可能很繁琐，并且需要开发人员熟悉在能力模式中不允许的所有内容。

找到违规的替代方法是使用ktrace(1)。ktrace(1)实用程序记录指定进程的内核活动。能力违规发生在内核内部，因此ktrace(1)可以使用-t p选项记录并返回有关程序违规的额外信息。

传统上，需要将程序放入能力模式中，然后它才会报告违规。当输入受限系统调用时，它将失败并返回ECAPMODE：Not permitted in capability mode。如果开发人员正在进行错误检查，那么他们的程序可能会以该错误终止。这种行为使违规跟踪变得不方便，因为ktrace(1)只会报告第一个能力违规，然后程序将终止。

幸运的是，对ktrace(1)的新扩展可以在程序不在能力模式中时记录违规。这意味着任何开发人员都可以在其程序上运行能力违规跟踪，而无需修改，以查看它引发违规的位置。由于程序实际上从未进入能力模式，因此它仍会获取资源并正常执行。

**违规跟踪示例**

下面显示的`cap_violate`程序尝试引发ktrace(1)可以捕获的每种类型的违规：


```
# ktrace -t p ./cap_violate
# kdump
1603 ktrace   CAP   system call not allowed: execve
1603 foo      CAP   system call not allowed: open
1603 foo      CAP   system call not allowed: open
1603 foo      CAP   system call not allowed: open
1603 foo      CAP   system call not allowed: open
1603 foo      CAP   system call not allowed: readlink
1603 foo      CAP   system call not allowed: open
1603 foo      CAP   cpuset_setaffinity: restricted cpuset operation
1603 foo      CAP   openat: restricted VFS lookup: AT_FDCWD
1603 foo      CAP   openat: restricted VFS lookup: /
1603 foo      CAP   system call not allowed: bind
1603 foo      CAP   sendto: restricted address lookup: struct sockaddr { AF_INET, 0.0.0.0:5000 }
1603 foo      CAP   socket: protocol not allowed: IPPROTO_ICMP
1603 foo      CAP   kill: signal delivery not allowed: SIGCONT
1603 foo      CAP   system call not allowed: chdir
1603 foo      CAP   system call not allowed: fcntl, cmd: F_KINFO
1603 foo      CAP   operation requires CAP_WRITE, descriptor holds CAP_READ
1603 foo      CAP   attempt to increase capabilities from CAP_READ to CAP_READ,CAP_WRITE
```

前7`system call not allowed`调用条目并非明确源自`cap_violate`程序代码。相反，它们是由FreeBSD的C运行时库引发的。当您使用`-t np`选项跟踪namei翻译以及使用能力违规时，这一点就变得明显了：

```
# ktrace -t np ./cap_violate
# kdump
1632 ktrace   CAP   system call not allowed: execve
1632 ktrace   NAMI  "./cap_violate"
1632 ktrace   NAMI  "/libexec/ld-elf.so.1"
1632 foo      CAP   system call not allowed: open
1632 foo      NAMI  "/etc/libmap.conf"
1632 foo      CAP   system call not allowed: open
1632 foo      NAMI  "/usr/local/etc/libmap.d"
1632 foo      CAP   system call not allowed: open
1632 foo      NAMI  "/var/run/ld-elf.so.hints"
1632 foo      CAP   system call not allowed: open
1632 foo      NAMI  "/lib/libc.so.7"
1632 foo      CAP   system call not allowed: readlink
1632 foo      NAMI  "/etc/malloc.conf"
1632 foo      CAP   system call not allowed: open
1632 foo      NAMI  "/dev/pvclock"
1632 foo      CAP   cpuset_setaffinity: restricted cpuset operation
1632 foo      NAMI  "ktrace.out"
1632 foo      CAP   openat: restricted VFS lookup: AT_FDCWD
1632 foo      NAMI  "/"
1632 foo      CAP   openat: restricted VFS lookup: /
1632 foo      CAP   system call not allowed: bind
1632 foo      CAP   sendto: restricted address lookup: struct sockaddr { AF_INET, 0.0.0.0:5000 }
1632 foo      CAP   socket: protocol not allowed: IPPROTO_ICMP
1632 foo      CAP   kill: signal delivery not allowed: SIGCONT
1632 foo      CAP   system call not allowed: chdir
1632 foo      NAMI  "."
1632 foo      CAP   system call not allowed: fcntl, cmd: F_KINFO
1632 foo      CAP   operation requires CAP_WRITE, descriptor holds CAP_READ
1632 foo      CAP   attempt to increase capabilities from CAP_READ to CAP_READ,CAP_WRITE
```

在实际情况中，能力模式总是在C运行时库初始化后进入的，因此程序永远不会触发这前7个违规。我们之所以看到它们，仅是因为ktrace(1)在程序启动之前开始记录违规。

这个演示清楚地表明，违规跟踪并不总是完美的。它是检测受限制的系统调用的有用指南，但可能不总是模仿程序在能力模式下的实际行为。在能力模式中，违规等效于错误；它们是停止执行的指示。违规跟踪忽视了这个建议，继续执行，因此可能会报告无效的违规。

下一个例子跟踪了unzip(1)实用程序的违规（在Capsicumization之前）：

```
# ktrace -t np unzip foo.zip
Archive:  foo.zip
creating: bar/
extracting: bar/bar.txt
creating: baz/
extracting: baz/baz.txt
# kdump
1926 ktrace   CAP   system call not allowed: execve
1926 ktrace   NAMI  "/usr/bin/unzip"
1926 ktrace   NAMI  "/libexec/ld-elf.so.1"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/etc/libmap.conf"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/usr/local/etc/libmap.d"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/var/run/ld-elf.so.hints"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libarchive.so.7"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/usr/lib/libarchive.so.7"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libc.so.7"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libz.so.6"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libbz2.so.4"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/usr/lib/libbz2.so.4"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/liblzma.so.5"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/usr/lib/liblzma.so.5"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libbsdxml.so.4"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libprivatezstd.so.5"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/usr/lib/libprivatezstd.so.5"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libcrypto.so.111"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libmd.so.6"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libthr.so.3"
1926 unzip    CAP   system call not allowed: readlink
1926 unzip    NAMI  "/etc/malloc.conf"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/dev/pvclock"
1926 unzip    NAMI  "foo.zip"
1926 unzip    CAP   openat: restricted VFS lookup: AT_FDCWD
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/etc/localtime"
1926 unzip    NAMI  "bar"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    CAP   system call not allowed: mkdir
1926 unzip    NAMI  "bar"
1926 unzip    NAMI  "bar"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "bar/bar.txt"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "bar/bar.txt"
1926 unzip    CAP   openat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "baz"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    CAP   system call not allowed: mkdir
1926 unzip    NAMI  "baz"
1926 unzip    NAMI  "baz"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "baz/baz.txt"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "baz/baz.txt"
1926 unzip    CAP   openat: restricted VFS lookup: AT_FDCWD
```

对于unzip(1)，违规跟踪输出更类似于开发人员在首次跟踪自己的程序时会看到的内容。大多数程序链接到库。在这种情况下，unzip(1)正在链接到libarchive(3)，这在这里得到了反映：

```
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/lib/libarchive.so.7"
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/usr/lib/libarchive.so.7"
```

对于unzip(1)，违规可以在C运行时违规的下面找到：

```
1926 unzip    NAMI  "foo.zip"
1926 unzip    CAP   openat: restricted VFS lookup: AT_FDCWD
1926 unzip    CAP   system call not allowed: open
1926 unzip    NAMI  "/etc/localtime"
1926 unzip    NAMI  "bar"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    CAP   system call not allowed: mkdir
1926 unzip    NAMI  "bar"
1926 unzip    NAMI  "bar"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "bar/bar.txt"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "bar/bar.txt"
1926 unzip    CAP   openat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "baz"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    CAP   system call not allowed: mkdir
1926 unzip    NAMI  "baz"
1926 unzip    NAMI  "baz"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "baz/baz.txt"
1926 unzip    CAP   fstatat: restricted VFS lookup: AT_FDCWD
1926 unzip    NAMI  "baz/baz.txt"
1926 unzip    CAP   openat: restricted VFS lookup: AT_FDCWD
```

在这个实例中，unzip(1)正在重新创建zip存档中包含的文件结构。由于在能力模式下不能使用AT_FDCWD值，所以会引发违规。大多数这些违规可以通过在进入能力模式之前打开AT_FDCWD（当前目录）并将该描述符传递到openat(2)、fstatat(2)和mkdirat(2)中作为相对引用来解决。

违规跟踪可能不会自动使程序Capsicum化，但它是开发人员工具箱中的另一个工具。在ktrace(1)下运行程序只需几秒钟，结果几乎总是一个不错的起点，用于使用Capsicum对程序进行沙盒化。

赞助：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**NVMe over Fabrics**

链接：
nvmf2 分支链接：https://github.com/bsdjhb/freebsd/tree/nvmf2

联系人：John Baldwin <jhb@FreeBSD.org>

NVMe over Fabrics（NVMf）允许使用NVMe协议通过网络布局与存储设备通信。这类似于使用iSCSI通过网络使用SCSI命令导出存储设备。

NVMe over Fabrics当前定义了用于光纤通道、RDMA和TCP的网络传输。

nvmf2分支的工作包括一个用户态库（lib/libnvmf），其中包含一个传输的抽象以及TCP传输的实现。它还包括对nvmecontrol(8)的更改，以添加“discover”、“connect”和“disconnect”命令来管理与远程控制器的连接。

该分支还包含了一个内核Fabrics实现。nvmf_transport.ko包含一个传输抽象，位于nvmf主机（SCSI术语中的initiator）和各个传输之间。nvmf_tcp.ko包含TCP传输层的实现。nvmf.ko包含一个NVMe over Fabrics主机（initiator），它连接到远程控制器并将远程命名空间导出为磁盘设备。类似于用于NVMe over PCI-express的nvme(4)驱动程序，通过/dev/nvmeXnsY设备导出命名空间，仅支持简单的操作，但也通过CAM导出为ndaX磁盘设备。与nvme(4)不同，nvmf(4)不支持nvd(4)磁盘驱动程序。nvmecontrol(8)可以与远程命名空间和远程控制器一起使用，例如获取日志页面、显示标识信息等。

请注意，nvmf(4)目前还比较简单，某些错误情况仍然是待办的。如果发生错误，队列（以及支持的网络连接）将被丢弃，但设备仍然存在，I/O请求暂停。可以使用nvmecontrol reconnect连接一组新的网络连接以恢复操作。与iSCSI不同，后者使用持久守护程序（iscsid(8)）在错误后重新连接，重新连接必须手动完成。

当前的代码非常新，可能不够健壮。它当然还不适用于生产环境。有经验的用户，如果不介意在内核恐慌后看到所有数据烟消云散，且对NVMe over Fabrics有兴趣，可以自行冒险开始测试。

下一个主要任务是实现一个Fabrics控制器（SCSI语言中的目标）。可能首先是在用户空间中实现一个简单的控制器，然后是一个“真实”的控制器，它将数据处理卸载到内核，但与ctld(8)有一定的集成，以便可以通过iSCSI或NVMe导出个别磁盘设备，或者通过单个配置文件和守护程序来管理所有这些。这可能需要在ctld中进行一些重构，以使其不那么依赖iSCSI。在控制器方面的工作还将验证传输独立层中一些目前未经充分测试的API设计决策。我认为在完成此步骤之后，将NVMe over Fabrics的任何更改合并到树中可能是没有意义的。

赞助：Chelsio Communications


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**内核**

对内核子系统/功能、驱动程序支持、文件系统等进行了更新。

**启动性能改进**

链接：

维基页面网址：https://wiki.freebsd.org/BootTime

BSDCan演讲幻灯片网址：https://www.bsdcan.org/events/bsdcan_2023/sessions/session/116/slides/44/BSDCan23-Firecracker.pdf


联系人：Colin Percival <cperciva@FreeBSD.org>

Colin正在协调努力加速FreeBSD引导过程。

最近的工作已经从EC2转移到Firecracker虚拟机管理器，它提供了一个非常精简的环境；将引导过程精简到最低程度使得更容易识别剩余的时间并确定是否可以进一步优化。

通过对FreeBSD和Firecracker进行一些实验性的补丁，现在可以在不到20毫秒的时间内启动FreeBSD内核。

一些最近的改进在Colin的BSDCan上关于将FreeBSD移植到Firecracker的演讲中讨论过。

这项工作得到了他的FreeBSD/EC2 Patreon的支持。

赞助商：https://www.patreon.com/cperciva

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**引导加载程序的CI测试工具**

链接：
FreeBSD Wiki GSoC页面
Github项目链接

联系人：Sudhanshu Mohan Kashyap <smk@FreeBSD.org>

FreeBSD支持多种架构、文件系统和磁盘分区方案。我正在尝试编写一个Lua脚本，该脚本允许测试在第一和第二级支持中支持的所有架构组合的引导加载程序，并报告任何破损的组合和预期功能。如果时间允许，还可以进一步探索将脚本整合到现有的构建基础设施中（无论是Jenkins还是Github Actions），以生成对测试结果的全面摘要。

目前，开发人员所做的任何更改都可能阻止操作系统在某些特定环境中启动。这些脚本确保更改不会导致在经过测试的环境中出现回归。这些脚本设计得高效，成本远低于当前所需的完整make universe。这些特性使得开发人员能够定期使用脚本，并在不必要的成本下将其整合到CI流水线中。

目前，与脚本相关的工作似乎进展顺利，但在将来，我肯定需要找到各种不同的QEMU配方来测试不同的环境。如果有人对当前发布版本的FreeBSD有任何种类的有效QEMU配方，请随时通过邮件发送给我，邮箱是smk@FreeBSD.org。

赞助商：Google Summer of Code '23项目


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD内核的物理内存整理**

链接：

GSoC项目维基页面网址：https://wiki.freebsd.org/SummerOfCode2023Projects/

PhysicalMemoryAntiFragmentationMechanisms

差异修订40575网址：https://reviews.freebsd.org/D40575

差异修订40772网址：https://reviews.freebsd.org/D40772


联系人：Bojan Novković <bnovkov@FreeBSD.org>

大多数现代CPU架构通过支持大于标准页面大小的页面来提高性能。不幸的是，由于高度的物理内存碎片化，分配这样的页面可能会失败。这项工作实现了物理内存整理，作为主动减少运行系统碎片化的手段。这项工作是正在进行的Google Summer of Code项目的一部分，其目标是向虚拟内存子系统添加各种物理内存抗碎片化措施。

差异修订D40575实现了用于量化物理内存碎片化程度的众所周知的度量标准。差异修订D40772实现了物理内存整理，并添加了一个监视系统并在需要时执行整理的守护程序。

计划中的未来工作包括设计一个合适的基准测试套件，运行测试，并使用来自审查和测试结果的反馈调整代码。这仍然是一个正在进行的工作，因此任何测试、审查和反馈都将不胜感激。

赞助商：Google Summer of Code '23项目


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**增加MAXCPU**

链接：

审查D36838：amd64：将MAXCPU从256增加到1024 URL：https://reviews.freebsd.org/D36838


联系人：Ed Maste <emaste@FreeBSD.org>

默认的amd64和arm64 FreeBSD内核配置目前支持最多256个CPU。可以通过设置MAXCPU内核选项构建自定义内核，以支持更大的核心数。然而，具有超过256个CPU的商品系统正在出现，并且在FreeBSD 14的支持生命周期内将变得越来越普遍。我们希望将默认的最大CPU计数增加到1024，以便在FreeBSD 14上“开箱即用”地支持这些系统。

已经进行了一些更改以支持更大的默认MAXCPU，包括将cpuset_t的用户空间最大值修复为1024。还进行了一些更改，以避免静态的MAXCPU大小的数组，并用按需内存分配替换它们。

需要进一步的工作来继续减少由MAXCPU大小确定的静态分配，并解决非常高核心计数系统上的可扩展性瓶颈，但目标是在支持大型CPU计数的同时发布带有稳定ABI和KBI的FreeBSD 14。

赞助商：FreeBSD基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD内核的SquashFS移植**

链接：

维基页面网址：https://wiki.freebsd.org/SummerOfCode2023Projects/PortSquashFuseToTheFreeBSDKernel

源代码网址：https://github.com/Mashijams/freebsd-src/tree/gsoc/squashfs


联系人：Raghav Sharma <raghav@FreeBSD.org>

SquashFS是一个只读文件系统，可以非常高效地压缩整个文件系统或单个目录。自2009年以来，Linux内核内置了对它的支持，在嵌入式Linux发行版中非常常见。该项目的目标是为FreeBSD内核添加SquashFS支持，以便能够从内存中的SquashFS文件系统启动FreeBSD。

目前，该驱动程序与FreeBSD 13.2发布兼容。该驱动程序能够正确解析SquashFS磁盘文件，并支持mount(8)。Linux的SquashFS支持许多压缩选项，如zstd、lzo2、zlib等，根据用户的喜好，当然，我们的驱动程序也支持所有这些压缩方式。

计划中的未来工作包括添加目录、文件、扩展属性和符号链接的读取支持。该项目仍在由Chuck Tuffli指导的过程中进行，预计将在Google Summer of Code计划结束时完成。

赞助商：Google Summer of Code 2023项目


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Pf改进**

链接：

D40911 URL: https://reviews.freebsd.org/D40911

D40861 URL: https://reviews.freebsd.org/D40861

D40862 URL: https://reviews.freebsd.org/D40862

D40863 URL: https://reviews.freebsd.org/D40863

D40864 URL: https://reviews.freebsd.org/D40864

D40865 URL: https://reviews.freebsd.org/D40865

D40866 URL: https://reviews.freebsd.org/D40866

D40867 URL: https://reviews.freebsd.org/D40867

D40868 URL: https://reviews.freebsd.org/D40868

D40869 URL: https://reviews.freebsd.org/D40869

D40870 URL: https://reviews.freebsd.org/D40870


联系人：Kajetan Staszkiewicz <vegeta@tuxpowered.net>
联系人：Naman Sood <naman@freebsdfoundation.org>
联系人：Kristof Provost <kp@FreeBSD.org>

pf(4)是FreeBSD中包含的防火墙之一，可能是最受欢迎的。pf是由OpenBSD项目创建，随后被移植到FreeBSD。

回溯OpenBSD语法

Kajetan引入了在“match”和“pass”规则中进行“scrub”操作的OpenBSD语法。现有规则仍然受支持，但现在还支持OpenBSD风格的“scrub”配置。

pfsync协议版本

现在可以配置pfsync(4)协议版本，允许在仍然支持不同内核版本之间的状态同步的同时进行协议更改。其主要优势是允许协议更改以启用新功能。

pfsync：通过IPv6传输

pfsync流量现在也可以通过IPv6传输。Naman完成了Luiz Amaral开始的工作。

SCTP

有正在进行的工作以支持在pf中使用SCTP。该支持包括对端口号的过滤、状态跟踪、pfsync故障转移以及为拒绝的连接返回ABORT块。

赞助商：InnoGames GmbH 赞助商：Orange Business Services 赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**网络接口API（IfAPI）**

链接：

原始项目页面网址：link:https://wiki.freebsd.org/projects/ifnet

联系人：Justin Hibbits <jhibbits@FreeBSD.org>

IfAPI（原名DrvAPI）项目始于2014年，其目标是隐藏ifnet(9)结构对网络驱动程序的影响。相反，所有对成员的访问都将通过访问器函数进行。这允许更改网络堆栈而无需重新编译驱动程序，并且可能允许单个驱动程序支持FreeBSD的多个版本。

截至目前，该目标已在基础系统中实现，但有几个端口需要更新以使用IfAPI。有一个工具可自动化大部分转换，即tools/ifnet/convert_ifapi.sh。文档也在制作中，但需要帮助。ifnet(9)需要进行大量清理，因为目前其中的一些信息已经过时。

赞助商：Juniper Networks, Inc.


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**使Netgraph无锁**

链接：

维基页面网址：https://wiki.freebsd.org/SummerOfCode2023Projects/LocklessSynchronizationBetweenNodesInNetgraph

仓库网址：https://github.com/zinh88/epoch-netgraph


联系人：Zain Khan <zain@FreeBSD.org>

Netgraph通过允许我们使用称为节点的内核对象在连接使用钩子的图中排列节点来帮助我们实现自定义或复杂的网络功能。节点可以对传入的数据包执行一组明确定义的操作，并且可以将输出发送到另一个连接的节点。向邻居“发送”数据包也可以看作在该邻居节点上调用函数。

在非SMP世界中，线程（或线程）总是将节点视为空闲（不忙碌），以便它们的函数可以立即被调用。并发引入了繁忙节点的可能性。此外，数据包的旅程还需要注意图的结构的变化，例如：由于不存在的钩子或节点而导致的寻址节点的路径可能不再完整，这可能导致引用已被释放的对象的情况。为了对抗这种灾难，现有的源代码使用了一个拓扑读写互斥体，以保护数据流免受重构事件（以及来自其他重构事件的重构事件）的影响。

我们希望恢复当并发CPU还不是一件事时存在的数据的相同平稳流动。也就是说，每次发生重构事件时，数据都不应该等待。与此同时，我们显然也不希望给内核造成恐慌的理由。

FreeBSD有其自己一套与并发安全相关的数据结构和机制。其中之一是Epoch。基于Epoch的回收涉及等待现有读侧关键部分完成，然后再修改或回收数据结构。

由于正在修改基本系统，这也会影响以前的设计选择，例如在消息上排队，引用计数等。

这个项目涉及大量的测试。目前，一些拓扑保护锁已被移除，并且只测试了简单的图（在运行FreeBSD的VM上）。真正的测试应该在至少有4个CPU核心的硬件上运行，我在拿到这样的硬件时会进行测试。

赞助商：Google Summer of Code '23项目

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**架构**

更新特定平台的功能并为新的硬件平台提供支持。

**针对amd64的SIMD增强**


链接：

SIMD分发框架草稿URL：https://reviews.freebsd.org/D40693

项目提案URL：link:http://fuz.su/~fuz/freebsd/2023-04-05_libc-proposal.txt


联系人：Robert Clausecker <clausecker@FreeBSD.org>

诸如SSE、AVX和NEON之类的SIMD指令集扩展在现代计算机上无处不在，并为许多应用程序提供性能优势。该项目的目标是提供常见libc函数的SIMD增强版本（主要是在string(3)中描述的那些），加速大多数C程序的执行速度。

对于每个优化的函数，将提供最多四种实现：

  * 一个针对amd64优化的标量实现，但不使用任何SIMD，

  * 一个使用SSE和SSE2或者使用所有SSE扩展直到SSE4.2的x86-64-v2基准实现，

  * 一个使用AVX和AVX2的x86-64-v3实现，以及

  * 一个使用AVX-512F/BW/CD/DQ的x86-64-v4实现。

用户将能够通过设置AMD64_ARCHLEVEL环境变量来选择使用哪个级别的SIMD增强。

尽管当前项目仅涉及amd64，但将来可能会扩展到其他架构，如arm64。

赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**将mfsBSD集成到发布构建工具中**

链接：

维基文章网址：https://wiki.freebsd.org/SummerOfCode2023Projects/IntegrateMfsBSDIntoTheReleaseBuildingTools

项目存储库（integrate-mfsBSD-building分支）网址：https://github.com/soobinrho/freebsd-src/tree/integrate-mfsBSD-building


联系人：Soobin Rho <soobinrho@FreeBSD.org>

**什么是mfsBSD？**

"mfsBSD是一个用于创建基于mfsroot的FreeBSD的小型但功能齐全的分发工具集，该分发将所有文件存储在内存（MFS）[Memory File
System]中，并从硬盘、USB存储设备或光盘加载。它可用于各种目的，包括无盘系统、恢复分区和远程覆盖其他操作系统。"

Martin Matuska既是mfsBSD白皮书的作者，也是mfsBSD存储库的维护者。

**目的**

该项目在src/release makefile中为-current和-stable版本的每周快照创建mfsBSD镜像的额外目标。目前，仅生成mfsBSD镜像的发布版本，这意味着它们往往与基本工具不同步。该项目旨在解决这个问题。

**位置**

这是一个GSoC 2023（Google Summer of Code）项目。因此，正式的编码期间是在2023年5月29日至2023年8月28日期间。作为开源社区中的一位初学者，作者欢迎在项目存储库中的整个代码期间提出所有评论/建议/拉取请求。

导师：Juraj Lutter和Joseph Mingone

赞助商：Google Summer of Code '23项目


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
**云**

优化云相关功能，增添对新云平台的支持。


**FreeBSD作为Tier 1 cloud-init平台**

链接：

cloud-init网站网址：https://cloud-init.io/

cloud-init文档网址：https://cloudinit.readthedocs.io/en/latest/

cloud-init正在进行的重构网址：https://github.com/canonical/cloud-init/blob/main/WIP-ONGOING-REFACTORIZATION.rst


联系人：Mina Galić <freebsd@igalic.co>

cloud-init是在云中配置服务器的标准方式。不幸的是，除了Linux之外的操作系统对cloud-init的支持相当有限，而FreeBSD上缺乏cloud-init支持是云提供商想要将FreeBSD作为Tier 1平台提供的一种障碍。为了解决这种情况，该项目旨在使FreeBSD的cloud-init支持达到与Linux支持相当的水平。更广泛的计划是在所有BSD上提供支持。

这个季度进展缓慢，但我已经成功交付了一个新的里程碑：

  * 临时网络类别已被重写并使其与平台无关。这些类别被多个云提供商用于在检索实际配置之前初始化临时网络。

  * cloud-init已在Vultr上成功测试。我希望在下一次发布中，我能说服Vultr将其FreeBSD镜像切换到cloud-init。

除此之外，我扩展了BSD的rsyslog支持。我还为cloud-init的ds-identify添加了一个rc脚本，这应该使零配置设置的速度提高数个数量级：ds-identify首先运行并非常快速地猜测机器正在运行的云提供商。然后，cloud-init仅使用该猜测，而不是通过完整列举所有可能的云提供商进行迭代和失败。构建自定义镜像的人可以轻松禁用此功能（通过删除/usr/local/etc/rc.d/dsidentify），并提供自己的特定列表，从而从启动中刮掉更多的毫秒。

下一步将是继续致力于网络重构任务，并为FreeBSD添加对LXD的支持，以便将其包含在CI测试中。后者将包括对LXD的工作，以及对FreeBSD virtio子系统的工作。

像往常一样，我非常欢迎早期测试者检查net/cloud-init-devel，并报告错误。自上次报告以来，cloud-init的错误跟踪器已从Launchpad移至GitHub，因此这可能减少一些摩擦。

赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD上的OpenStack**

链接：

OpenStack网址：https://www.openstack.org/

FreeBSD上的OpenStack网址：https://github.com/openstack-on-freebsd


联系人：Chih-Hsin Chang <starbops@hey.com>
联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

该项目旨在移植关键的OpenStack组件，如keystone、nova和neutron，以便FreeBSD可以作为OpenStack主机运行。

我们开始移植nova-novncproxy和nova-serialproxy，以增加访问实例控制台的方式。为了降低想尝试该项目的人的门槛，我们还将我们的开发环境从物理机器迁移到虚拟机器。在Linux KVM之上运行bhyve VM仍然存在问题。有关此问题的详细说明可以在此处找到。其他的成就包括：

  * 解决实例内的网络连接问题

  * 能够生成多个实例

  * 从Python 3.8迁移到3.9。

在下一个季度，我们将继续致力于控制台代理服务，以使整体工作流更加流畅。

构建POC站点的逐步文档也可以在文档存储库中找到。每个OpenStack组件的修补版本都在同一GitHub组织下。

有兴趣帮助该项目的人可以首先通过按照安装指南进行安装来检查文档。我们始终欢迎反馈和帮助。

赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**在Microsoft HyperV和Azure上的FreeBSD**

链接：

FreeBSD维基上有关Microsoft Azure的文章网址：https://wiki.freebsd.org/MicrosoftAzure

FreeBSD维基上有关Microsoft HyperV的文章网址：https://wiki.freebsd.org/HyperV


联系人：Microsoft FreeBSD Integration Services Team <bsdic@microsoft.com>

联系人：freebsd-cloud邮件列表

联系人：FreeBSD Azure Release Engineering Team <releng-azure@FreeBSD.org>

联系人：Wei Hu <whu@FreeBSD.org>

联系人：Souradeep Chakrabarti <schakrabarti@microsoft.com>

联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

在本季度，我们主要致力于ARM64架构的支持，并构建和发布到Azure社区库的镜像。在项目的测试公共库中有一些测试镜像，名为FreeBSDCGTest-d8a43fa5-745a-4910-9f71-0c9da2ac22bf： * FreeBSD-CURRENT-testing * FreeBSD-CURRENT-gen2-testing * FreeBSD-CURRENT-arm64-testing

要使用它们，在创建虚拟机时： . 在选择图像步骤中，选择其他项中的社区图像（预览） . 搜索FreeBSD

正在进行的工作任务：

  * 自动化镜像构建和发布过程，并合并到src/
    release/。

  * 构建并发布基于ZFS的镜像到Azure Marketplace

      * 所有必需的代码都已合并到主分支，可以通过指定VMFS=zfs来创建
        基于ZFS的镜像。

      * 需要使构建过程更加自动化，并与发布工程合作开始生成快照。

  * 构建并发布Hyper-V gen2 VM镜像到Azure Marketplace

  * 将快照构建发布到Azure社区库

上述任务由FreeBSD基金会赞助，由Microsoft提供资源。

Microsoft的Wei Hu和Souradeep Chakrabarti正在进行由Microsoft赞助的多个任务：

  * 将Hyper-V客户机支持移植到aarch64

      * https://bugs.freebsd.org/267654

      * https://bugs.freebsd.org/272461

未完成的任务：

  * 在Microsoft Learn上更新有关FreeBSD的文档

  * 在Azure Pipelines中支持FreeBSD

  * 更新Azure代理端口到最新版本

  * 向上游提交Azure代理的本地修改

赞助商：Microsoft为Microsoft内部的人提供资源，FreeBSD基金会提供其他一切

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**FreeBSD在EC2上**

链接：

FreeBSD/EC2 Patreon网址：https://www.patreon.com/cperciva

联系人：Colin Percival <cperciva@FreeBSD.org>

FreeBSD可用于x86（Intel和AMD）和ARM64（Graviton）EC2实例。工作仍在进行，以确保将来的实例类型将得到支持，包括最近宣布的M7a“EPYC”实例，这应该在FreeBSD 14.0-RELEASE中得到支持。

最近，每周的FreeBSD快照从“UEFI”引导模式更改为“UEFI Preferred”引导模式，使它们能够获得UEFI提供的引导性能改进，同时仍支持与UEFI不兼容的“裸机”和“上一代”实例类型。此更改将出现在FreeBSD 14.0-RELEASE中。

EC2引导脚本最近已更新以支持IMDSv2。此更改将出现在FreeBSD 14.0-RELEASE中。

如果FreeBSD 13.2的用户需要这些更新之一，作者可以提供FreeBSD“13.2-RELEASE加更新” AMIs。

这项工作得到了Colin的FreeBSD/EC2 Patreon的支持。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**文档**

文档树、手册页面或新的外部书籍/文档中的重要变更。

**文档工程团队**

链接：FreeBSD文档项目网址：https://www.freebsd.org/docproj

链接：FreeBSD文档项目新贡献者入门指南网址：https://docs.freebsd.org/en/books/fdp-primer/

链接：文档工程团队网址：https://www.freebsd.org/administration/#t-doceng


联系：FreeBSD Doceng Team <doceng@FreeBSD.org>

doceng@ 团队是处理与FreeBSD文档项目相关的一些元项目问题的机构；有关更多信息，请参阅FreeBSD
Doceng Team章程。

在本季度：

  * fernape@ 被任命为新的Doceng团队成员。

  * www/gohugo 端口维护权已转移到doceng@，因为它是我们文档基础设施的关键部分。这得到了前维护者的同意。

  * 改进了翻译工作流程（在以下部分描述）。

**Porter's Handbook**

USES=nextcloud 已经有文档记录了。

**FDP Primer**

FreeBSD文档项目新贡献者入门指南添加了一个关于Weblate的新章节。这个全面的章节提供了逐步的指导，介绍了加入FreeBSD翻译团队的步骤，无论是在线在Weblate上翻译还是离线。它为有效的翻译、校对和测试过程提供了宝贵的见解和实用建议。此外，该章节为贡献者提供了必要的知识，以正式提交他们的翻译到文档库，确保其工作的无缝整合。

**FreeBSD在Weblate上的翻译**

链接：在Weblate上翻译FreeBSD网址：https://wiki.freebsd.org/Doc/Translation/Weblate

链接：FreeBSD Weblate实例网址：https://translate-dev.freebsd.org/


2023年第二季度状态

  * 15种语言

  * 183名注册用户

  * 新的Weblate服务器

FreeBSD Weblate实例现在在专用服务器上运行，显著提高了其速度，并增强了翻译工作的效率。我们由衷感谢ebrandi@提供这个硬件升级。

语言

  * 中文（简体）(zh-cn)（进度：7%）

  * 中文（繁体）(zh-tw)（进度：3%）

  * 荷兰语（nl）（进度：1%）

  * 法语（fr）（进度：1%）

  * 德语（de）（进度：1%）

  * 印尼语（id）（进度：1%）

  * 意大利语（it）（进度：5%）

  * 韩语（ko）（进度：32%）

  * 挪威语（nb-no）（进度：1%）

  * 波斯语（fa-ir）（进度：3%）

  * 波兰语（进度：1%）

  * 葡萄牙语（pt-br）（进度：22%）

  * 锡兰语（si）（进度：1%）

  * 西班牙语（es）（进度：33%）

  * 土耳其语（tr）（进度：2%）

我们要感谢所有贡献、翻译或审核文档的人。

请帮助在您的本地用户组中推广这一努力，我们总是需要更多的志愿者。

**FreeBSD手册工作组**

联系人：Sergio Carlavilla <carlavilla@FreeBSD.org>

网络章节正在重新制作。

**FreeBSD网站翻新 - WebApps工作组**

联系人：Sergio Carlavilla <carlavilla@FreeBSD.org>

负责创建新的FreeBSD文档门户和重新设计FreeBSD主网站及其组件的工作组。FreeBSD开发者可以在FreeBSD Slack频道#wg-www21中关注并加入工作组。工作分为四个阶段：

 1. 重新设计文档门户

    创建一个新的设计，具有响应式布局和全局搜索。（已完成）

 2. 重新设计网页上的手册页面

    使用mandoc生成HTML页面的脚本。（已完成）在https://man-dev.FreeBSD.org上的公共实例

 3. 重新设计网页上的Ports页面

    Ports脚本创建一个应用程序门户。（进行中）

 4. 重新设计FreeBSD主网站

    新的设计，具有响应式布局和深色主题。（进行中）


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Ports**

影响Ports Collection的变更，无论是触及整个树的大规模变更，还是单个端口本身。

FreeBSD上的KDE

链接：

KDE/FreeBSD计划网址：https://freebsd.kde.org/

FreeBSD — KDE社区维基网址：https://community.kde.org/FreeBSD


联系人：Adriaan de Groot <kde@FreeBSD.org>

KDE on FreeBSD项目为FreeBSD ports树打包CMake、Qt和来自KDE社区的软件。该软件包括一个名为KDE Plasma的完整桌面环境（适用于X11和Wayland）和数百个可在任何FreeBSD机器上使用的应用程序。

KDE团队（kde@）是desktop@和x11@的一部分，构建软件堆栈，使FreeBSD成为美观且可用作每日驱动的图形桌面工作站。下面的说明主要描述了KDE的端口，但也包括对整个桌面堆栈重要的项目。

**基础设施**

Qt5端口进行了各种更新：

  * 在使用Clang 16构建时，修复了devel/qt5-webengine。这是为了准备即将发布的FreeBSD 14。

  * 修复了devel/qt5-qmake，以处理在否则没有Qt的系统上安装qmake会导致奇怪错误的边缘情况。

Qt6端口进行了各种更新：

  * 在使用Clang 16构建时，修复了devel/qt6-tools。这是为了准备即将发布的FreeBSD 14。

桌面可访问性技术必备的accessibility/at-spi2-core端口已更新到版本2.48.0。

accessibility/at-spi2-core端口现在对非X11桌面有更好的支持。这对基于Wayland的系统是一项改进。感谢Jan Beich的贡献。

许多PDF查看器的基础graphics/poppler端口已更新到23.05。

ports-mgmt/packagekit-qt端口是树中的新成员，为FreeBSD上的图形包管理器铺平了道路。

**KDE堆栈**

KDE Gear每个季度发布一次，KDE Plasma每月更新一次，KDE Frameworks每月都有新版本发布。这些（大型）更新在其上游发布后不久就会到达，并且没有单独列出。

  * KDE Frameworks更新到5.105、.106和.107。

  * KDE Gear更新到23.04.0，然后是.1和.2，带有错误修复。

  * KDE Plasma Desktop更新到版本5.27.4，然后是.5和.6，带有错误修复。

**相关端口**

弃用：

  * graphics/ikona，一个用Rust编写的具有Qt绑定的图标查看器，已被上游弃用。

  * polish/kadu，曾在波兰流行的聊天应用，已被弃用，上游已消失。

  * sysutils/plasma5-ksysguard，一个系统监控应用程序，上游已弃用，将不再更新。

更新：

  * astro/kstars，一个交互式天文馆，已更新到版本3.6.4。

  * devel/qcoro，一个C++协程实现，已更新到0.9.0。

  * devel/qtcreator，用于Qt、C++等的集成开发环境，已更新到版本10.0.2。

  * games/gcompris-qt，一个面向3-12岁儿童的教育套件，已更新到版本3.2。

  * graphics/kphotoalbum，一个相册和显示实用程序，已更新到版本5.10.0。

  * net-im/tokodon，一个Mastodon社交网络客户端，加入了KDE Gear。

  * textproc/kdiff3，一个文本差异工具，已更新到版本1.10.1。

新软件：

  * devel/kommit，一个Git客户端，已添加。这是先前包gitklient的重命名。

  * multimedia/kasts是KDE社区的新播客听音应用。

  * textproc/arianna是KDE社区的面向移动设备的电子书阅读器，使阅读FreeBSD文档成为一种愉悦。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**FreeBSD上的GCC**

链接：

GCC项目网址：https://gcc.gnu.org/

GCC 10发布系列网址：https://gcc.gnu.org/gcc-10/

GCC 11发布系列网址：https://gcc.gnu.org/gcc-11/

GCC 12发布系列网址：https://gcc.gnu.org/gcc-12/

GCC 13发布系列网址：https://gcc.gnu.org/gcc-13/

联系人：Lorenzo Salvadore <salvadore@FreeBSD.org>

上游已发布了GCC 13。正如在过去的状态报告中宣布的，我计划尝试从第一个GCC 13发布开始更新GCC_DEFAULT，因此本季度的大部分工作都是为此做准备。

随着GCC 13.1的发布（第一个GCC 13发布：我提醒一下，GCC从1开始计算次要版本发布），在ports树中创建了两个新端口：

  * lang/gcc13，跟踪GCC 13的发布；

  * lang/gcc14-devel，跟踪新的GCC 14上游分支的快照。

**\*-devel端口**

已启用对.init_array和.fini_array的支持。FreeBSD自提交83aa9cc00c2d以来一直支持这两者。

在i386、amd64和aarch64上，将默认的引导选项从LTO_BOOTSTRAP还原为STANDARD_BOOTSTRAP：

  * LTO引导在这些架构上对软件包构建器产生了太多的失败

  * LTO_BOOTSTRAP仍然对希望使用它的用户可用。

这些更改将被传递到生产端口。

**生产端口**

上游发布了GCC 13，为此创建了新的端口lang/gcc13。GCC 11和GCC 12已在上游进行了更新，并计划发布GCC 10的新版本。现在需要更新所有相应的端口。

为了简化端口维护者和用户的工作，我计划一起测试和更新以下所有更改：

  * 更新lang/gcc10，lang/gcc11，lang/gcc12；

  * 将GCC_DEFAULT更新为13；

  * 在生产端口上启用.init_array和.fini_array；

  * 在生产端口上从LTO_BOOTSTRAP切换回STANDARD_BOOTSTRAP。

这将带来以下优势：

  * 通过较少的exp-runs进行更多的测试；

  * 对端口用户进行更少的构建。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Puppet**

链接：

Puppet网址：https://puppet.com/docs/puppet/latest/puppet_index.html

联系人：Puppet团队 <puppet@FreeBSD.org>

Puppet是一款自由软件配置管理工具，由一个信任源（Puppet Server）和描述机器预期配置的领域特定语言组成，以及每个节点上的代理（Puppet Agent），该代理强制执行实际配置与预期配置相匹配。可以设置一个可选的数据库（PuppetDB）用于报告和描述高级模式，其中一台机器的配置取决于另一台机器的配置。

Puppet团队正在维护与Puppet及其相关工具有关的端口。

Puppet 8最近发布，并已添加到ports树中。

Puppet 6已经达到生命周期结束，并已弃用。它现在已经过期。因此，建议Puppet 6的用户更新到Puppet 7或Puppet 8。

目前，对于依赖于Puppet的端口，Puppet 7仍然是默认的Puppet版本。Puppet社区正在努力确保各种Puppet模块与最新的代码一起工作，截至报告撰写时，更新到Puppet 8可能会有一些挑战。情况每天都在变得更好，我们预计在几个月内，当模块更新的浪潮结束时，将切换到Puppet 8作为Puppet的默认版本。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**MITRE Caldera on FreeBSD**

链接：

MITRE Caldera网址：https://caldera.mitre.org/

Red Canary网址：https://www.redcanary.com/


联系人：José Alonso Cárdenas Márquez <acm@FreeBSD.org>

MITRE Caldera是一个网络安全平台，旨在轻松自动化对抗仿真、协助手动红队操作并自动化事件响应。

它基于MITRE ATT&CK®框架，是MITRE的一个活跃研究项目。

MITRE Caldera（security/caldera）于2023年4月添加到ports树中。此端口包括对MITRE Caldera原子插件使用的Atomic Red Team Project的支持。

这项工作的主要目标是增强FreeBSD作为信息安全或网络安全有用平台的可见性。

此外，您可以使用https://github.com/alonsobsd/caldera-makejail或https://github.com/AppJail-makejails/caldera来轻松测试MITRE Caldera基础设施。AppJail是一个用于从命令行管理Jail容器的良好工具。

欢迎有兴趣帮助该项目的人。

当前版本：4.2.0

待办事项

  * 添加Caldera测试基础设施makejail。

  * 将FreeBSD添加到MITRE Caldera官方支持的平台中，详见https://github.com/mitre/caldera/pull/2752。

  * 将FreeBSD添加到Red Canary官方支持的平台中，详见https://github.com/redcanaryco/atomic-red-team/pull/2450。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**Wazuh在FreeBSD上的支持**

链接：

Wazuh网址：https://www.wazuh.com/

联系人：José Alonso Cárdenas Márquez <acm@FreeBSD.org>

Wazuh是一个用于威胁预防、检测和响应的免费开源平台。它能够保护在本地、虚拟化、容器化和基于云的环境中运行的工作负载。

Wazuh解决方案包括部署到受监视系统的端点安全代理和一个管理服务器，该服务器收集并分析代理收集的数据。Wazuh的功能包括与Elastic Stack和OpenSearch的完全集成，通过它用户可以导航安全警报的搜索引擎和数据可视化工具。

Wazuh在FreeBSD上的移植是由Michael Muenz发起的。他在ports树中首次添加Wazuh的是security/wazuh-agent，时间是2021年9月。在2022年7月，我接管了此端口并开始移植其他Wazuh组件。

目前，所有Wazuh组件都已移植或适应：security/wazuh-manager、security/wazuh-agent、security/wazuh-server、security/wazuh-indexer和security/wazuh-dashboard。

在FreeBSD上，security/wazuh-manager和security/wazuh-agent是从Wazuh源代码编译的。security/wazuh-indexer是一个用于存储代理数据的适应后的textproc/opensearch。security/wazuh-server包含了适用于FreeBSD的配置文件适应。运行时依赖项包括security/wazuh-manager、sysutils/beats8（filebeat）和sysutils/logstash8。security/wazuh-dashboard使用了适应后的textproc/opensearch-dashboards和从wazuh-kibana-app源代码生成的FreeBSD版本的wazuh-kibana-app插件。

这项工作的主要目标是增强FreeBSD作为信息安全或网络安全有用平台的可见性。

此外，您可以使用https://github.com/alonsobsd/wazuh-makejail或https://github.com/AppJail-makejails/wazuh来轻松测试Wazuh单节点基础设施（All-in-one）。AppJail是一个用于从命令行管理Jail容器的良好工具。

欢迎有兴趣帮助该项目的人。

当前版本：4.4.4

待办事项

  * 添加Wazuh集群模式基础设施makejail（进行中）

  * 将FreeBSD添加到Wazuh Inc官方支持的平台中，详见https://github.com/wazuh/wazuh-kibana-app/pull/5413

  * 添加FreeBSD SCA策略（进行中）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**Third Party Projects**

许多项目基于FreeBSD构建，或将FreeBSD组件纳入其项目。由于这些项目可能对广大FreeBSD社区感兴趣，我们有时会在季度报告中包含这些项目提交的简要更新。FreeBSD项目对这些提交中的任何声明的准确性或真实性不做陈述。

**PkgBase.live**

链接：

网站网址：https://alpha.pkgbase.live/

源代码网址：https://codeberg.org/pkgbase


联系人：Mina Galić <freebsd@igalic.co>

PkgBase.live，FreeBSD PkgBase项目的非官方存储库，已重新上线。

作为一个服务，PkgBase.live受到了https://up.bsd.lv/的启发，该网站为STABLE和CURRENT分支提供了freebsd-update(8)。up.bsd.live本身已经进入休息状态，所以重新启动PkgBase.live就更加有理由了。

目前，我们为以下平台提供构建：

  * FreeBSD 13.2-RELEASE

  * FreeBSD 13-STABLE

  * FreeBSD 14-CURRENT

每个平台的架构如下：

  * amd64

  * aarch64

  * armv7

  * i386

您可能会注意到RISCv64目前已经消失。

硬件是在Vultr的一个强大的VPS。运行构建作业和提供软件包的服务器和jails是“自托管”的，这意味着它们已经安装并且通过PkgBase保持最新。

由于我们还没有弄清楚如何在FreeBSD jails中配置Vultr的IPv6，PkgBase.live目前无法通过IPv6访问。如果您有相关经验，请与我们联系！

除了用户和测试人员之外，我们仍然鼓励其他人效仿。

PkgBase的硬件由FreeBSD社区的一名成员赞助。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**Containers and FreeBSD: Pot, Potluck, and Potman**

链接：

Pot在GitHub上的组织网址：https://github.com/bsdpot

联系人：Luca Pizzamiglio (Pot) <pizzamig@FreeBSD.org>

联系人：Bretton Vine (Potluck) <bv@honeyguide.eu>

联系人：Michael Gmelin (Potman) <grembo@FreeBSD.org>


Pot是一个Jail管理工具，还通过Nomad支持编排。

在本季度，发布了Pot 0.15.5，其中包含了一些来自不同贡献者的错误修复和设置属性（即Jail sysctl变量）的功能。它将在2023Q3季度软件包集中提供。

Potluck的目标是成为FreeBSD和Pot的Dockerhub，就像Dockerhub是Linux和Docker的Dockerhub一样：Pot和在许多情况下Nomad使用的Pot风格和完整的容器映像的存储库。

所有Potluck容器都已经重新构建为基于FreeBSD 13.2的映像，并使用Pot signify进行了签名。

已经编写了一份《使用Ansible、Pot和其他工具在FreeBSD上构建虚拟数据中心的初学者指南》，该指南解释了如何使用Ansible playbooks部署基于Pot和Potluck的复杂环境，包括MariaDB、Prometheus、Grafana、nginx、OpenLDAP或Traefik等示例节点以及由Nomad和Consul管理的容器编排。

由pot团队提交的一项改进Nomad安全性的补丁，Nomad是一种支持通过sysutils/nomad-pot-driver支持Pot的调度程序和编排器，已经被上游接受，并将成为Nomad 1.6.0的一部分。

一如既往，欢迎反馈和补丁。

赞助商：Honeyguide Group

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

# FreeBSD 2022 年第三季度 季度报告&#x20;

这里是 2022 年的第三季度报告，包括 24 份报告。这比上一季度略少。

我注意到，在过去，我们的季度报告要多得多：经常超过 30 份，有时甚至超过 40 份。因此，我想鼓励你们所有的人提交报告：报告对于分享你的工作、寻找帮助、让更多的人审视你的变化、让更多的人了解你的工作是非常有用的。有更多的人审查你的修改，让更多的人测试你的软件，让你在需要的时候接触到更多的人。当你需要向所有的 FreeBSD 社区讲述一些事情时，你可以接触到更多的读者。告知所有的 FreeBSD 社区以及其他许多情况。请不要害羞，也不要担心您的母语不是英语，或者您不精通 AsciiDoc 的语法：季刊团队将很乐意帮助您解决任何需要。

另一方面，如果你真的没有什么可报告的，那么也许你想加入下面描述的一个有趣的项目，或者你会从其中的一个项目中得到启发，去做一个新的项目。也许你会受到其中一个项目的启发，去做一些新的事情，从而在未来有一些报道。

我们祝愿大家有一个愉快的阅读体验。

Lorenzo Salvadore，代表状态报告小组。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

本报告的渲染版可在此查阅：

[https://www.freebsd.org/status/report-2022-07-2022-09/](https://www.freebsd.org/status/report-2022-07-2022-09/)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

目录

* FreeBSD 团队报告
  * FreeBSD 核心团队
  * FreeBSD 基金会
  * FreeBSD 发布工程团队
  * 集群管理团队
  * 持续集成
  * ports
* 项目
  * OpenStack 与 FreeBSD
  * 作为一级云计算平台的 FreeBSD
* 用户空间
  * bhyve 调试服务器的改进
  * 重写 pjdfstest
  * 正在进行的 LLDB 多进程调试支持工作
  * DTrace：指令级动态跟踪
* 内核
  * ENA FreeBSD 驱动程序更新
  * wtap(4) 增强
  * 英特尔无线走向 11ac
  * 更多的无线更新
  * 使用日志式软更新在文件系统上启用快照
* 架构
  * FreeBSD/Firecracker
* 文档
  * 文档工程团队
* ports
  * Calendar-data: 增加了许可证
  * KDE 与 FreeBSD
  * GCC 有新的维护者，GCC 12.2 和更多
  * sysutils/lsof 重大升级
* 第三方项目
  * 容器和 FreeBSD：Pot, Potluck 和 Potman

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### FreeBSD 团队报告

来自各个官方和半官方团队的条目，可以在[管理](https://www.freebsd.org/administration/)页面找到。

#### FreeBSD 核心团队

联系：FreeBSD 核心团队 [core@FreeBSD.org](mailto:core@FreeBSD.org)

FreeBSD 核心团队是 FreeBSD 的管理机构。

**已完成的项目**

**新的核心团队秘书**

核心小组的所有成员公开表示感谢 Muhammad Moinur Rahman (bofh) 在过去两年中担任核心小组的秘书。

核心小组批准 Sergio Carlavilla（carlavilla）为新的核心小组秘书。

**处理 GDPR 删除请求的程序**

在基金会律师的帮助下，核心小组已经审查了处理 GDPR 删除请求的程序。该文件目前正在撰写中，将会在完成后公布。

**新的隐私政策**

核心团队正在与 FreeBSD 基金会紧密合作，以更新隐私政策，使之与当前的法律和类似网站的做法保持一致，例如我们的网站。

**Bruce Evans 纪念牌**

核心团队经投票一致同意为 Bruce Evans 设立纪念牌，提及他是 FreeBSD 的联合创始人。

**EuroBSDCon 核心团队办公时间**

9 月 1 6 日星期五，新的核心团队在 EuroBSDcon 2022 开发者峰会上发表了演讲。核心团队做了自我介绍，并谈了一下他们这一届的计划。与会人员对细节进行了讨论、问答和建议。

**Commit 权限**

核心小组批准了重启 Konrad Witaszczyk（def@）的源代码提交权限。现在 Konrad 在剑桥大学工作，负责开发 CheriBSD。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### FreeBSD 基金会

链接：

FreeBSD 基金会的网址: https://www.FreeBSDFoundation.org

技术路线图网址: https://FreeBSDFoundation.org/blog/technology-roadmap/

捐赠网址: https://www.FreeBSDFoundation.org/donate/

基金会合作伙伴计划网址: https://www.FreeBSDFoundation.org/

FreeBSD——基金会-合作伙伴关系-计划：[https://www.FreeBSDFoundation.org/FreeBSD-foundation-partnership-program](https://www.freebsdfoundation.org/FreeBSD-foundation-partnership-program)

FreeBSD 杂志网址: https://www.FreeBSDFoundation.org/journal/

基金会新闻和活动网址: https://www.FreeBSDFoundation.org/

联系：Deb Goodkin [deb@FreeBSDFoundation.org](mailto:deb@FreeBSDFoundation.org)

FreeBSD 基金会是符合 501(c)(3) 的非盈利组织，致力于支持和推广 FreeBSD 项目和全球社区。来自个人和企业的捐款被用来资助和管理软件开发项目、会议和开发者峰会。我们还为 FreeBSD 贡献者提供旅行补助，购买和支持硬件以改善和维护 FreeBSD 基础设施，并提供资源以改善安全、质量保证和发布工程工作。我们出版营销材料来推广、教育和宣传 FreeBSD 项目，促进商业供应商和 FreeBSD 开发者之间的合作，最后，在执行合同、许可协议和其他需要一个公认的法律实体的法律安排时代表 FreeBSD 项目。

**筹款工作**

首先，我想向所有为我们的工作提供资金捐助的人表示衷心的感谢。我们的资金 100% 来自于你们的捐款，所以每一笔捐款都可以帮助我们继续在许多方面支持 FreeBSD，包括在这份状况报告中资助和发表的一些工作。

我们主要在五个方面支持 FreeBSD：软件开发是我们资助的最大领域，通过员工开发人员和承包商来实现新的功能，支持一级平台，审查补丁，并修复问题。您可以在这份报告中了解到我们在操作系统改进方面所做的一些工作。宣传 FreeBSD 是我们支持的另一个领域，通过会议、网上和现场的演讲，以及教程和操作指南来传播 FreeBSD 的信息。我们购买并支持用于支持该项目工作的 FreeBSD 基础设施的硬件。基金会组织的虚拟和现场活动帮助联系和吸引社区成员分享他们的知识并进行项目合作。最后，我们在需要时为项目提供法律支持并保护 FreeBSD 的商标。

我们今年的目标是为 200 万美元左右的支出预算筹集至少 140 万美元。当我们进入 2022 年的最后一个季度时，我们的捐款总额为 167,348 美元，所以我们仍然需要您的帮助。如果你今年还没有捐款，请考虑 https://freebsdfoundation.org/donate/。我们还有一个针对大型商业捐助者的合作伙伴计划。你可以在https://freebsdfoundation.org/our-donors/freebsd-foundation-partnership-program/ 找到更多信息。

**系统改进**

在 2022 年的第三季度，有 300 个 src，36 个 port，和 13 个 doc 树的提交将 FreeBSD 基金会列为赞助商。其中一些工作有专门的报告条目。

* 作为一级云计算平台的 FreeBSD
* 对英特尔 11ac 的无线支持
* LLDB 多进程调试支持
* FreeBSD 上的 OpenStack
* 使用日志式软更新的文件系统上的快照

其他赞助的工作是很难简明扼要地总结的。它从复杂的新功能到跨越 src 源代码的各种 bug 修复都不相同。以下是一个小样本，可以让大家了解上一季度的工作。

* 240afd8 makefs: 增加对 ZFS 的支持

这允许人们采用一个阶段性的目录树，并创建一个由 ZFS 池组成的文件，其中有一个或多个数据集，包含目录树的内容。这对于创建虚拟机镜像非常有用，而不需要使用内核来创建池；“zpool create”需要 root 权限，目前在 jail 中禁用。makefs -t zfs 还通过使用固定的种子来生成伪随机数，提供可重复的镜像，用于生成 GUID 和加盐哈希。

* 36f1526 在 arm64 上增加实验性的 16k 页面支持

在 arm64 上添加了初始的 16k 页面支持。它被认为是实验性的，不能保证与用户空间或以当前 4k 页大小构建的内核模块兼容。测试表明，在内核工作负载中取得了良好的效果，这些工作负载包括分配和释放大量的内存，因为在最好的情况下，只需要调用虚拟机子系统的四分之一。

* 1424f65 vm\_pager: 删除默认的页表

它现在没有被使用。保留了 OBJ\_DEFAULT 标识符，但将其作为　 OBJT\_SWAP 的别名，以方便树外代码的使用。

* a889a65 eventtimer：修复定时器重载代码中的几个 race

在 handleevents() 中，在获取下一个事件的时间之前锁定定时器状态。一个并发的 callout\_cc\_add() 调用可能正在改变下一个偶数时间，而竞赛可能导致 handleevents() 编程一个过时的时间。导致 callout 运行得更晚（不受限制的时间，最多到闲置的硬时钟周期为 1s）比要求的时间晚。

**Bhyve 问题支持**

基金会与 John Baldwin 签订了合同，以便在出现问题时为 Bhyve 奉献时间，特别是安全问题。以下是他在该合同中对 2022q3 年的工作总结：

* bb31aee bhyve virtio-scsi: 避免对访客请求的越界访问。
* 62806a7 bhyve virtio-scsi: 整理警告和调试打印文件。
* 7afe342 bhyve e1000: 净化传输环索引。
* c94f30e bhyve: 验证用于映射穿透式 BAR 的主机 PA。
* 16bedf5 pci: 添加辅助程序以遍历设备的 BAR。
* baf753c bhyve: 支持其他命名直通设备的方案。
* fa46f37 bhyve e1000: 跳过有小头的数据包。
* e7439f6 bhyve xhci: 在初始化端点时缓存 MaxPStreams 的值。

**RISC-V 的改进**

在本季度末，基金会与 Mitchell Horne 签订了合同，增加和改进对 RISC-V 硬件的支持。Mitchell 还将进行一般的维护工作，如修复错误，处理报告，为新的代码修改提供审查，以及改善源代码的可读性和文档。

**持续集成和质量保障**

基金会提供了一名全职工作人员，并资助了一些项目，以改善持续集成、自动测试以及 FreeBSD 项目的整体质量保障工作。您可以在专门的条目中阅读本季度的 CI 活动。

**FreeBSD 推广与教育**

我们的大部分工作是致力于项目的宣传。这可能涉及到突出有趣的 FreeBSD 工作，制作文献和视频教程，参加活动，或做演讲。我们制作文献的目的是教给人们 FreeBSD 的基本知识，并帮助他们在采用或贡献的道路上更加容易。除了参加活动和发表演讲之外，我们还鼓励和帮助社区成员举办他们自己的 FreeBSD 活动，发表演讲，或者担任 FreeBSD 的工作人员。

FreeBSD 基金会在全球范围内赞助了许多会议、活动和峰会。这些活动可以是与 BSD 相关的，也可以是开源的，或者是面向未被代表的群体的技术活动。我们支持以 FreeBSD 为中心的活动，以帮助提供一个分享知识的场所，在项目上一起工作，并促进开发者和商业用户之间的合作。这都有助于提供一个健康的生态系统。我们支持非 FreeBSD 的活动，以促进和提高对 FreeBSD 的认识，增加 FreeBSD 在不同应用中的使用，并招募更多的贡献者加入该计划。我们将继续参加个人和虚拟的活动，并计划 11 月的供应商峰会。除了参加和策划虚拟活动之外，我们还在不断地开展新的培训活动，并更新我们的指南选择，以方便让更多的人尝试使用 FreeBSD。

请看我们上一季度所做的一些宣传和教育工作：

* 在 7 月 28 日至 30 日于加州洛杉矶举行的 Scale 19x 会议上举办了一个 FreeBSD 研讨会并设立了一个展位。您可以在 SCALE19X 会议报告中了解更多关于我们的参与情况。
* 赞助并出席 7 月 30-31 日在台湾举行的 COSCUP 会议
* 参加了 EuroBSDCon 开发者峰会，赞助并出席了 9 月 15-18 日在奥地利维也纳举行的 EuroBSDcon 2022。
* 赞助并出席了 2022 年 9 月 29-30 日在洛基山举行的“计算机领域女性庆典”。可以在这里找到 Deb 的演讲的幻灯片。
* 发布 FreeBSD 基金会 2022 年夏季更新
* 继续以管理员和导师的身份参与 Google Summer of Code。在这里可以看到对一些 Google Summer of Code 学生的采访。
* 介绍了一个新的 FreeBSD 资源页面，可以按主题类型、内容类型和难度进行搜索。
* 新的博客文章：
  * 特邀文章：科研中的 FreeBSD
  * 为 2022 年及以后的 FreeBSD 做宣传
  * 八月基金会筹款更新
  * 在 Linux 和 FreeBSD 之间共享双许可证的驱动程序
* 新的和更新的操作指南和快速指南：
  * FreeBSD 快速指南: 在 FreeBSD 上播放视频
  * FreeBSD 上的二进制包管理

我们通过出版专业的 FreeBSD 杂志来帮助大家了解 FreeBSD。正如我们之前提到的，FreeBSD 杂志现在是一份免费出版物。了解更多信息并访问最新的期刊：https://www.FreeBSDfoundation.org/journal/。

你可以在 https://www.FreeBSDfoundation.org/news-and-events/ 找到更多关于我们参加的活动和即将举行的活动。

**法律/FreeBSD 知识产权**

基金会拥有 FreeBSD 的商标，保护这些商标是我们的责任。我们还为核心团队提供法律支持，以调查出现的问题。

前往 https://www.FreeBSDFoundation.org 了解更多关于我们如何支持 FreeBSD 以及我们如何帮助您的信息!

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### FreeBSD 发布工程团队

链接：

FreeBSD 12.4-RELEASE 计划表链接: https://www.freebsd.org/releases/12.4R/schedule/

FreeBSD 13.2-RELEASE 计划表链接: https://www.freebsd.org/releases/13.2R/schedule/

FreeBSD 14.0-RELEASE 计划表链接: https://www.freebsd.org/releases/14.0R/schedule/

FreeBSD development 计划表链接: https://download.freebsd.org/snapshots/ISO-IMAGES/

联系：FreeBSD 发布工程团队, [re@FreeBSD.org](mailto:re@FreeBSD.org)

FreeBSD 发布工程团队负责制定和发布 FreeBSD 官方项目版本的发布时间表，宣布代码冻结并维护相应的分支，以及其他一些工作。

在 2022 年的第三季度，发布工程小组继续为 main、 stable/13 和 stable/12 分支提供每周的开发快照构建。

此外，即将到来的 12.4、13.2 和 14.0 发布周期的时间表也在项目网站上公布。

赞助商：Rubicon Communications, LLC (“Netgate”) 赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 集群管理团队

链接：

集群管理团队成员链接： https://www.freebsd.org/administration/#t-clusteradm

联系：集群管理团队 [clusteradm@FreeBSD.org](mailto:clusteradm@FreeBSD.org)

FreeBSD 集群管理团队的成员负责管理该项目所依赖的机器，以同步其分布式工作和通信。在本季度，该团队进行了以下工作：

* 为 CI 系统增加了额外的存储空间。这将有助于存储更多的工件。
* 在所有官方镜像中部署了 VuXML。它加快了 pkg 的审计功能。
* 一个新的（和额外的）监控系统已经到位。
* 一些旧的和有问题的机器已经退役。
* 将几个服务移到了较新的硬件上。
* 定期进行集群范围内的软件升级
* 定期支持 FreeBSD.org 用户账户
* 对所有物理主机和镜像机进行定期的磁盘和部件支持（和更换）。

正在进行的工作。

* git infra: 增加 `--filter` 支持。
* 与 PowerPC 团队合作，改进软件包构建者、通用和参考机器。
* 在我们的主站点进行站点审计：清点备件和其他占用我们机柜空间的杂物。
* 与 Juniper 讨论为我们的主站点捐赠新的交换机的问题。
* 计划在我们的主站点进行大规模的网络升级。
* 集群更新（更多的扩展项目）。截至 2022-09-30，大多数集群机器都在运行 FreeBSD 13-STABLE 或 14-CURRENT。只有少数机器还在使用 FreeBSD 12-STABLE。

我们正在欧洲寻找一个额外的全镜像站点（五台服务器）。请看适合我们需求的通用镜像布局。我们也欢迎提供额外的单服务器镜像，特别是在欧洲。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 持续集成

链接：

FreeBSD Jenkins Instance 网址: https://ci.FreeBSD.org

FreeBSD CI artifact archive 网址: https://artifact.ci.FreeBSD.org

FreeBSD Jenkins wiki 网址: https://wiki.freebsd.org/Jenkins

Hosted CI wiki 网址: https://wiki.freebsd.org/HostedCI

3rd Party Software CI 网址: https://wiki.freebsd.org/3rdPartySoftwareCI

Tickets related to freebsd-testing@ 网址: https://preview.tiny网址.com/y9maauwg

FreeBSD CI Repository 网址: https://github.com/freebsd/freebsd-ci

dev-ci Mailing List 网址: https://lists.freebsd.org/subscription/dev-ci

联系：Jenkins Admin [jenkins-admin@FreeBSD.org](mailto:jenkins-admin@FreeBSD.org)

联系：Li-Wen Hsu [lwhsu@FreeBSD.org](mailto:lwhsu@FreeBSD.org)

联系：freebsd-testing Mailing List

联系：IRC #freebsd-ci channel on EFNet

FreeBSD CI 团队负责维护 FreeBSD 项目的持续集成系统。CI 系统检查提交的修改是否能够成功构建，然后对新构建的结果进行各种测试和分析。这些构建的工件被归档到工件服务器中，以备进一步测试和调试的需要。CI 团队成员检查失败的构建和不稳定的测试，并与该领域的专家合作，修复代码或调整测试基础设施。

在 2022 年第三季度，我们继续与项目中的贡献者和开发者合作，以满足他们的测试需求，同时也继续与外部项目和公司合作，改进他们的产品和 FreeBSD。

重要的已完成任务:

* 扩大工件存储空间，以增加更多类型的工件和更长的保留期。
* 在 EuroBSDcon 2022 开发者峰会上展示测试/CI 状态更新
* 增加 main-powerpc-images 和 main-powerpcspe-images

正在进行的工作任务：

* 设计并实施预提交的 CI 构建和测试（以支持工作流工作组）
* 设计和实现使用 CI 集群来构建发布工件，就像发布工程那样
* 测试和合并 FreeBSD-ci repo 中的拉动请求
* 为贡献者和开发者简化 CI/测试环境的设置
* 设置 CI 阶段环境，并将实验性工作放在上面
* 整理 freebsd-ci 代码库中的脚本，为合并到 src 代码库做准备
* 更新 wiki 上的文档

已有或等待执行的任务：

* 收集和整理 CI 任务和想法
* 为运行测试的虚拟客体设置公共网络接入
* 实现使用裸机硬件来运行测试套件
* 添加 drm port，并针对 -CURRENT 编译测试
* 计划运行 ztest 测试
* 增加更多外部工具链相关的工作
* 提 - 高硬件实验室的成熟度，增加更多测试用的硬件
* 帮助更多的软件在其 CI 管道中获得 FreeBSD 支持 (Wiki 页面: 3rdPartySoftwareCI, HostedCI)
* 与托管 CI 供应商合作以获得更好的 FreeBSD 支持

请参阅 freebsd-testing@ 相关信息以了解更多的 WIP 信息，不要犹豫，加入我们一起努力吧!

赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### Ports

链接：

About FreeBSD Ports 网址:https://www.FreeBSD.org/ports/

Contributing to Ports 网址: https://docs.freebsd.org/en/articles/contributing/#ports-contributing

FreeBSD Ports Monitoring 网址: http://portsmon.freebsd.org/

Ports Management Team 网址: https://www.freebsd.org/portmgr/

Ports Tarball 网址: http://ftp.freebsd.org/pub/FreeBSD/ports/ports/

联系：René Ladan [portmgr-secretary@FreeBSD.org](mailto:portmgr-secretary@FreeBSD.org)

联系：FreeBSD Ports Management Team [portmgr@FreeBSD.org](mailto:portmgr@FreeBSD.org)

ports 管理团队负责监督 ports 的整体方向、建筑配套和人事事务。下面是上一季度的情况。

目前，在 Ports 中有超过 30,500 个 port。目前有不到 2,800 个开放的 port PR，其中 750 个是未分配的。上一季度，主分支上有 151 个提交者提交了 9,137 份代码，2022Q3 分支上有 61 个提交者提交了 589 份代码。与两个季度前相比，这意味着 port 的数量略有增加，但也意味着（未分配的）port PR 的数量略有增加，提交的数量略有减少。

在上一季度，我们欢迎 Felix Palmen (zirias@) 成为新的 ports committer，欢迎 Akinori MUSHA (knu@) 回来，并向 Olli Hauer (ohauer@) 道别。我们还欢迎 Luca Pizzamiglio (pizzamig@) 成为 portmgr 的正式成员。

在上个季度中，对 Ports 树进行了一些大的修改。

从每个 Makefile 的顶部删除了“Created by” 一行，因为其中很多都已经过时了。

WWW: 已经从每个 pkg-descr 中移到了每个 Makefile 中作为一个变量； 以下是 Stefan Eßer (se@) 所写的，他做了这项工作。

对一个 port 功能的描述，应以提供进一步信息的网页的 网址 结束，例如使用或配置的最佳实践。这些信息可以用 pkg query -e 来显示已安装的包，或 pkg rquery -e 来显示可用的包。网址 曾经被附加到 ports 的 pkg-descr 文件的末尾，并以“WWW:”为前缀，这样工具就可以从描述中提取 网址。随着时间的推移，许多这样的 网址 都变得过时了，因为 port 的更新通常只修改 Makefile，而不是 pkg-descr 文件。通过将这些 网址 的定义移到 Makefile 中，维护者更有可能将 网址 与其它的 port 变更一起更新，而工具也能更容易地访问它们。现在，网址 被分配给 Makefile 中的 WWW 宏，并可以通过 port 目录中的 make -V WWW 进行查询。处理软件包文件中的描述的工具仍然能够工作，因为最后的“WWW:”行是由 Makefile 中的 WWW 值生成的。

在 EuroBSDCon 期间，portmgr@ 对改善内核模块包的情况进行了讨论。讨论了各种可能性。

以下是发生在幕后的情况：

* 一个新的 USES，“vala”，被添加进来。
* Go 的默认版本被提升到了 1.19。
* CMake 现在是一个元 port
* 增加了对 Qt 6 的初步支持，版本为 6.3.2
* Vim 不再在系统中安装 vimrc 了。
* 一些主要的 ports 得到了更新：
  * pkg 1.18.4
  * Chromium 106.0.5249.91
  * Firefox 105.0.1
  * 火狐长期支持版本 102.3.0
  * KDE 应用程序 22.8.1
  * KDE 框架 5.98
  * Rust 1.63.0
  * SDL 2.24.0
  * Xorg 服务器 21.1.4 (大修)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 项目

跨越多个类别的项目，从内核和用户空间到 Ports 或外部项目。

#### FreeBSD 上的 OpenStack

链接：

OpenStack 网址: https://www.openstack.org/

OpenStack on FreeBSD 网址: https://github.com/openstack-on-freebsd

联系：Chih-Hsin Chang [starbops@hey.com](mailto:starbops@hey.com) 联系：Li-Wen Hsu [lwhsu@FreeBSD.org](mailto:lwhsu@FreeBSD.org)

OpenStack 是一个开源的云操作系统，适用于不同类型的资源，如虚拟机和裸机。用户可以在这个开放的云平台上催生 FreeBSD 实例，但目前还不能在 FreeBSD 主机上运行 OpenStack 控制面板。这个项目的目标是移植 OpenStack 的关键组件，使 FreeBSD 能够作为 OpenStack 主机运行。

学术界和工业界的研究小组从 2022 年中期开始对支持 CHERI 的 Morello 板进行了评估。像 OpenStack 这样的资源协调平台可以提高配置、管理和回收这些板子的速度和成本。

从 2022 年 1 月开始，Chih-Hsin Chang 一直在努力将几个 OpenStack 组件移植到 FreeBSD 上运行，包括：

* Keystone（身份服务）
* Glance (图像服务)
* Placement (资源跟踪和库存服务)
* Neutron (网络服务)
* Nova (计算服务)

其中一些项目仍在大力开发中。例如，由于 Neutron 的设计，DHCP 服务器被放在 Linux 网络命名空间内。有必要在 FreeBSD 上找到一个替代品，例如 vnet，并对其进行调整。大多数情况下，移植的策略是通过绕过障碍物来尽可能地减少影响。但是像 oslo.privsep 这样的东西值得进行真正的移植。oslo.privsep 根植于 Linux 的能力，可以进行权限分离工作。现在我们只是在 oslo.privsep 中绕过了任何与 Linux 功能相关的操作。所以目前在源代码和配置中存在大量的 hack 行为。所有这些连同编译和安装步骤将被收集在项目库中。

在第四季度，Chih-Hsin 计划专注于移植 Neutron 和 Nova，以完成虚拟机的生命周期操作。亮点包括：

* DHCP 集成
* FreeBSD 桥接驱动/代理
* Bhyve + Libvirt 集成
* 赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 作为一级云计算平台的 FreeBSD

链接：

cloud-init Website 网址: https://cloud-init.io/

cloud-init Documentation 网址: https://cloudinit.readthedocs.io/en/latest/

cloud-init ongoing refactorization 网址: link:https://github.com/canonical/cloud-init/blob/main/WIP-ONGOING-REFACTORIZATION.rst

联系：Mina Galić [me+FreeBSD@igalic.co](mailto:me+FreeBSD@igalic.co)

cloud-init 是在云中配置服务器的标准方式。不幸的是，对 Linux 以外的操作系统的云计算支持相当差，而 FreeBSD 缺乏对云计算的支持，这对那些希望提供 FreeBSD 作为一级平台的云计算供应商来说是一个障碍。为了补救这种情况，这个项目旨在使 FreeBSD 的云端启动支持与 Linux 的支持相提并论。更广泛的计划是提升对所有 BSD 的支持。

这个项目的成果包括完成对某些网络类的提取，实现 ifconfig(8) 和 login.conf(5) 解析器，实现 IPv6 配置，为 Azure 创建 devd.conf(5) 规则，以及 FreeBSD Handbook 关于生产 FreeBSD 的文档。

在这个过程中，任何在模块和文档中发现的与 BSD 相关的错误也将被修复。

有兴趣帮助这个项目的人可以通过 net/cloud-init-devel 来帮助测试新的功能和修复，这个项目将每周更新一次。此外，我们也非常欢迎能够使用 OpenBSD 和 NetBSD 并有相关经验的人提供帮助。

赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 用户空间

影响基本系统和其中程序的变化。

**bhyve 调试服务器的增强**

链接：

链接：Wiki project page

链接：Differential

联系：Bojan Novković [bojan.novkovic@kset.org](mailto:bojan.novkovic@kset.org)

这个项目的目标是增强 bhyve 的调试服务器的功能。现有的几个与单步走有关的功能与英特尔特定的虚拟机机制有关，这严重损害了 bhyve 在其他 x86 平台上的调试功能。第一个目标是将单步支持扩展到 AMD 主机上。第二个目标是使用客户操作系统的硬件调试寄存器增加对硬件观察点的支持。

该项目是在谷歌的夏季代码计划下进行的，大约在 7 月底完成。这个项目的维基还包含了关于几个已实现机制的详细文档。

这些变化可以总结为以下几点：

* 支持在 AMD 平台的虚拟机内放置软件断点。
* 支持在 AMD 平台上对虚拟机进行单步操作。
* 支持在英特尔和 AMD 平台的虚拟机中放置硬件观察点。

欢迎任何反馈、评论和讨论，我们将不胜感激。

赞助商：谷歌代码之夏

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**重写 pjdfstest**

链接：

Github 网址: https://github.com/musikid/pjdfstest

Blog 网址: https://musikid.github.io/blog/rewrite-pjdfstest/

联系：Alan Somers [asomers@FreeBSD.org](mailto:asomers@FreeBSD.org)

早在 2007 年，Pawel Jakub Dawidek [pjd@FreeBSD.org](mailto:pjd@FreeBSD.org) 编写了 pjdfstest，一个 POSIX 文件系统的一致性测试工具。他最初写这个工具是为了验证 ZFS 对 FreeBSD 的移植，但后来它也被用于其他文件系统和其他操作系统。

今年，Sayafdine Said [musikid@outlook.com](mailto:musikid@outlook.com)在 Google 的赞助下重写了它。新版本有几个改进：

* 可配置性增强，以便更好地与其他文件系统一起使用。
* 速度更快，主要得益于上述可配置性。
* 更好的测试案例隔离，使故障易于调试。
* 所有测试用例不再需要 root 权限。
* 测试用例可以在调试器中运行。
* 可维护性增强，减少重复操作。

仍有几个悬而未决的 PR 需要完成，但我们希望能把这些工作做完，并很快把 pjdfstest 加入到 ports 中。在那里，它将被 /usr/tests 用于 ZFS 和 UFS，以及被外部开发者用于其他文件系统。

赞助商：谷歌代码之夏

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**正在进行的关于 LLDB 多进程调试支持的工作**

链接：

Moritz Systems Project Description 网址: https://www.moritz.systems/blog/multiprocess-support-for-lldb/

Progress Report 1 网址: https://www.moritz.systems/blog/implementing-non-stop-protocol-compatibility-in-lldb/

Progress Report 2 网址: https://www.moritz.systems/blog/full-multiprocess-support-in-lldb-server/

联系：Kamil Rytarowski [kamil@moritz.systems](mailto:kamil@moritz.systems)

联系：Michał Górny [mgorny@moritz.systems](mailto:mgorny@moritz.systems)

根据上游的描述，“LLDB 是下一代高性能调试器。它是作为一组可重用的组件构建的，这些组件高度利用了更大的 LLVM 项目中的现有库，例如 Clang 表达式解析器和 LLVM 反汇编器。”

FreeBSD 在基本系统中包括 LLDB。之前赞助的项目改进了 LLDB，使其成为基础系统中可信的调试器，尽管它与 GNU GDB 的当代版本相比仍有一些限制。这个项目于 2022 年 4 月开始。它的目标是实现对多个进程同时调试的全面支持。

在项目开始时，LLDB 对多进程调试的支持非常有限。目前，服务器已经能够使用 GDB 远程串行协议的多进程扩展来监控多个进程。为该协议实现客户端对应的工作正在进行。

一旦该项目完成，LLDB 将能够同时跟踪任意数量的分叉进程（相当于 GDB 的 detach-on-fork off）。

赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**DTrace：指令级动态跟踪**

链接：

Wiki article 网址: https://wiki.freebsd.org/SummerOfCode2022Projects/InstructionLevelDynamicTracing

Final code review 网址: https://reviews.freebsd.org/D36851

联系：Christos Margiolis [christos@FreeBSD.org](mailto:christos@FreeBSD.org)

联系：Mark Johnston [markj@FreeBSD.org](mailto:markj@FreeBSD.org)

kinst 是一个新的 DTrace 提供者，允许任意的内核指令追踪。

该提供程序目前只针对 amd64 实现，但我们计划在未来将其移植到其他架构上。

kinst 探针是由 libdtrace 按需创建的，几乎可以为内核中的每一条指令创建探针。探针的形式如下：

```shell-session
kinst:<module>:<function>:<offset>
```

其中 `module` 是包含指定函数的内核模块，`function`是要追踪的内核函数，`offset` 是特定指令的偏移量。省略 `offset` 会使函数中的所有指令都被追踪。省略 `module` 会导致 DTrace 搜索该函数的所有内核模块。

例如，要追踪 amd64\_syscall() 中的第二条指令，首先确定第二条指令的偏移量：

```shell-session
# kgdb
(kgdb) disas /r amd64_syscall
Dump of assembler code for function amd64_syscall:
   0xffffffff809256c0 <+0>:     55      push   %rbp
   0xffffffff809256c1 <+1>:     48 89 e5        mov    %rsp,%rbp
   0xffffffff809256c4 <+4>:     41 57   push   %r15
```

偏移量为 1。然后，要追踪它：

```shell-session
# dtrace -n 'kinst::amd64_syscall:1'
```

D 语言中还增加了一个新的关键字 `regs`，提供了对探针启动时的 CPU 寄存器的只读访问。例如，当 kinst::amd64\_syscall:1 探针启动时，追踪帧指针的内容（amd64 上的寄存器 %rbp）:

```shell-session
# dtrace -n 'kinst::amd64_syscall:1 {printf("0x%x", regs[R_RBP]);}'
```

kinst 的工作方式与 FBT（函数边界跟踪）提供者类似，它在目标指令上放置一个断点，并钩住内核的断点处理程序。它比 FBT 更强大，因为它可以用来在一个函数中的任意点上创建探针，而不是在函数边界。因为 kinst 必须能够追踪任意指令，所以它没有在软件中模拟大多数指令，而是使被追踪的线程在返回到原始代码之前执行一个指令的副本。

计划中的未来工作包括将 kinst 移植到更多的平台上，特别是 arm64 和 riscv，以及开发可以使用 kinst 追踪使用内核调试符号的内联函数调用的工具。

赞助商：谷歌公司（GSOC 2022）。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**内核**

内核子系统/功能、驱动支持、文件系统等方面的更新。

**ENA FreeBSD 驱动程序更新**

链接：

ENA README 网址: https://github.com/amzn/amzn-drivers/blob/master/kernel/fbsd/ena/README.rst

联系：Michal Krawczyk [mk@semihalf.com](mailto:mk@semihalf.com)

联系：David Arinzon [darinzon@amazon.com](mailto:darinzon@amazon.com)

联系：Marcin Wojtas [mw@FreeBSD.org](mailto:mw@FreeBSD.org)

ENA（弹性网络适配器）是亚马逊网络服务（AWS）的虚拟化环境中可用的智能网卡。ENA 驱动程序支持多个发送和接收队列，可以处理高达 100Gb/s 的网络流量，这取决于它所使用的实例类型。

自上次更新以来已完成：

* ENA 驱动 v2.6.0 和 v2.6.1 的上游，包括。
* 修复了第 6 代实例重置后的性能下降问题。
* 修复了启用 KASSERT 时的错误网图断言。
* 代码清理和风格修正。
* 记录的改进。
* 修复了 ENI 指标的检索问题。

赞助商：Amazon.com Inc

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**wtap(4) 增强**

链接：

Add sta, hostap and adhoc mode to wtap wlan simulator

联系：En-Wei Wu [enweiwu@FreeBSD.org](mailto:enweiwu@FreeBSD.org)

联系：Li-Wen Hsu [lwhsu@FreeBSD.org](mailto:lwhsu@FreeBSD.org)

联系：Bjoern A. Zeeb [bz@FreeBSD.org](mailto:bz@FreeBSD.org)

wtap(4) 是 Monthadar Al Jaberi [monthadar@gmail.com](mailto:monthadar@gmail.com) 和 Adrian Chadd [adrian@FreeBSD.org](mailto:adrian@FreeBSD.org) 在 2012 年推出的一个 net80211(4)Wi-Fi 模拟器。它最初支持 802.11s 网状模式，并被用于验证。在 2022 年谷歌代码之夏期间，En-Wei 一直致力于为它带来 sta、hostap、adhoc 和监控模式。这项工作还包括用 atf(7) 编写的 wtap(4) 为 net80211(4) 添加基本测试。

更多细节，请查看项目的 wiki 页面。

赞助商：Google Summer of Code 赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**英特尔无线向 11ac 发展**

链接：

Intel iwlwifi status FreeBSD wiki page 网址: https://wiki.freebsd.org/WiFi/Iwlwifi

联系：Bjoern A. Zeeb [bz@FreeBSD.org](mailto:bz@FreeBSD.org)

这个正在进行的项目旨在使用 LinuxKPI 兼容代码和本地 net80211 和内核代码支持 FreeBSD 上最新的 Intel 无线芯片组。此外，在 LinuxKPI 802.11 兼容代码中支持 11n 和 11ac 标准的工作正在进行中，并在本地 net80211 无线堆栈中填补 11ac 的空白。

对于英特尔 iwlwifi 无线驱动程序，在过去几个月中没有重大更新。我们将固件更新到最新的公开可用版本，并修复了一些最明显的错误。支持 D3 节电代码的工作也在进行中。

LinuxKPI 兼容代码也得到了一些改进和修复，这些改进和修复有时只在某些世代的 iwlwifi 芯片组上可以看到。

net80211 和 LinuxKPI 兼容代码对 11n 和 11ac 的改变到目前为止几乎没有公开可见，以避免破坏基本支持。基于较新的 802.11 标准的常量更新和其他没有用户可见效果的变化被合并了，功能上的变化将在未来几个月内跟进，最初隐藏在编译时或运行时选项后面。

为了跟踪这个分支的用户的利益，以及帮助进行更多的测试，改进和更新大部分被合并回 stable/13。

要了解最新的开发状况，请关注 freebsd-wireless 邮件列表和查看 wiki 页面。

赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**更多无线更新**

链接：

Bjoern’s Wireless Work In Progress landing page 网址: https://people.freebsd.org/\~bz/wireless/

Realtek rtw88 status FreeBSD wiki page 网址: https://wiki.freebsd.org/WiFi/Rtw88

Realtek rtw89 status FreeBSD wiki page 网址: https://wiki.freebsd.org/WiFi/Rtw89

MediaTek mt76 status FreeBSD wiki page 网址: https://wiki.freebsd.org/WiFi/Mt76

QCA ath11k status FreeBSD wiki page 网址: https://wiki.freebsd.org/WiFi/Ath11k

联系：Bjoern A. Zeeb [bz@FreeBSD.org](mailto:bz@FreeBSD.org)

目前的发展主要是由英特尔的 iwlwifi 驱动再次推动（见其他报告）。俗话说“互相帮助”，所以 Realtek 的 rtw89 驱动的工作有助于发现困扰 iwlwifi 用户的 LinuxKPI 的错误。在这份状态报告中，主题主要是更多的驱动程序，它们确实需要更多的 LinuxKPI 支持。

各种工作正在进行中：

* Realtek 的 rtw88 PCI 正在进行中，在 EuroBSDCon 上与 Hans Petter Selasky 进行了富有成效的讨论后，rtw88 USB WiFi 加密狗的 LinuxKPI USB 支持工作将继续进行。
* Realtek 的 rtw89 驱动已经提交给 main，但还没有连接到构建中。扫描工作已经开始，但数据包还没有通过。有了这个驱动，就可以为拥有该芯片组的用户提供测试便利，以确定更多未实现的 LinuxKPI 位（其中一些也会帮助其他驱动），并减少我的工作。
* 下一个驱动可能是基于联发科的 mt76 驱动（用于 7921 和 7915），我已经在编译并开始测试。
* 根据要求，我也在开发支持 STA 模式的 ATH11K，因为一些供应商似乎用这些芯片运送笔记本电脑。

虽然其中一些工作显然得益于 FreeBSD 基金会赞助的 iwlwifi 和较新的标准支持，但其中很多只是自由时间的工作。如果你对这些驱动程序中的任何一个感兴趣，我将非常感激，如果有更多的人能够帮助其中的一个或另一个。这可能是定期测试主程序的更新，编写文档和更新 wiki 页面，跟踪 PR，尝试补丁，帮助个别 LinuxKPI 位的工作，无论是否有 802.11 的工作，或者只是调试个别驱动和/或芯片组的问题。如果你有兴趣帮助上述任何一项工作，请给我发邮件。

对于最新的发展状况，请关注 freebsd-wireless 邮件列表并查看 wiki 页面（如果存在）。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**在使用日志式软更新的文件系统上启用快照**

链接：

Milestone 1 Core Changes 网址: https://reviews.freebsd.org/D36491

联系：Kirk McKusick [mckusick@FreeBSD.org](mailto:mckusick@FreeBSD.org)

这个项目将使 UFS/FFS 文件系统的快照在使用日志式软更新运行时可用。

UFS/FFS 文件系统有拍摄快照的能力。因为快照的拍摄是在软更新编写之后加入的，它们与软更新完全集成。当日志式软更新在 2010 年被添加时，它们从未与快照整合。因此，快照不能在运行有日志的软更新的文件系统上使用。

随着 FreeBSD 对 ZFS 的支持，快照变得不那么重要了，因为 ZFS 可以快速而容易地进行快照。然而，在两种情况下，UFS 快照仍然是重要的。第一是它们允许可靠地转储实时文件系统，从而避免了可能的数小时的停机时间。第二种情况是，它们允许运行后台 fsck。类似于 ZFS 中对刷新的需求，fsck 需要定期运行以发现未被发现的磁盘故障。快照允许 fsck 在实时文件系统上运行，而不是需要安排停机时间来运行它。

这个项目有两个目标：

* 在运行日记式软更新时启用快照，并确保它们可以被用于在实时文件系统上进行后台转储。这个目标应该在 2022 年底前完成。
* 扩展 fsck\_ffs，使其能够使用快照对运行有日记软更新的文件系统进行后台检查。这个目标预计将在 2023 年第三季度完成。

赞助：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**架构**

更新特定平台的功能并引入对新硬件平台的支持。

**FreeBSD/Firecracker**

链接：

Firecracker VM

联系：Colin Percival [cperciva@FreeBSD.org](mailto:cperciva@FreeBSD.org)

Firecracker 是由 Amazon Web Services 开发的开源“微型虚拟机”；它是为“无服务器”计算环境的需要而设计的，并特别注重安全和极简主义。

从 2022 年 6 月开始，Colin Percival 一直在努力将 FreeBSD 移植到 Firecracker 环境中运行，并得到了其他 FreeBSD 开发者的大力协助。在这份季度报告中，一组补丁正在等待审查，这些补丁共同增加了所需的支持，使 FreeBSD 能够在 Firecracker 的补丁版本中运行。

在第四季度，Colin 打算完成对 FreeBSD 的相关补丁的提交，发布内核和磁盘镜像，以便其他 FreeBSD 用户可以尝试使用 Firecracker，并更新和合并 Firecracker 的补丁，增加 PVH 启动支持（被 FreeBSD 使用）。

这项工作已经产生了“附带”的好处，揭示了加速 FreeBSD 启动过程的方法；由于其低开销和最小的环境，Firecracker 是进行这项工作的绝佳环境。

这项工作得到了 Colin 的 FreeBSD/EC2 Patreon 的支持。

赞助商：https://www.patreon.com/cperciva

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**文档**

在文档、手册页或新的外部书籍/文档中值得注意的变化。

**文档工程团队**

链接：FreeBSD 文档项目

链接：为新的贡献者提供的 FreeBSD 文 档项目入门手册

链接：文档工程团队

联系：FreeBSD Doceng 团队 [doceng@FreeBSD.org](mailto:doceng@FreeBSD.org)

doceng@ 团队是一个处理与 FreeBSD 文档工程相关的一些元项目问题的机构；更多信息请参见 FreeBSD Doceng 团队章程。

在上个季度：

* 0mp@ 卸任了 Doceng 的秘书，fernape@ 加入成为新的秘书。Doceng 感谢 0mp@ 的服务。
* eadler@ 的文档位在他的要求下被收走保管。
* 为文档库添加了一个 git 提交信息模板。

待定和讨论中的项目：

* 删除网站和文档门户中过时的翻译。

**FreeBSD 的文档项目入门**

* FDP 中增加了关于商标处理的信息。

**port 开发者手册**

* 更新了关于移植 Haskell 程序的文档。
* 记录了将 WWW 从 pkg-descr 移到 Makefile 的过程。
* 在 ports 框架中导入 Qt 6 库之后，增加了与之相关的文档。

**FreeBSD 网站的翻译**

链接：在 Weblate 上翻译 FreeBSD

链接：FreeBSD Weblate 实例

**2022 年第三季度状况**

12 种语言

148 个注册用户

Gasol Wu 加入了中文翻译团队。

Alvaro Felipe Calle 加入了西班牙语翻译团队。

**语种**

* 中文（简体） (zh-cn) (进度: 8%)
* 中文（繁体）（zh-tw）（进度：4%）。
* 荷兰语 (nl) (进展: 1%)
*
  * 法语 (fr) (进展: 1%)
* 德文 (de) (进展: 1%)
* 印度尼西亚语 (id) (进展: 1%)
* 意大利语 (it) (进展: 4%)
* 挪威语 (nb-no) (进展: 1%)
* 波斯语 (fa-ir) (进展: 3%)
* 葡萄牙语 (pt-br) (进展: 16%)
* 西班牙文 (es) (进展: 15%)
* 土耳其语 (tr) (进展: 2%)

我们要感谢每一个作出贡献、翻译或审阅文件的人。

请在您当地的用户群中推广这项工作，我们总是需要更多的志愿者。

**FreeBSD 手册页面门户网站**

联系：Sergio Carlavilla [carlavilla@FreeBSD.org](mailto:carlavilla@FreeBSD.org)

Manual Pages Portal 已经被重新设计为使用 mandoc(1) 进行渲染。门户网站的预览版已经推出。我们已经收集了反馈，并在可能的情况下进行了处理。还有一些剩余的非阻塞问题。Doceng@ 希望继续推进向这个新门户的迁移。

感谢所有审查和提供反馈的人。

**FreeBSD 网站改版——WebApps 工作组**

联系人：Sergio Carlavilla [carlavilla@FreeBSD.org](mailto:carlavilla@FreeBSD.org)

负责创建新的 FreeBSD 文档门户和重新设计 FreeBSD 主网站及其组件的工作小组。FreeBSD 开发者可以在 FreeBSD Slack 频道 #wg-www21 上关注并加入该工作组。这项工作将分为四个阶段。

1. 重新设计文档门户

创建一个新的设计，具有响应性和全局搜索功能。(完成)

1. 重新设计网络上的手册页面

使用 mandoc 生成 HTML 页面的脚本。(完成)

1. 重新设计网络上的“ports”页面

用 ports 脚本来创建一个应用门户。(工作正在进行中)

1. 重新设计 FreeBSD 的主网站

新设计，响应式和暗色主题。(未开始)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### ports

影响 Ports 的变化，无论是涉及大部分的全面变化，还是个别 port 本身。

#### Calendar-data：添加了许可证

链接：

GitHub calendar-data 仓库的 网址: https://github.com/freebsd/calendar-data

联系：Stefan Eßer [se@FreeBSD.org](mailto:se@FreeBSD.org)

联系：Lorenzo Salvadore [salvadore@FreeBSD.org](mailto:salvadore@FreeBSD.org)

联系：Warner Losh [imp@FreeBSD.org](mailto:imp@FreeBSD.org)

port deskutils/calendar-data 包含了 BSD 日历程序的日历文件，由 se@ 维护。这个 ports 的数据存在于 GitHub 仓库，目前主要由 salvadore@ 维护。

大约两年前，基础仓库中的日历文件被从那里删除，并在 GitHub 上创建了一个新的仓库；也可以参见这篇关于创建相关 ports 的 Phabricator 评论。这一改进使得日历文件可以独立于基础系统进行更新。

不幸的是，在创建存储库的时候，忘记了给它添加许可证。这个问题在本季度通过这个由 salvadore@ 提交并由 imp@ 合并的拉动请求得到了解决。由于这些数据最初来自 src 仓库，所以同样的许可证也适用。如果你在过去为日历文件贡献了不同的许可预期，请通知我们，这样我们就可以为你的贡献提供相应的许可，或者删除它们。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### FreeBSD 上 的 KDE

链接：

KDE FreeBSD 网址: https://freebsd.kde.org/

KDE Community FreeBSD 网址: https://community.kde.org/FreeBSD

联系：Adriaan de Groot [kde@FreeBSD.org](mailto:kde@FreeBSD.org)

KDE on FreeBSD 项目将来自 KDE Community 的软件，以及依赖关系和相关软件打包到 FreeBSD ports 上。这些软件包括一个叫做 KDE Plasma 的完整桌面环境（适用于 X11 和 Wayland）和数百个可以在任何 FreeBSD 机器上使用的应用程序。

KDE 团队 (kde@) 是 desktop@ 和 x11@ 的一部分，他们建立了软件堆栈，使 FreeBSD 成为漂亮的、可用于日常驱动的基于图形的桌面机器。下面的说明主要描述的是 KDE 的 ports，但也包括对整个桌面栈很重要的项目。

**Qt6 可用**

KDE ports 中的大新闻并不直接与 KDE 有关。Qt6 已经可用了，它为我们准备好了下一代基于 Qt 的应用程序。

现在可以用 USES=qt:6 来选择新的 Qt 版本。一些 ports 已经进行了调整以使用新的版本。

KDE 本身没有受到影响：针对 Qt6 的 KDE 框架的上游工作还没有完成。大多数 KDE Frameworks 会在 Qt6 上编译，但这对 FreeBSD 的 port 来说并不重要。使用 devel/qt6 可以得到 Qt 6.4.0，在本季度末发布。

**KDE Stack**

KDE Gear 每季度发布一次，KDE Plasma 每月更新一次，KDE Frameworks 每月也有一个新版本。这些（大型）更新在其上游发布后不久就登陆了，并没有单独列出。

* KDE Frameworks 5 现在是 5.98 版本（从 2022 年 9 月开始每月最新发布）。
* KDE Gear 现在是 22.08.1 版（2022 年 9 月的更新）。
* KDE Plasma 现在是 5.24.6 版（2022 年 7 月的更新）。

请注意，KDE Plasma 5.25 已经在上游发布了，但在登陆 ports 之前还在等待修正 (例如，KDE 的 bug 跟踪中的这个 KActivityManager bug)。

**相关的 port**

* accessibility/qt5-speech 现在支持多个后端，以及无后端的语音合成。
* devel/cmake 被重新组织了，因此 devel/cmake 现在是一个安装了 devel/cmake-core 和其余 CMake 套件的 metaport。(感谢 diizzy@) CMake ports 也被更新到了 3.24 版，并在整个树上的 ports 中做了相应的改动。
* net/qt5-network 改善了与 libressl 的兼容性。
* x11/plasma-wayland-protocols 在下一季度的 KDE Plasma 桌面更新之前已经更新。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**GCC：新的维护者，GCC 12.2 等等**

链接：

GCC 项目网址：https://gcc.gnu.org

GCC 11 发布系列的网址：https://gcc.gnu.org/gcc-11/

GCC 12 发布系列的网址：https://gcc.gnu.org/gcc-12/

联系：[toolchain@FreeBSD.org](mailto:toolchain@FreeBSD.org)

联系：Lorenzo Salvadore [salvadore@FreeBSD.org](mailto:salvadore@FreeBSD.org)

* salvadore@ 采用了所有对应于 gcc 支持版本的现有 ports，即：lang/gcc10、lang/gcc11、lang/gcc11-devel、lang/gcc12、lang/gcc12-devel 和 lang/gcc13-devel。目前 -devel port 每周都会更新，除非是编译失败导致无法更新。当然，在后一种情况下，会尽快修复和/或向上游报告构建失败的情况。
* GCC 12.2 已经发布了。传统上，FreeBSD 会等待 GCC 的第二个次要版本的发布，将其作为默认的 GCC 版本，因此大部分需要用 GCC 编译的软件已经被移植到最新的主要版本。因此，将 GCC 默认版本更新为 12 版的工作已经开始。非常感谢已经运行了第一个 exp-run 的 antoine@ 以及所有参与这个过程的贡献者、维护者和提交者。https://bugs.freebsd.org/bugzilla/show\_bug.cgi?id=2659548
* 关于 LTO 的讨论一直在进行，有很多不同的观点。如果有兴趣，你可以阅读该主题的最新贡献：lang/gcc11: Needs build time warning for /tmp consumption 和 lang/gcc11: build gets stuck。提醒一下。LTO\_BOOTSTRAP 是一个默认启用的选项。如果您在自己的机器上联编 port，而它的资源消耗是不可接受的，禁用这个选项会让您得到更轻的编译。
* jbeich@ 提交了一个补丁，以暴露非默认的 -stdlib=libc++ 支持，这个补丁已经成功地提交给所有相关的 port (gcc >= 11)。链接：https://bugs.freebsd.org/bugzilla/show\_bug.cgi?id=265962
* diizzy@ 刷新了 MASTER\_SITE\_GCC 变量中的镜像列表，同时删除了 ftp 镜像。GCC 主站点被用作后备站点。链接: https://reviews.freebsd.org/D36372
* 仍然需要对这三个变化提供帮助，以便与上游的 GCC 一起工作 (需要对 GCC 源码和上游的专业知识，而不是对 ports 框架的专业知识)。
  * upstreaming lang/gcc11/patch-gets-no-more
  * upstreaming lang/gcc11/patch-arm-unwind-cxx-support
  * https://bugs.freebsd.org/bugzilla/show\_bug.cgi?id=256874

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### sysutils/lsof 主要更新

链接：

lsof 项目 repo 网址: https://github.com/lsof-org/lsof

联系：

Larry Rosenman [ler@FreeBSD.org](mailto:ler@FreeBSD.org)

sysutils/lsf 进行了一次重大升级，不再在 `/dev/kmem` 中查找数据，而是使用用户空间的 API。这在源代码上花了很长时间，但终于完成了。自 13.0-RELEASE 以来，它第一次修复了 lsof(8) 与 ZFS 一起工作。

这将使今后的维护工作更加容易。

内核人员：如果你做了破坏 lsof 的改动，请提交 GitHub 拉取请求到 https://github.com/lsof-org/lsof。请测试对 lsof 使用的接口的任何改动，并确保它们仍然工作。现在这些都应该是用户地接口，但请测试。

我感谢 Warner Losh [imp@FreeBSD.org](mailto:imp@FreeBSD.org), Mateusz Guzik [mjg@FreeBSD.org](mailto:mjg@FreeBSD.org), 和 Ed Maste [emaste@FreeBSD.org](mailto:emaste@FreeBSD.org) 帮助我完成这一重大改变。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**第三方项目**

许多项目都建立在 FreeBSD 的基础上，或者将 FreeBSD 的组件纳入他们的项目中。由于这些项目可能会引起更广泛的 FreeBSD 社区的兴趣，我们有时会在季度报告中加入这些项目提交的简短更新。FreeBSD 项目对这些提交的信息的准确性和真实性不做任何陈述。

**容器和 FreeBSD：Pot, Potluck and Potman**

链接：

Pot 组织在 github 上的 网址: https://github.com/bsdpot

联系：Luca Pizzamiglio (Pot) [pizzamig@freebsd.org](mailto:pizzamig@freebsd.org)

联系：Stephan Lichtenauer (Potluck) [sl@honeyguide.eu](mailto:sl@honeyguide.eu)

联系。Michael Gmelin (Potman) [grembo@freebsd.org](mailto:grembo@freebsd.org)

Pot 是一个 jail 管理工具，也支持通过 Nomad 进行协调。

在上一季度，pot 0.15.3 已经发布。它包含了许多改进，比如 mount-out 可以移除或卸载之前 mount-in 的文件夹或文件系统，信号和 exec 命令，更好的 jail 生命周期处理，以及许多 bug 修复。

Nomad 驱动的新版本 nomad-pot-driver 0.9.0 也已经发布，支持信号和 exec，并进行了稳定性修复。

Potluck 的目标是成为 FreeBSD 和 pot，就像 Dockerhub 之于 Linux 和 Docker 一样：一个 pot 风味和完整的容器镜像的存储库，可用于 pot 和许多情况下 Nomad 的使用。

自从上次的状态报告以来，已经提交了许多变化，包括对核心镜像的许多修复和改进，如 grafana、postgresql-patroni 或 loki。此外，所有的镜像都已经针对 FreeBSD 13.1 和 12.3 进行了重建，并包含了当前正在使用的软件包的季度版本。

最后，Luca 在 EuroBSDCon 2022 上举办了 Pot 的实施和生态系统的讲座——一个天真的 FreeBSD 容器实施可以走多远。

一如既往，我们欢迎反馈和补丁。

# FreeBSD 2022 年第二季度 季度状况报告

> 原文地址 [https://www.freebsd.org/status/report-2022-04-2022-06/](https://www.freebsd.org/status/report-2022-04-2022-06/)。

FreeBSD 季度状态报告 2022 年第二季度

这里是 2022 年的第二份季度报告，共包括 26 份报告。

在本季度，季度团队设法更快地发布报告，并希望能减少错误。然而，如果你注意到某些错误，请报告，以便我们能够纠正它们，并在我们的工具中添加自动检查设置，以防止将来出现这些错误，并尽可能对发布过程保持高效率。

我们还想提醒你，如果由于任何原因，你需要更多的时间来提交季度报告，团队将等待你，但请提醒我们，以便我们意识到有些报告仍未提交。

非常感谢所有选择通过季度报告与 FreeBSD 社区分享其工作的人。

Lorenzo Salvadore，代表现状报告小组。



本报告的渲染版可在此查阅： [https://www.freebsd.org/status/report-2022-04-2022-06/](https://www.freebsd.org/status/report-2022-04-2022-06/)



目录

- FreeBSD 团队报告
  - FreeBSD 核心团队
  - FreeBSD 基金会
  - FreeBSD 发布工程团队
  - 集群管理团队
  - 持续集成
  - Ports
- 项目
  - Linux 兼容层更新
  - FreeBSD 与 riscv64
  - 微软 HyperV 和 Azure 上的 FreeBSD
- 用户空间
  - 正在进行的关于 LLDB 多进程调试支持的工作
  - makefs(8) 中的 ZFS 支持
  - 基本系统 OpenSSH 更新
  - pf 的最新状况
- 内核
  - ENA FreeBSD 驱动程序更新
  - 新的蓝牙 ® 配置守护程序：blued
  - OpenVPN DCO
  - 无线更新
  - 共享页地址随机化
- 架构
  - 支持恩智浦 DPAA2
  - 关于 arm64 及其他的中型超级页
- 文件
  - 文档工程团队
- Ports
  - FreeBSD 上的 KDE
  - 其他地方
  - GCC ：更新 GCC_DEFAULT 和其他改进
  - Valgrind - 13.1/14.0 的大量错误修正和更新
  - FreeBSD 上 的 Pantheon 桌面
  - 英特尔的 igt-gpu-tools 的完整功能移植



#### FreeBSD 团队报告

来自各官方和半官方团队的报告，可在[行政页面](https://www.freebsd.org/administration/)找到。

#### FreeBSD 核心团队

联系：FreeBSD 核心团队 [core@FreeBSD.org](mailto:core@FreeBSD.org)

FreeBSD 核心团队是 FreeBSD 的管理机构。

第十二代 FreeBSD 核心团队是由活跃的开发者选举产生的。core.12 的成员是：

- Baptiste Daroussin（bapt, 现任）
- Benedict Reuschling（bcr）
- Ed Maste（emaste, 现任）
- Greg Lehey（grog）
- John Baldwin（jhb）
- Li-Wen Hsu（lwhsu）
- Emmanuel Vadot（manu）
- Tobias C. Berner（tcberner）
- Mateusz Piotrowski（0mp）

6 月 10 日，即将离任的 core.11 和即将上任的 core.12 团队召开了交接会议，新的核心团队于 6 月 18 日宣布成立。

在任命新的核心小组秘书和完成交接任务后，现任核心小组秘书 Muhammad Moinur Rahman (bofh) 将卸任。

在本季度，Kornel Dulęba（kd）和 Dmitry Salychev（dsl）的 src 提交权限已经被批准。



#### FreeBSD 基金会

链接：

FreeBSD 基金会 网址：https://www.FreeBSDFoundation.org

技术路线图 网址：https://FreeBSDFoundation.org/blog/technology-roadmap/

捐赠 网址：https://www.FreeBSDFoundation.org/donate/

基金会合作计划 网址：https://www.FreeBSDFoundation.org/FreeBSD-foundation-partnership-program

FreeBSD 杂志 网址：https://www.FreeBSDFoundation.org/journal/

基金会新闻和活动 网址：https://www.FreeBSDFoundation.org/news-and-events/

联系：Deb Goodkin deb@FreeBSDFoundation.org

FreeBSD 基金会是一个 501(c)(3) 的非营利组织，致力于支持和促进全球的 FreeBSD 项目和社区。捐献来自个人和企业的资金被用来资助和管理软件开发项目、会议和开发者峰会。我们还为 FreeBSD 贡献者提供旅行补助，购买和支持硬件以改善和维护 FreeBSD 的基础设施，并提供资源以改善安全、质量保证和发布工程工作。我们发布营销材料来推广、教育和宣传 FreeBSD 项目，促进商业供应商和 FreeBSD 开发者之间的合作，最后，在执行合同、许可协议和其他需要公认的法律实体的法律安排中代表 FreeBSD 项目。

**筹集资金的努力**

首先，我想向所有为我们的工作提供资金捐助的人表示衷心的感谢。我们的资金 100% 来自于你们的捐款，因此每一笔捐款都可以帮助我们在许多方面继续支持 FreeBSD，包括在这份状况报告中资助和发表的一些工作。

我们今年的目标是为大约 200 万美元的支出预算筹集至少 140 万美元。在我写这份报告的时候，我们为实现这一目标筹集了不到 20 万美元。因此，我们显然需要加紧努力筹款。这是迄今为止我工作中最困难的部分。我更愿意和社区中的人们讨论我们如何帮助你们，帮助创造内容以招募更多的用户和贡献者加入项目，并了解个人和组织在使用 FreeBSD 时遇到的挑战和痛点，以便我们能够帮助改善这些方面。索取金钱并不在此列。

我们在五个主要领域支持 FreeBSD。软件开发是我们资助的最大的领域，我们有六个软件开发人员，他们介入实现新的功能，支持一级平台，审查补丁，并修复问题。你可以在这份报告中了解到我们在操作系统改进方面所做的一些工作。FreeBSD 宣传是我们支持的另一个领域，通过会议、网上和现场的演讲、教程和操作指南来传播 FreeBSD 的信息。我们购买并支持用于支持该项目工作的 FreeBSD 基础设施的硬件。基金会组织的虚拟和现场活动帮助联系和吸引社区成员分享他们的知识并进行项目合作。最后，我们在需要时为项目提供法律支持，并保护 FreeBSD 的商标。

如果你今年还没有捐款，请考虑一下捐款，地址是：[https://freebsdfoundation.org/donate/](https://freebsdfoundation.org/donate/)。

我们还有一个针对大型商业捐助者的合作伙伴计划。你可以在 [https://freebsdfoundation.org/our-donors/ ](https://freebsdfoundation.org/our-donors/freebsd-foundation-partnership-program/)找到更多信息。

**操作系统的改进**

在 2022 年第二季度，有 243 份 src、62 份 port 和 12 份文档树的提交将 FreeBSD 基金会列为赞助商。这分别占了每个版本库中提交总数的 10.6%、0.7% 和 4.5%。

**赞助工作**

你可以在个别季度报告条目中读到一些基金会赞助的工作。

- 基本系统 OpenSSH 更新
- 正在进行的关于 LLDB 多进程调试支持的工作
- 无线状态
- 在 makefs 中支持 ZFS

这里介绍了其他正在进行的赞助工作。

- FreeBSD Wireguard 的改进

> Wireguard 项目的目的是改善对 FreeBSD Wirguard 内核模块的支持。
>
> John Baldwin 的工作包括调整模块，使其使用 FreeBSD 的 OCF 而不是 Wireguard 的内部实现。 它还包括增加新的密码和 API 支持。
>
> 最新的上游版本包含了这项工作。

- FreeBSD 上的 Openstack

> OpenStack 是一个用于不同类型资源（如虚拟机）的云系统。
>
> 然而，OpenStack 只非官方地支持 FreeBSD 作为客户系统。
>
> 这意味着用户可以在开放的云平台上催生 FreeBSD 实例，但目前还不能在 FreeBSD 主机上运行 OpenStack。
>
> 这个项目的目标是移植 OpenStack 组件，使 FreeBSD 能够作为 OpenStack 主机运行。

- Bhyve 问题支持

> 基金会最近签署了一份支持 Byhve 的新合同。
>
> 这份合同将使 John Baldwin 能够在 Bhyve 出现问题时为其奉献时间，特别是安全问题。

- Handbook 改进探索

> 在基金会的赞助下，Pau Amma 完成了一个小型项目，探索如何改进《Handbook》。
>
> 已经发出了一份调查，结果将很快与大家分享。

**持续集成和质量保证**

基金会提供了一名全职工作人员，并资助了一些项目，以改善持续集成、自动测试以及 FreeBSD 项目的整体质量保障工作。

**支持 FreeBSD 基础设施**

基金会为该项目提供硬件和支持。一个新的澳大利亚镜像被集群管理团队部署到了网上。如果你是大洋洲或东南亚的 FreeBSD 用户，请让我们知道安装程序镜像和软件包的下载速度是否有所提高。

通过你们的捐款，基金会购买了新的硬件来修复两个 PowerPC 软件包的构建器，一个是小端软件包（powerpc64le），第二个是大端软件包（powerpc64，powerpc）。新的硬件刚刚到达数据中心，很快就会安装。预计在不久的将来会有很多 PowerPC 软件包。

**倡导和教育 FreeBSD**

我们的大部分工作是致力于项目的宣传。这可能涉及到突出有趣的 FreeBSD 工作，制作文献和视频教程，参加活动，或做演讲。我们制作文献的目的是教给人们 FreeBSD 的基本知识，并帮助他们在采用或贡献的道路上更加容易。除了参加活动和发表演讲之外，我们还鼓励和帮助社区成员举办他们自己的 FreeBSD 活动，发表演讲，或者担任 FreeBSD 的工作人员。

FreeBSD 基金会在全球范围内赞助了许多会议、活动和峰会。这些活动可以是与 BSD 相关的，也可以是开源的，或者是面向未被代表的群体的技术活动。我们支持以 FreeBSD 为中心的活动，以帮助提供一个分享知识的场所，在项目上一起工作，并促进开发者和商业用户之间的合作。这都有助于提供一个健康的生态系统。我们支持非 FreeBSD 的活动，以促进和提高对 FreeBSD 的认识，增加 FreeBSD 在不同应用中的使用，并招募更多的贡献者加入该计划。我们将继续参加虚拟活动，并计划在 2022 年 6 月举行开发者峰会。除了参加和策划虚拟活动之外，我们还在不断地进行新的培训计划，并更新我们的指南选择，以促进更多的人尝试使用 FreeBSD。

请看我们上一季度所做的一些宣传和教育工作：

- 我们获得了 2022 年 10 月 30 日至 11 月 2 日在北卡罗来纳州罗利举行的 All Things Open 的展位和非营利性赞助商地位
- 我们在 7 月 28-30 日在加州洛杉矶举行的 Scale 19x 上的展位和研讨会已经确定。FreeBSD 研讨会将于 2022 年 7 月 29 日星期五举行，你可以到基金会的 502 号展位参观
- 确认我们是 2022 年 9 月 15-18 日在奥地利维也纳举行的 EuroBSDcon 的银牌赞助商
- 赞助并帮助组织 2022 年 6 月 16-17 日的 FreeBSD 开发者峰会。视频可以在 FreeBSD 项目的 YouTube 频道上看到
- 庆祝 2022 年 6 月 19 日的 FreeBSD 日，以及接下来的整个一周
- 我们获得了 7 月 30 日至 31 日在台湾举行的 COSCUP 之友级别的赞助
- 发布 FreeBSD 基金会 [2022 年春季更新](https://freebsdfoundation.org/news-and-events/newsletter/freebsd-foundation-spring-2022-update/)
- 新的博客文章
- [我们来谈谈基金会的资金问题](https://freebsdfoundation.org/blog/lets-talk-about-foundation-funding/)
- [新董事会成员访谈：Cat Allman](https://freebsdfoundation.org/blog/new-board-member-interview-cat-allman/)
- [欢迎 FreeBSD 的谷歌代码之夏参与者](https://freebsdfoundation.org/blog/welcome-freebsd-google-summer-of-code-participants/)
- [13.1 版本中的 FreeBSD 基金会工作](https://freebsdfoundation.org/blog/freebsd-foundation-work-in-the-13-1-release/)
- [基金会选举新的官员，采访即将离任的董事会成员](https://freebsdfoundation.org/blog/foundation-elects-new-officers-interviews-outgoing-board-members/)
- [帮助我们庆祝整个星期的 FreeBSD 日](https://freebsdfoundation.org/blog/help-us-celebrate-freebsd-day-all-week-long/)
- 新的和更新的如何操作和快速指南
  - [网络基础知识：WiFi 和蓝牙](https://freebsdfoundation.org/freebsd-project/resources/networking-basics-wifi-and-bluetooth/)
  - [FreeBSD 上的音频](https://freebsdfoundation.org/freebsd-project/resources/audio-on-freebsd/)
  - [用 VirtualBox 安装 FreeBSD (Mac/Windows)——视频指南](https://freebsdfoundation.org/freebsd/how-to-guides/installing-freebsd-with-virtualbox-video-guide/)
  - [FreeBSD 操作系统简介——视频指南](https://freebsdfoundation.org/freebsd-project/resources/an-introduction-to-the-freebsd-operating-system-video/)
  - [在 FreeBSD 上安装一个桌面环境——视频指南](https://freebsdfoundation.org/freebsd-project/resources/installing-a-desktop-environment-on-freebsd-video-guide/)
  - [在 FreeBSD 上安装一个 port——视频指南](https://freebsdfoundation.org/freebsd-project/resources/installing-a-port-on-freebsd-video-guide/)

我们通过出版专业的 FreeBSD 杂志来帮助世界了解 FreeBSD。正如我们之前提到的，FreeBSD 杂志现在是一份免费出版物。了解更多信息并访问最新的期刊：https://www.FreeBSDfoundation.org/journal/。

你可以在 https://www.FreeBSDfoundation.org/news-and-events/ 找到更多关于我们参加的活动和即将举行的活动。

**法律/FreeBSD 知识产权**

基金会拥有 FreeBSD 的商标，保护这些商标是我们的责任。我们还为核心团队提供法律支持，以调查出现的问题。

进入 https://www.FreeBSDFoundation.org ,了解更多关于我们如何支持 FreeBSD 以及我们如何帮助你的信息。



#### FreeBSD 发布工程团队

链接:

FreeBSD 13.1-RELEASE schedule 网址：https://www.freebsd.org/releases/13.1R/schedule/

FreeBSD 13.1-RELEASE 公告 网址：https://www.freebsd.org/releases/13.1R/announce/

FreeBSD 的发布 网址：https://download.freebsd.org/releases/ISO-IMAGES/

FreeBSD 的开发快照 网址：https://download.freebsd.org/snapshots/ISO-IMAGES/

联系:FreeBSD 发布工程团队，re@FreeBSD.org

FreeBSD 发布工程团队负责为 FreeBSD 的官方项目发布制定并发布发布计划，宣布代码冻结并维护相应的分支，以及其他事项。

在 2022 年的第二季度，发布工程团队完成了 13.1-RELEASE 周期的工作。这是 stable/13 的第二个版本分支。在整个发布周期中，发生了三次 BETA 构建和六次 RC（候选发布版）构建，将最终发布日期从 2022 年 4 月 21 日移至 2022 年 5 月 16 日，因为在最后一刻发现了一些问题。

我们感谢所有测试 13.1-RELEASE 的 FreeBSD 开发人员和贡献者，他们报告了问题，并 着周期的进展勤奋地进行了修改。

此外，在整个季度中，还为主分支、stable/13 和 stable/12 分支发布了几个开发快照版本。

赞助商：Rubicon Communications, LLC ("Netgate") 赞助商：FreeBSD 基金会



#### 集群管理团队

链接：

集群管理小组成员 网址：https://www.freebsd.org/administration/#t-clusteradm

FreeBSD 集群管理团队的成员负责管理该项目所依赖的机器，以同步其分布式工作和通信。在这一季度，该团队进行了以下工作：

- 在澳大利亚悉尼安装了一个新的镜像，由 IX 澳大利亚公司托管
- 修复了 CI 集群的硬件故障
- 建立一个新的内部监测系统
- 定期进行集群范围内的软件升级
- 对 FreeBSD.org 用户账户的定期支持工作

正在进行中：

- 与 PowerPC 团队合作，改进软件包构建者、通用和参考机器。
- 计划硬件更新，并修复各站点的杂项故障
- 改善成套建筑的基础设施
- 审查服务 jail 和服务管理员的运作情况
- 与 doceng@ 合作，改善 https://www.freebsd.org 和 https://docs.freebsd.org 的部署。
- 改进网络服务架构
- 完善集群备份计划
- 完善日志分析系统

我们正在欧洲寻找一个额外的全镜像站点（五个服务器）。请看[通用镜像布局](https://wiki.freebsd.org/Teams/clusteradm/generic-mirror-layout)，以满足我们的需要。我们也欢迎提供额外的单服务器镜像（见[小镜像](https://wiki.freebsd.org/Teams/clusteradm/tiny-mirror)），特别是在欧洲。



#### 持续集成

链接：

FreeBSD Jenkins Instance 网址：https://ci.FreeBSD.org

FreeBSD CI 软件存档 网址：https://artifact.ci.FreeBSD.org

FreeBSD Jenkins wiki 网址：https://wiki.freebsd.org/Jenkins Hosted CI wiki 网址：https://wiki.freebsd.org/HostedCI

第三方软件 CI 网址：https://wiki.freebsd.org/3rdPartySoftwareCI

与 freebsd-testing@ 相关的票据 网址：https://preview.tiny网址.com/y9maauwg

FreeBSD CI 存储库 网址：https://github.com/freebsd/freebsd-ci

dev-ci 邮件列表 网址：https://lists.freebsd.org/subscription/dev-ci

联系：Jenkins Admin jenkins-admin@FreeBSD.org

联系：Li-Wen Hsu lwhsu@FreeBSD.org

联系：[freebsd-testing 邮件列表](https://lists.freebsd.org/mailman/listinfo/freebsd-testing)

联系：IRC EFNet 平台上的 #freebsd-ci

FreeBSD CI 团队负责维护 FreeBSD 项目的持续集成系统。CI 系统检查提交的修改是否能够成功构建，然后对新构建的结果进行各种测试和分析。这些构建的工件被归档到工件服务器中，以备进一步测试和调试的需要。CI 团队成员检查失败的构建和不稳定的测试，并与该领域的专家合作，修复代码或调整测试基础设施。

在 2022 年的第二季度，我们继续与项目中的贡献者和开发者合作，以满足他们的测试需求，同时也与外部项目和公司保持合作，以改进他们的产品和 FreeBSD。

重要的已完成任务：

- 修正了 CI 集群的硬件故障问题

进行中的任务：

- 设计和实施提交前的 CI 构建和测试（以支持[工作流程工作组](https://gitlab.com/bsdimp/freebsd-workflow)的工作）
- 设计和实施 CI 集群的使用，以建立发布工程的工件。
- 测试和合并 [FreeBSD-ci repo](https://github.com/freebsd/freebsd-ci/pulls) 中的提交请求
- 简化贡献者和开发者的 CI/测试环境设置
- 设置 CI 阶段环境，并将实验性工作放在上面
- 整理 freebsd-ci 版本库中的脚本，为合并到 src 版本库做准备
- 更新 wiki 上的文件

正在进行或等待的任务：

- 收集和整理 [CI 任务和想法](https://hackmd.io/@FreeBSD-CI/freebsd-ci-todo)
- 为运行测试的虚拟客体设置公共网络接入
- 实施使用裸机硬件来运行测试套件
- 增加 drm port，针对 -CURRENT 构建测试
- 计划运行 ztest 测试
- 增加更多外部工具链相关的工作
- 提高硬件实验室的成熟度，增加更多测试用硬件
- 帮助更多的软件在其 CI 管道中获得 FreeBSD 支持（Wiki 页面:[3rdPartySoftwareCI](https://wiki.freebsd.org/3rdPartySoftwareCI), [HostedCI](https://wiki.freebsd.org/HostedCI)）
- 与托管 CI 供应商合作以获得更好的 FreeBSD 支持

更多的 WIP 信息请参见 [freebsd-testing@相关票据](https://preview.xn--tiny-yw4g653s.com/y9maauwg)，请不要犹豫，加入我们的努力吧!

赞助商：FreeBSD 基金会



#### Ports

链接：

关于 FreeBSD ports 网址：https://www.FreeBSD.org/ports/

贡献 Port 的网址：https://docs.freebsd.org/en/articles/contributing/#ports-contributing

FreeBSD Ports 监控 网址：http://portsmon.freebsd.org/

Ports 管理团队 网址：https://www.freebsd.org/portmgr/

Ports Tarball 网址：http://ftp.freebsd.org/pub/FreeBSD/ports/ports/

联系：René Ladan portmgr-secretary@FreeBSD.org

联系：FreeBSD Ports 管理团队 portmgr@FreeBSD.org

Ports 管理团队负责监督 Ports 的整体方向、建筑配套和人事事务。以下是上一季度发生的情况。

Port 的数量略高于 30,000。在上一季度，“main”分支有 151 个提交者提交了 9137 个代码，"2022Q2" 分支有 61 个提交者提交了 589 个代码。在写这篇文章的时候，有 2700 个开放 port 的 PR，其中 682 个是未分配的。与上一季度相比，提交活动略有减少，而 PR 的数量则保持不变。注意：Freshports 似乎大幅多计了。本季度的 port 数是以不同的方式得出的，与上一季度的 port 数没有可比性。

在上一季度，portmgr 欢迎 salvadore@ 的回归，但同时也因为缺乏活跃而与七个 port 提交者告别。

在两周一次的会议上，portmgr 讨论了以下主题。\* ca_root_nss 的未来 \* 基本系统提供某些 .pc 文件的可行性 \* 处理基本系统小版本升级时内核模块 port 不兼容问题的方法

经过开发人员的讨论，portmgr 决定授予所有文档和源码提交权限，以修复 Ports 树中任何与文档相关的错误，但不影响其功能。

以下是在 2022q2 期间对 Ports Tree 所做的修改： \* pkg 更新到了 1.18.3 版，Firefox 更新到了 102.0 版，Chromium 更新到了 103.0.50060.53 版 \* GCC、 Lazarus、 Python 和 Ruby 的默认版本分别更新为 11 (powerpcspe 保持 8 版)、 2.2.2、 3.9 和 3.0。\* 加入了两个新的 USES，gstreamer 用于支持基于 GStreamer 插件的 port，pytest 用于帮助使用 pytest 进行测试。



#### 项目

跨越多个类别的项目，从内核和用户空间到 port 或外部项目。

#### Linux 兼容层更新

联系：Dmitry Chagin [dchagin@FreeBSD.org](mailto:dchagin@FreeBSD.org) 联系：Edward Tomasz Napierala [trasz@FreeBSD.org](mailto:trasz@FreeBSD.org)

这个项目的目标是提高 FreeBSD 执行未经修改的 Linux 二进制文件的能力。目前特定的 Linux 应用程序的支持状态正在 Linux 应用程序状态 Wiki 页面上进行跟踪。

Y2k38 Linux 项目的实施已基本完成；所有 `'*_time64()'` 系统调用都已提交。

arm64 Linux 仿真层的状态与 amd64 Linux 仿真层的状态保持一致：即实现了 vDSO、机器依赖的 futexes、信号传递。

线程亲和性系统调用被修改以实现 Linux 语义。

总共修复了 50 多个错误；glibc-2.35 测试套件报告了不到 80 个失败的测试。

Linux 仿真层的所有修改都合并到了 stable/13 分支。

在 libsysdecode 和 kdump 中加入了对流行的 Linux 系统调用跟踪的初步支持。目前正在进行的工作是让追踪更多的系统调用发挥作用。

赞助商：EPSRC (Edward 的工作)



#### FreeBSD 与 riscv64

链接:

golang 主页 网址：https://github.com/golang/go

FreeBSD riscv64 github repo 网址：https://github.com/MikaelUrankar/go/tree/freebsd\_riscv64

FreeBSD riscv64 golang 问题 网址：golang/go#53466

联系：Mikaël Urankar mikael@FreeBSD.org 联系：Dmitri Goutnik dmgk@FreeBSD.org

已经完成了将 go 移植到 FreeBSD riscv64 上的工作，它可以构建并通过所有 run.bash 测试，包括 cgo （在 QEMU 和 Unmatched 上测试）。在上游创建了一个拉动请求，该提案已被添加到提案项目的活动栏中，并将在每周的提案审查会议上被审查。



#### 微软 HyperV 和 Azure 上的 FreeBSD

链接：

微软在 FreeBSD 上的 Azure WIKI 文章 网址：https://wiki.freebsd.org/MicrosoftAzure

微软在 FreeBSD 上的 HyperV WIKI 文章 网址：https://wiki.freebsd.org/HyperV

联系：Microsoft FreeBSD 集成服务团队 bsdic@microsoft.com

联系人：[freebsd- cloud 邮件列表](https://lists.freebsd.org/mailman/listinfo/freebsd-cloud)

联系：FreeBSD Azure 发布工程团队 releng-azure@FreeBSD.org

联系：Wei Hu whu@FreeBSD.org

联系：Li-Wen Hsu lwhsu@FreeBSD.org

Azure Marketplace 上的 [13.1-RELEASE 镜像](https://azuremarketplace.microsoft.com/marketplace/apps/thefreebsdfoundation.freebsd-13_1)已经发布。

正在进行的工作任务：

- 实现镜像构建和发布过程的自动化
- 构建并向 Azure 市场发布基于 ZFS 的镜像
  - 通过合并 [makefs(8)](https://www.freebsd.org/cgi/man.cgi?query=makefs&sektion=8&format=html) 和 [release(7)](https://www.freebsd.org/cgi/man.cgi?query=release&sektion=7&format=html) 的 ZFS 支持，taks 将受益。
    - https://reviews.freebsd.org/D23334
    - https://reviews.freebsd.org/D34426
    - https://reviews.freebsd.org/D35248
- 构建和发布 Hyper-V gen2 VM 镜像到 Azure Marketplace
- 被 https://bugs.freebsd.org/264267 阻拦

上述任务由 FreeBSD 基金会赞助，并由微软提供资源。

Wei Hu 和他在微软的同事正在从事由微软赞助的几项任务：

- 修复 Azure 中 Hyper-V gen2 VM 的启动问题
  - https://bugs.freebsd.org/264267
- 移植 Hyper-V 客户端以支持 arch64

开启的任务：

- 在 https://docs.microsoft.com 更新 FreeBSD 的相关文档
- 在 [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) 中支持 FreeBSD
- 将 [Azure 代理](https://www.freshports.org/sysutils/azure-agent) port 更新到最新版本
- [Azure 代理代理](https://github.com/Azure/WALinuxAgent/pull/1892)的上游本地修改

赞助商:微软提供了 Wei Hu 等人在微软的工作，以及其他方面的资源 赞助商：FreeBSD 基金会提供其他一切



#### 用户空间

影响基本系统和其中程序的变化。

#### 正在进行的关于 LLDB 多进程

链接：

Moritz Systems 项目简介网址：https://www.moritz.systems/blog/multiprocess-support-for-lldb/

进度报告 1 网址：https://www.moritz.systems/blog/implementing-non-stop-protocol-compatibility-in-lldb/

联系：Kamil Rytarowski kamil@moritz.systems 联系：Michał Górny mgorny@moritz.systems

根据上游的描述，“LLDB 是下一代高性能调试器。它是作为一组可重用的组件构建的，这些组件高度利用了更大的 LLVM 项目中的现有库，例如 Clang 表达式解析器和 LLVM 反汇编器。”

FreeBSD 在基本系统中包括 LLDB。之前赞助的项目改进了 LLDB，使其成为基本系统中可信的调试器，尽管它与 GNU GDB 的当代版本相比仍有一些限制。这个项目于 2022 年 4 月开始。它的目标是实现对多个进程同时调试的全面支持。

在项目开始时，LLDB 对多进程调试的支持非常有限。客户端的特点是支持通过维护与不同服务器实例的多个连接来同时调试多个独立进程。由于我们早期的工作，服务器能够处理 fork(2) 和 vfork(2) 调用，并且要么分离新分叉的子进程并继续跟踪父进程，要么分离父进程并跟踪子进程（等同于 GDB 的 `follow-fork-mode` 设置）。

待项目完成，LLDB 将能够同时追踪任意数量的分叉进程（相当于 GDB 的 `detach-on-fork off`）。将实现对 GDB 远程串行协议的多进程扩展的完全支持，以及对不停机扩展的部分支持，该扩展将使多个进程独立恢复和停止。

赞助商：FreeBSD 基金会



#### 在 makefs(8) 中支持 ZFS

链接：

邮件列表 网址：https://lists.freebsd.org/archives/freebsd-hackers/2022-May/001128.html

makefs(8) 代码审查 网址：https://reviews.freebsd.org/D35248 release(7) 代码审查 网址：https://reviews.freebsd.org/D34426

联系：Mark Johnston [markj@FreeBSD.org](mailto:markj@FreeBSD.org)

makefs(8) 是一个源自 NetBSD 的工具，它完全在用户空间创建文件系统镜像。它是建立虚拟机（VM）镜像的一个有用的工具链组件，因为它不需要任何特殊的权限，不像格式化一个字符设备，挂载新的文件系统，并将文件复制到上面。此外，makefs 可以创建可重复的镜像，并旨在最大限度地减少资源消耗。目前，FreeBSD 的 makefs 可以创建 UFS、cd9660 和 msdos（FAT）文件系统镜像。

最近的工作使 makefs 能够创建 ZFS 镜像。makefs 的 ZFS 支持包括创建多个数据集的能力，每个数据集映射到输入文件层次中的一个目录。然而，许多 ZFS 功能并不被支持，因为该实现只提供了获得可重复的根池所需的功能。

后续工作使 release(7) 框架能够使用这个新的 makefs 扩展来创建基于 ZFS 的虚拟机和云镜像。

赞助商：FreeBSD 基金会



链接：

OpenSSH 网址：https://www.openssh.com/

OpenSSH 8.9 发布说明 网址：https://www.openssh.com/txt/release-8.9\[https://www.openssh.com/txt/release-8.9

OpenSSH 9.0 发布说明 网址：https://www.openssh.com/txt/release-9.0\[https://www.openssh.com/txt/release-9.0

联系：Ed Maste [emaste@freebsd.org](mailto:emaste@freebsd.org)

OpenSSH，一套远程登录和文件传输工具，在 FreeBSD 基本系统中从 8.8p1 版本更新到 9.0p1。

它还没有被合并到 stable/13 和 stable/12 分支。我预计将在七月进行。

注意: OpenSSH 9.0p1 将 scp(1) 从使用传统的 scp/rcp 协议改为默认使用 SFTP 协议。可以使用 -O 标志来代替以前的协议。

赞助商：FreeBSD 基金会



#### pf 的最新状况

联系：Kristof Provost [kp@FreeBSD.org](mailto:kp@FreeBSD.org) 联系：Reid Linnemann [rlinnemann@netgate.com](mailto:rlinnemann@netgate.com)

**以太网**

pf 最近增加了对以太网层过滤的支持。见 2021q2 pf_ethernet 报告。

从那时起，以太网层的过滤功能得到了扩展：

- anchor 支持
- 查看第三层头的能力，以便与源/目的 IP（v4/v6）地址匹配
- 对 IP 地址匹配的表格支持
- 直接派发到 dummynet
- 将以太网层的数据包直接传给 dummynet，而不是对数据包进行标记，并依靠第三层来处理 dummynet

**Dummynet**

pf 最近开始能够使用 dummynet 进行数据包调度。这种支持已经被扩展和改进，现在相信已经可以用于生产了。

一个值得注意的修正是，回复到/路由到的流量现在也要接受 dummynet 调度。

**最后匹配时间戳**

pf 现在可以跟踪一个规则最后一次被匹配的时间。与 ipfw 规则的时间戳类似，这些时间戳在内部是以秒为单位的系统“墙上时钟时间”的 uint32_t 捕捉。(参见 time(9))。时间戳是 CPU 本地的，并且在每次规则或状态被匹配时更新。

赞助商：Rubicon Communications, LLC（"Netgate"）



#### 内核

内核子系统/功能、驱动支持、文件系统等方面的更新。

#### ENA FreeBSD 驱动程序更新

链接：

ENA readme 网址：https://github.com/amzn/amzn-drivers/blob/master/kernel/fbsd/ena/README.rst

联系：Michal Krawczyk [mk@semihalf.com](mailto:mk@semihalf.com) 联系：Dawid Gorecki [dgr@semihalf.com](mailto:dgr@semihalf.com) 联系：Marcin Wojtas Marcin Wojtas [mw@FreeBSD.org](mailto:mw@FreeBSD.org)

ENA（Elastic Network Adapter）是亚马逊网络服务（AWS）的虚拟化环境中可用的智能网卡。ENA 驱动程序支持多个发送和接收队列，可以处理高达 100Gb/s 的网络流量，这取决于它所使用的实例类型。

自上次更新以来已完成：

- ENA 驱动程序的上游版本 v2.5.0，其中包括：
  - 改进复位程序的处理
  - 延长定时器服务寿命，以便能够检测更多的硬件故障
  - 修复验证 Tx 请求 ID 的逻辑
  - 修复用于 Tx 的 IPv6 L4 校验和卸载处理
  - 在驱动中添加 NUMA awareness
- 对即将发布的 ENA 驱动（v2.6.0）进行内部审查，包括：
  - 进一步改进复位处理
  - 代码清理和风格修正
  - 记录的改进
  - 对 ENI 指标的检索进行修复

正在进行的工作：

- 测试即将发布的 ENA 驱动程序（v2.6.0）

赞助商：亚马逊



#### 新的蓝牙 ® 配置守护程序：blued

链接： blued git 网址：https://git.lysator.liu.se/kempe/blued

联系：

邮件：kempe@lysator.liu.se

IRC: kempe@libera.chat

**简介**

blued 工具提供了一个 IPC 接口，可以让非特权用户以用户友好的方式连接和使用蓝牙设备，并支持安全的简单配对（公钥加密，如果设备允许，还可以进行中间人保护）。

**什么是 blued？**

blued 有三个部分：一个库、一个守护程序和一个命令行工具。库对蓝牙的细节进行抽象，守护程序管理蓝牙设备，命令行工具让用户列出或扫描蓝牙设备，与设备配对，或从一个设备上取消配对。命令行工具通过 UNIX 套接字与守护程序进行通信。

与 bthidd 和 hcsecd 不同，blued 支持安全的简单配对并提供 IPC。为了让 HID 设备工作，仍然需要 bthidd。我们提供了一个脚本来配对蓝牙设备，并对 bthidd 进行适当的配置，这样它就可以在没有用户干预的情况下工作和重新连接。

待配对被证明是稳定的，错误也被解决了，我们计划以某种方式将 bthidd 与 blued 集成，使 HID 设备在配对时自动开始工作，而不需要使用外部脚本。长期目标是提供一个图形化的用户界面，可以列出设备并提供简单的一键式设置来连接它们。

**安装和使用 blued v0.1**

你需要在 `/etc/src` 中安装可选的 src 组件。

首先，[按照 FreeBSD 手册中的解释](https://docs.freebsd.org/en/books/handbook/advanced-networking/#network-bluetooth)，确保你已经加载了工作的蓝牙驱动。

为了测试 blued，请获取 [blued v0.1 的源代码](https://git.lysator.liu.se/kempe/blued/-/releases/v0.1)。然后编译它，用 kernel_patches 中的补丁修补你的 FreeBSD 内核，并按照 README 中的解释重新编译 hci 模块。

我主要在 FreeBSD 12.3 上测试了 blued，但在 13.1 上测试时，我的补丁应用得很干净。目前我还没有提供 port，但可以直接从构建目录中运行该软件，或者运行`make install`来安装所有需要的文件。blued 和 bluecontrol 都使用 capsicum，blued 可以被配置为无需 root 权限。

更多信息请参考 `README` 中的运行 blued 部分。

**帮助**

**测试**

我只用自己的鼠标试过这个软件，并意识到一个单一的蓝牙设备的样本量是相当小的。我期待着问题的出现，同时也非常期待其他人的反馈!

如果出现问题，从 /var/log/debug.log 和 /var/log/messages 的输出，以及尝试配对时从 `hcidump -x` 得到的流量转储，将有助于故障排除。

**贡献**

如果你想参与代码并提交补丁，欢迎你[访问 Lysator 的 Git 上的仓库](https://git.lysator.liu.se/kempe/blued)



#### OpenVPN DCO

链接：

D34340 网址：[D34340](https://reviews.freebsd.org/D34340)

OpenVPN 维基 网址：[OpenVPN wiki](https://community.openvpn.net/openvpn/wiki/DataChannelOffload)

联系：Kristof Provost [kp@FreeBSD.org](mailto:kp@FreeBSD.org)

OpenVPN DCO（或称数据通道卸载）将 OpenVPN 的数据包处理转移到内核中。

传统上，OpenVPN 使用 tun(4) 接口来传输和接收数据包。在这种设置下，收到的数据包由内核接收，传递给 OpenVPN 应用程序进行解密，然后再传回内核进行网络栈处理。这需要在内核和用户空间之间进行多次转换，自然会造成性能损失。

新的 if_ovpn OpenVPN DCO 卸载驱动完全在内核中执行加密/解密，提高了性能。

最初的性能测试显示，吞吐量从大约 660Mbit/s 提高到大约 2Gbit/s。

用户空间的 OpenVPN 代码也需要修改以使用新的 if_ovpn 卸载驱动。这预计将成为未来 2.6.0 版 OpenVPN 的一部分。

赞助商：Rubicon Communications, LLC (“Netgate”)



#### 无线更新

链接：

Intel iwlwifi 状态 FreeBSD wiki 页面 网址：https://wiki.freebsd.org/WiFi/Iwlwifi

Realtek rtw89 状态 FreeBSD wiki 页面 网址：https://wiki.freebsd.org/WiFi/Rtw89

联系：Bjoern A. Zeeb [bz@FreeBSD.org](mailto:bz@FreeBSD.org)

整个项目旨在为目前使用 LinuxKPI 兼容代码的 FreeBSD 带来对较新芯片组的支持，该代码由本地 net80211 和内核代码支撑。此外，我们的目标是继续努力支持更新的无线标准。在第二季度，有 40 个提交进入了 FreeBSD CURRENT。随着越来越多的用户尝试多种驱动，支持时间也在增加。

早期版本的 Intel iwlwifi 衍生的无线驱动在 13.1-RELEASE 中发布了，这使得这项工作进入了第一个 FreeBSD 版本。此后，iwlwifi 驱动程序和固件又在 CURRENT 和 stable/13 中进行了更新，这是持续开发的一部分。与上游 Intel Linux 版本的驱动共享的文件中的变化现在不到 400 行。最近，一个长期存在的老式芯片组的问题（有希望）得到解决，允许支持 iwm(4) 的网卡在近三个月后再次与 iwlwifi(4) 一起工作。在今年年底之前，项目的主要重点将是让我们达到当代的速度。

4 月 1 日，使用与 iwlwifi 工作相同的 LinuxKPI 基础设施，Realtek 的 rtw88(4) 驱动被纳入了 CURRENT。由于 DMA 的问题，在接下来的几周里，一个解决方法被开发出来并放到了代码仓库上，因此用户不再需要修补内核。对于物理内存超过 4GB 的机器，该驱动仍然需要在 loader.conf 中设置一个调整项。这个调整项使得该驱动在六月被合并到了 stable/13，随后又在 CURRENT 和 stable/13 中进一步更新。随着基于 rtw88 的芯片组的 USB 部分被准备纳入 Linux，准备 FreeBSD 也能支持 USB 部分的工作已经开始（需要更多时间）。

在过去的几个月里，Realtek 的 rtw89 已经开始编译，在它能够在 URRENT 启用之前，仍然是一个稳定运行和关联的工作。

感谢所有用户的测试和反馈，耐心等待下一次的更新、错误修复，或者只是我的一个答复。和你们一起工作是一件非常愉快的事情! 继续向我发送错误报告，但请记住，你应该感谢 FreeBSD 基金会，因为它使大部分工作成为可能。

要了解最新的开发状况，请关注 freebsd-wireless 邮件列表 并查看 wiki 页面。

赞助商：FreeBSD 基金会



#### 共享页地址随机化

链接：

[D35392](https://reviews.freebsd.org/D35392) [D35393](https://reviews.freebsd.org/D35393) [D35349](https://reviews.freebsd.org/D35349)

联系：Kornel Duleba [mindal@semihalf.com](mailto:mindal@semihalf.com)

联系：Marcin Wojtas [mw@FreeBSD.org](mailto:mw@FreeBSD.org)

共享页是一个 R/X 页，由 image activator 映射到每个进程中。它存储了 signal trampoline 以及其他元数据，例如实现用户空间定时器所需的信息。以前，它被映射在进程虚拟地址空间的顶部。随着上述变化，它的地址将被随机化。我们计划对所有架构的 64 位二进制文件默认开启该功能。目前，这些补丁正在审查中，等待批准。

赞助商：Stormshield



#### 架构

更新特定平台的功能，并引入对新硬件平台的支持。

#### 恩智浦 DPAA2 支持

链接：

[更改历史](https://github.com/mcusim/freebsd-src/commits/lx2160acex7-dev)

[代码](https://github.com/mcusim/freebsd-src/tree/lx2160acex7-dev/sys/dev/dpaa2)

联系：Dmitry Salychev [dsl@FreeBSD.org](mailto:dsl@FreeBSD.org)

联系：Bjoern A. Zeeb [bz@FreeBSD.org](mailto:bz@FreeBSD.org)

恩智浦的一些 SoC（LX2160A、LS1088A）配备了 [DPAA2](https://www.nxp.com/design/qoriq-developer-resources/second-generation-data-path-acceleration-architecture-dpaa2:DPAA2)，即第二代的数据路径加速架构。它允许动态配置和连接数据包处理“对象”（网络接口的 DPNI，媒体访问控制器的 DPMAC 等），以形成一个片上网络。

在上个季度，该驱动开始运行良好，足以用于 [SolidRun 的 Honeycomb LX2](https://solidrun.atlassian.net/wiki/spaces/developer/pages/197494288/HoneyComb+LX2+ClearFog+CX+LX2+Quick+Start+Guide)（ACPI 测试平台），Traverse Technologies 已经为（他们的）Ten64（用作 FDT 测试平台）制作了一个 [FreeBSD 预览](https://forum.traverse.com.au/t/freebsd-preview-for-ten64/173)。

该驱动仍在进行中，但已接近审查，以便将第一个版本放入代码库中，让大家从中受益。

WIP：

- FDT MDIO 支持。FreeBSD 目前缺乏对 SPF 部分的支持
- 驱动程序资源的去分配，以正确卸载 dpaa2.ko
- [错误修复](https://github.com/mcusim/freebsd-src/issues)和改进

TODO:

- 对 DPIO 和 DPNI 的处理器亲和性
- 缓存的内存支持的软件门户
- 缓解瓶颈
- 支持更多的硬件组件（DPSW、DCE 等）

赞助商：赤裸裸的热情 :)

赞助商：Traverse Technologies (提供 Ten64 HW 用于测试)



#### 关于 arm64 及其他的中等规模的超级页

联系：Eliot H. Solomon [ehs3@rice.edu](mailto:ehs3@rice.edu) 联系：Alan L. Cox [alc@rice.edu](mailto:alc@rice.edu)

64 位 ARM 架构的页表描述符格式包含一个称为连续位的标志。这告诉 MMU，它可以缓存一组对齐的、物理上连续的 16 个页表条目，这些条目具有相同的权限和属性，只需使用一个 TLB 条目。

毗连位，以及概念上类似于 RISC-V 架构的 Svnapot 扩展，允许使用 64KB 的超级页。这些中等大小的超级页可以为较小的内存对象带来地址转换的速度，通常与更传统的 2 MiB 超级页相关。

这个项目的重点是为 FreeBSD 带来对中型超级页的支持。到目前为止，我们已经修改了 arm64 pmap 的代码，通过检测物理上连续的页表项并使用 Contiguous 位来自动利用 64 KiB 超级页。现在，我们正在努力调整内核的超级页保留模块，以支持 64 KiB 的保留，除了目前的 2 MiB 的保留之外。增加中等大小的预留将允许虚拟内存系统明确地分配符合超级页推广要求的内存块，而不是仅仅希望它们偶然出现。

我们的目标是以一种通用的方式来实现这一点，使其有可能指定多个任意的 2 次方预留尺寸，从而更容易利用其他架构上的硬件功能，如 Ryzen 的 PTE 凝聚，它可以透明地将 4 KiB 的页表条目组合并为中等大小的超级页。

赞助商：莱斯大学计算机科学系



#### 文档

文档树、手册页或新的外部书籍/文件中值得注意的变化。

#### 文档工程团队

链接：FreeBSD 文档项目

链接：为新的贡献者提供的 FreeBSD 文档项目入门手册

链接：文档工程团队

联系：FreeBSD Doceng 团队 [doceng@FreeBSD.org](mailto:doceng@FreeBSD.org)

doceng@ 团队是一个处理与 FreeBSD 文档工程相关的一些元项目问题的机构；更多信息请参见 [FreeBSD Doceng 团队章程](https://www.freebsd.org/internal/doceng/)。

在上个季度，Graham Perrin (grahamperrin@) 和 Pau Amma (pauamma@)，被授予文档提交权限。

有几个项目还在讨论中。

将网站和文档门户与项目的 GeoDNS 基础设施进行镜像。

如何处理文档中的商标。

从网站和文档门户中删除过时的翻译。

#### Weblate 上的 FreeBSD 翻译

链接：在 Weblate 上翻译 FreeBSD 链接：FreeBSD Weblate 实例

2022 年第二季度状况

- 12 种语言
- 152 个注册用户（9 个新用户）

语种

- 中文（简体）(zh-cn)
- 中文（繁体）(zh-tw)
- 荷兰语 (nl)
- 法语(fr)
- 德语 (de)
- 印度尼西亚语 (id)
- 意大利语 (it)
- 挪威语 (nb-no)
- 波斯语 (fa-ir)
- 葡萄牙语 (pt-br)
- 西班牙文 (es)
- 土耳其语(tr)

我们要感谢每一个作出贡献、翻译或审阅文件的人。

同时，请在你的本地用户组中帮助推广这项工作，我们总是需要更多的志愿者。

#### FreeBSD 网站改版——WebApps 工作组

联系：Sergio Carlavilla [carlavilla@FreeBSD.org](mailto:carlavilla@FreeBSD.org)

负责创建新的 FreeBSD 文档门户和重新设计 FreeBSD 主网站及其组件的工作小组。FreeBSD 开发者可以在 FreeBSD Slack 频道 #wg-www21 上关注并加入该工作组。这项工作将分为四个阶段：

1.  重新设计文档门户

    创建一个新的设计，具有响应性和全局搜索功能。(完成)

2.  重新设计网络上的手册页面

    使用 mandoc 生成 HTML 页面的脚本。(工作正在进行中)

3.  重新设计网络上的“ports”页面

    创建应用门户的 port 脚本。(工作正在进行中)

4.  重新设计 FreeBSD 的主网站

    新的设计，响应性和暗色主题。(未开始)



#### Ports

影响 Ports 的变化，无论是涉及大部分目录的全面变化，还是个别 Ports 本身的变化。

#### FreeBSD 上的 KDE

链接：

KDE FreeBSD 网址：https://freebsd.kde.org/

KDE Community FreeBSD 网址：https://community.kde.org/FreeBSD

联系：Adriaan de Groot [kde@FreeBSD.org](mailto:kde@FreeBSD.org)

KDE on FreeBSD 项目将来自 KDE Community 的软件，以及依赖关系和相关软件打包到 FreeBSD ports 上。这些软件包括一个叫做 KDE Plasma 的完整桌面环境（适用于 X11 和 Wayland）和数百个可以在任何 FreeBSD 机器上使用的应用程序。

KDE 团队 (kde@) 也是 desktop@ 和 x11@ 的一部分，他们建立了软件栈，使 FreeBSD 成为漂亮的、可用于日常驱动的基于图形的桌面机器。下面的说明主要是描述 KDE 的 Ports，但也包括对整个桌面堆栈有意义的项目。

**KDE 堆栈**

KDE Gear 每季度发布一次，KDE Plasma 每月更新一次，KDE Frameworks 每月也有一个新版本。这些（大型）更新在其上游发布后不久就登陆，不单独列出。

- astro/kstars 最新版本 3.5.9。
- deskutils/grantleetheme 在 UPDATING 中得到了一个条目，因为这个 port 的安装结构发生了一些不寻常的变化。
- deskutils/kalendar 加入了 KDE Gear 版本。
- devel/okteta 更新了二进制（以及八进制和十六进制）数据查看器和编辑器。
- finance/kraft 需要对较新的 KDE 框架进行特定的构建修复。
- games/gcompris-qt 扩展了新版本，现在支持更多的图像格式（某些活动需要）。
- graphics/digikam 在构建过程中不再需要 SQL 服务器。
- graphics/krita 更新到了 5.0.5，可能是最后的 5.0 版本。
- math/labplot 在最近的版本中有大量的新功能，如果你需要任何类型的数据绘图，非常值得一看。
- net-im/ruqola 已经更新。这是一个 Qt 风格的 Rocket 聊天应用程序。
- www/falkon 加入了 KDE Gear 的发布。

**相关应用程序**

- Archivers/quazip 被更新了。
- deskutils/semantik 已更新。
- 更新了 develop/py-qt5-pyqt，以便该 port 现在也能拉入 DBus。几乎所有桌面 Qt 应用程序都需要 DBus，包括那些用 Python 编写的应用程序。
- devel/qcoro 在某些 FreeBSD 版本上有构建问题，已解决。
- devel/qtcreator 随每个新版本的发布而更新。
- devel/qt5 在 ports 中更新了它的基础架构，这样它在卸载时就不会产生奇怪的错误信息。
- graphics/ksnip 和相关库已更新到最近的版本。
- Matrix 客户端 Nheko (net-im/nheko) 和 Neochat (net-im/neochat) 在发布和库升级之后进行了更新。
- 更新了 x11/rsibreak；有助于防止在写长的季度报告时受伤。

**其他方面**

- devel/appstream 的更新支持更多的应用程序信息。
- 如果用户安装了多个 python3 Port 和 lang/python3，devel/cmake 更倾向于使用通用的 python3 而不是版本化的 python3。
- 更新了 devel/dbus。
- graphics/poppler 更新了若干次。
- graphics/ImageMagick (包括 6 和 7) 更新了若干次。
- multimedia/gstreamer 已更新。



#### GCC：更新 GCC_DEFAULT 和其他改进

链接：

GCC 项目 网址：https://gcc.gnu.org

GCC 11 发布系列 网址：https://gcc.gnu.org/gcc-11/

联系：[toolchain@FreeBSD.org](mailto:toolchain@FreeBSD.org)

联系：Gerald Pfeifer [gerald@pfeifer.com](mailto:gerald@pfeifer.com)

联系：Lorenzo Salvadore [salvadore@FreeBSD.org](mailto:salvadore@FreeBSD.org)

联系：Lorenzo Salvadore Piotr Kubaj [pkubaj@FreeBSD.org](mailto:pkubaj@FreeBSD.org)

- salvadore@ 致力于将 Mk/bsd.default-versions.mk 中的 GCC_DEFAULT 从 10 升级到 11，根据 antoine@ 的 exp-runs 打开 bug 报告并修复了一些：非常感谢所有帮助这项工作的人。GCC_DEFAULT 从 GCC 10 到 GCC 11 的更新现在已经由 gerald@ 提交，并在下一个季度的分支中及时发生。https://bugs.freebsd.org/bugzilla/show\_bug.cgi?id=258378 pkubaj@ 通过引入一个默认启用的新选项，将 GCC 引导转换为使用 GCC 本身的链接时间优化，适用于 GCC 11 和更新版本。启用 LTO_BOOTSTRAP 进行构建需要大量的内存和时间。实际需要多少资源取决于你的配置 (例如，你是用 port 还是用 poudriere 构建？你的架构是什么？）。举个例子，一个用户报告说需要 5 GiB 的临时文件，而在 PR 265254 中，由于产生了过多的进程，估计需要大约 130 GB 的内存（也见 https://gcc.gnu.org/bugzilla/show\_bug.cgi?id=106328 ）。考虑禁用 LTO_BOOTSTRAP，改用 STANDARD_BOOTSTRAP（或者完全禁用 BOOTSTRAP），以防出现问题。
- pkubaj@ 还添加了 lang/gcc12 和 lang/gcc13-devel port，并将 lang/gcc9 更新到 9.5。
- 这三个改动仍然需要帮助，以便与上游的 GCC 一起工作（需要 src 专业知识，而不是 ports）。
- 上游的 lang/gcc11/patch-gets-no-more
- upstreaming lang/gcc11/patch-arm-unwind-cxx-support
- https://bugs.freebsd.org/bugzilla/show\_bug.cgi?id=256874



#### Valgrind - 13.1/14.0 的大量错误修正和更新

链接：

Valgrind 主页 网址：https://www.valgrind.org/

Valgrind 新闻 网址：https://www.valgrind.org/docs/manual/dist.news.html

联系：Paul Floyd [pjfloyd@wanadoo.fr](mailto:pjfloyd@wanadoo.fr)

在过去的几个月里，FreeBSD 上的 Valgrind 已经进行了相当多的错误修正。特别是，i386 版本在很大程度上已经“赶上”了它的老大哥 amd64。

devel/valgrind-devel port 已经提升到 3.20.0.g20220612,1，其中包括以下所有的变化。如果你经常使用 Valgrind，请切换到 valgrind-devel。

以下是自 Valgrind 3.19.0 发布以来的变化列表（该版本是与 devel/valgrind port 一起使用的版本）。

- 如果 Valgrind 在保存系统调用的携带标志时有信号到达，则信号恢复不正确。
- 修正了从 ld 产生的 PT_LOADs 中读取 DWARF 调试信息的问题，版本 9 后的 ld 将 RW 段分成两部分，这主要影响到共享库（.so 文件）。
- 在 i386 上正确实现线程 GDTs 的管理，这限制了应用程序只能创建 8192 个线程
- 使“brk”的第一页对寻址无效
- 分析和清理回归测试套件，特别是调整 i386 的泄漏测试，使其不能检测到 ECX 中剩余指针可能造成的泄漏。
- 让 lldb 可以读取 coredumps。
- 改进 C 语言分配函数的 errno 设置。
- 修正用 llvm-devel (15.0.0) 建立 Valgrind 的问题。

对于 FreeBSD 13.1 / 14.0，有

- funlinkat, copy_file_range, swapoff, shm_open2 的系统调用包装器。
- 在 fcntl 中添加 K_INFO 处理程序
- 增加了对新的 auxv 条目的处理
- 为 DRD 和 Helgrind 增加了一些默认的抑制措施

现在有一个初始版本的 vgdb invoker 支持——这允许 vgdb 使用 ptrace 来强迫 valgrind 轮询 gdb 命令。这在 port 版本中还不能使用。

这并没有留下多少悬而未决的问题。我希望 14.0 和更新的 llvm 版本会继续需要支持。除此以外，还有

- 一些关于错误信息的小问题，以获得正确的源信息
- 更好的核心转储（低优先级）
- 为 Helgrind 处理 TLS（线程本地存储）（如果不是不可能的话，也很难）。



#### FreeBSD 上的 Pantheon 桌面

链接：

基本操作系统网址：https://elementary.io

开发库 网址：https://codeberg.org/olivierd/freebsd-ports-elementary

联系：Olivier Duchateau [duchateau.olivier@gmail.com](mailto:duchateau.olivier@gmail.com)

Pantheon 桌面环境是为 elementary OS 设计的。它建立在 GNOME 技术（如 Mutter、GNOME Shell、GTK 3 和 4）之上，并以 Vala 语言编写。

其目标是为用户提供一个新的桌面。有些功能没有得到很好的支持，但我们可以有完整的会话。

仓库包含 Mk/Uses 框架 elementary.mk，官方应用程序，以及依赖 x11-toolkits/granite 的策划的 port（总共 56 个新 port）。

我已经提交了几个补丁，特别是：

- x11-toolkits/granite7
- devel/libgee 更新到 0.20.5 [bug #262893](https://bugs.freebsd.org/bugzilla/show_bug.cgi?id=262893)
- sysutils/bamf 更新至 0.5.6 [bug #264203](https://bugs.freebsd.org/bugzilla/show_bug.cgi?id=264203)

开放任务

- 增加对用户设置的支持（这是非常以 Ubuntu 为中心的）。
- 完成移植 wingpanel-indicator-power（电源管理）。



#### 英特尔的 igt-gpu-tools 的完整功能移植

链接：

FreeBSD Wiki 项目页面 网址：https://wiki.freebsd.org/SummerOfCode2022Projects/ImprovingTheLinuxKPICompatibilityLayerForTheFreeBSDGraphicsStack

状态报告 网址：https://cdaemon.com/tags/gsoc2022

联系：Jake Freeland [jfree@freebsd.org](mailto:jfree@freebsd.org)

Intel 的 igt-gpu-tools 是 Linux 上 drm 驱动的一个通用测试套件。igt-gpu-tools 套件被分成针对 kms、内存管理和命令提交的测试和工具。该工具提供了详细的报告，以便透明地跟踪内核变化，并对现代 drm 驱动进行有效的调试。

将该项目移植到 FreeBSD 上可以为 FreeBSD 的 LinuxKPI 驱动的 drm 驱动的未来版本带来更大的稳定性。一个合适的 kms 驱动的测试套件也可以增加代码输出，使 FreeBSD 的桌面体验与 Linux 代码库同步。

该项目于 2022 年 6 月 13 日在 FreeBSD 的谷歌代码之夏计划下正式启动。我改编的代码可以在删除非 FreeBSD 兼容片段后进行编译。我们的计划是以符合 POSIX 的方式重新实现这些被剥离的组件。

值得注意的不兼容代码包括：debugfs，libkmod，libprocps，Linux 性能事件，和 Linux userfaultfd。如果你愿意协助将 libkmod 或 libprocps 移植到 ports 中，请不要犹豫，与我联系。

当 FreeBSD 兼容代码完成后，我将在 FreeBSD 14.0-CURRENT 上使用一系列图形处理器运行修改后的 igt 测试。如果一切顺利，这个项目的 diff 将被提交到 ports 中。

赞助商：谷歌代码之夏

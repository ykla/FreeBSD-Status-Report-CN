# FreeBSD 2023 年第三季度 季度状况报告

### FreeBSD 2023 年第三季度 季度状况报告

这是 2023 年的第三份状态报告，共包含 32 项内容。

这是夏季季度，因此它包含了许多来自 Google Summer of Code 的有趣新闻。当然，我们也有我们通常的团队报告，许多项目与我们分享了它们的最新消息。为 FreeBSD 14 的首次发布完成了许多重要的工作。

祝阅读愉快。

Lorenzo Salvadore，代表状态团队。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

这份报告的网页版本可以在此处查看：

https://www.freebsd.org/status/report-2023-07-2023-09/

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

目录

* FreeBSD 团队报告
    * FreeBSD 核心团队
    * FreeBSD 基金会
    * FreeBSD 发布工程团队
    * 持续集成
    * Ports 集合
* 项目
    * 填补 FreeBSD 桌面体验的空白
    * LLDB 内核模块改进
* 用户空间
    * 基于 OpenSSL 3 的基础上 — 改进
    * 登录类修复和改进
* 内核
    * 在使用日志软更新的文件系统上启用快照
    * FreeBSD 内核的 SquashFS 驱动程序
    * 进程可见性安全策略
    * Linux 兼容性层更新
* 架构
    * NXP DPAA2 支持
    * 用于 amd64 的 SIMD 增强
    * 将 mfsBSD 集成到发布构建工具中
* 云
    * 在 FreeBSD 上运行 OpenStack
    * FreeBSD 在 Microsoft HyperV 和 Azure 上
    * FreeBSD 在 EC2 上
* 文档
    * 文档工程团队
    * FreeBSD 在线编辑器和手册编辑器
    * FreeBSD 专家系统
* 端口
    * 在 FreeBSD 上运行的 KDE
    * 在 FreeBSD 上运行的 Pantheon 桌面
    * FreeBSD 办公团队
    * Wifibox：使用 Linux 驱动在 FreeBSD 上驱动您的无线网卡
    * FreeBSD 上的 GCC
    * Valgrind：为 FreeBSD 15 更新的 valgrind-devel
    * GitLab 16.3 可用
    * PortOptsCLI — Ports 集合辅助工具
* 第三方项目
    * 介绍 BSD Cafe 项目
    * 容器和 FreeBSD：Pot、Potluck 和 Potman

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### FreeBSD 团队报告

摘自各种官方和半官方团队的条目，详见管理页面。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD 核心团队**

联系方式：FreeBSD 核心团队 [core@FreeBSD.org](mailto:core@FreeBSD.org)


FreeBSD 核心团队是 FreeBSD 的治理机构。

**Hans Petter Selasky 的离世**

FreeBSD 核心团队要感谢 Hans Petter Selasky 多年的服务。我们为他的离世感到悲伤，并与社区一同哀悼。

悼念。

**与 FreeBSD 基金会的会议**

核心团队和 FreeBSD 基金会继续会面，讨论 FreeBSD 管理、开发和未来的下一步计划。核心团队与基金会的董事会成员以及基金会的员工进行了两次会议。他们讨论了基金会如何帮助核心团队和整个项目。

**Portmgr termlimits**

核心团队与端口管理团队讨论了引入开发者在团队中的归属时间限制的问题。该提案得到了端口管理团队的批准，将于 2024 年初生效，同时定期的潜伏者计划将为端口管理团队引入一批新成员。

**FreeBSD 15 中弃用 32 位平台**

正在进行工作，将在 FreeBSD 15 中将对 32 位平台的支持标记为“弃用”。

**Matrix 即时通讯**

Matrix 实例和 Element-web 客户端的测试仍在进行中。

计划在九月的 EuroBSDCon 之后发布 beta 版。

**改进提交位到期策略**

核心团队将阐明一旦开发者成为校友后如何更新 PGP 密钥。

**EuroBSDCon**

核心团队成员在 EuroBSDCon 期间在科英布拉与 FreeBSD 基金会会面，讨论了项目的发展方向。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD 基金会**

链接：

FreeBSD 基金会网址：https://freebsdfoundation.org/

技术路线图网址：https://freebsdfoundation.org/blog/technology-roadmap/

捐赠网址：https://freebsdfoundation.org/donate/

基金会合作伙伴计划网址：https://freebsdfoundation.org/our-donors/

freebsd-foundation-partnership-program/

FreeBSD Journal 网址：https://freebsdfoundation.org/journal/

基金会活动网址：https://freebsdfoundation.org/our-work/events/

联系人：Deb Goodkin [deb@FreeBSDFoundation.org](mailto:deb@FreeBSDFoundation.org)

FreeBSD 基金会是一家致力于支持和推动 FreeBSD 项目及其全球社区的 501(c)(3) 非营利组织。个人和公司的捐赠资金用于管理和资助软件开发项目、会议和开发者峰会。我们还向 FreeBSD 贡献者提供差旅津贴，购买和支持硬件以改善和维护 FreeBSD 基础设施，并提供资源以改进安全性、质量保证和集群管理工作。我们发布营销材料，以推广、教育和倡导 FreeBSD，促进商业供应商与 FreeBSD 开发者之间的合作，并最终代表 FreeBSD 项目执行涉及认可法律实体的合同、许可协议和其他法律安排。

在这个季度，我们协助 FreeBSD 庆祝其 30 周年！这种激动人心的氛围推动我们加速努力，推动 FreeBSD 在增长和创新方面取得更大进展，这使我们专注于确定可以投入资源的关键领域。在九月份的董事会会议上，我们进一步明确了我们的目标，重点是增加 FreeBSD 的采用和可见性，多元化我们的资金来源，并投资于项目的社区健康和长期稳定性。我们正在确定关键受众和市场，并为这些目标设定可衡量的成果。

在这份状态报告中，您将了解到有关我们助力推动 FreeBSD 增长和创新的工作的更多信息。我们将重点介绍我们正在进行的所有技术工作，既有来自我们内部软件开发人员的工作，也有外部项目资助的努力。您将了解我们在推广 FreeBSD 到我们社区之外受众的倡导工作。最后，您将看到我们与当前和潜在的商业用户建立联系所做出的巨大努力。

**筹款**

我们要衷心感谢所有慷慨捐赠以支持我们工作的人。除了众多个人捐赠之外，我们特别感谢 NetApp、Netflix 和 ARM 的重要捐款。仅在第三季度，我们就收到了 183,842 美元的捐款，使我们今年的总额达到 375,000 美元。今年我们的预算约为 2,230,000 美元，其中包括增加用于 FreeBSD 倡导和软件开发的支出。我们预算的一大部分用于与直接改进 FreeBSD 并保持其安全性相关的工作。通过提供专门的个人来重点关注合作伙伴关系的重要性，我们可以有效地强调投资我们努力的重要性，并强调 FreeBSD 的长期可行性对公司的意义。您的支持对于我们的使命至关重要，我们深深感谢您对 FreeBSD 社区的承诺。请考虑捐赠支持我们的 2023 年筹款活动！https://freebsdfoundation.org/donate/ 对于我们较大的商业捐赠者，请查看我们更新的 FreeBSD 基金会合作伙伴计划。

**合作伙伴关系和研究**

在本季度的合作伙伴关系和研究中，我们在三个关键领域取得了进展：

首先，企业工作组开始壮大，参与人数增至 58 人，并在四个工作流中展开活跃的项目。这些工作流包括云原生、Samba、bhyve 可管理性以及支持 AI 工作负载。在其他几个领域也存在兴趣，我们预计到年底和明年第一季度，我们将在多个关注领域看到有意义的功能更新。

其次，我们与其他开源社区成员和组织（尤其是开源倡议组织）合作取得了良好的进展，推动了来自 FreeBSD 社区的提案和技术。与开源倡议组织的开放政策联盟合作，我们正在回应美国政府有关如何支持开源安全性和可持续性的信息请求。作为此过程的一部分，Greg Wallace 在最近在北卡罗来纳洛利市举行的 All Things Open 大会上参与了由开放政策联盟组织的一个小组组织的讨论。Greg Wallace 还一直在追踪美国政府如何在其默认安全性政策建议中整合 CHERI，比如来自美国和全球政府安全机构的最新报告。在第 28 页，CHERI 被列为关键的“设计时安全”策略，紧随 Rust 之后。

最后，我们继续加强与越来越多使用

 FreeBSD 的公司的合作伙伴关系。几个会议促进了这些关系，包括 EuroBSDCon、开源峰会和 All Things Open。我们还制定了一个新的计划，支持与美国政府合作的供应商/云用户。该计划的详细信息将在 FreeBSD 供应商峰会上宣布。

**倡导**

我们的大部分工作致力于 FreeBSD 项目的倡导。这可能涉及突出展示有趣的 FreeBSD 工作、制作文学和视频教程、参加活动或进行演讲。我们制作文学的目标是教导人们 FreeBSD 的基础知识，并帮助他们更轻松地采用或贡献。除了参加和演讲活动外，我们鼓励并帮助社区成员举办自己的 FreeBSD 活动、做演讲或设立 FreeBSD 展台。

FreeBSD 基金会赞助了全球许多会议、活动和峰会。这些活动可以是与 BSD 相关的、开源的，或者是面向少数群体的技术活动。我们支持以 FreeBSD 为重点的活动，以帮助提供一个分享知识、共同开展项目工作和促进开发者与商业用户合作的场所。这有助于提供一个健康的生态系统。我们支持非 FreeBSD 活动，以推广和提高 FreeBSD 的知名度，在不同应用中增加 FreeBSD 的使用，并吸引更多的贡献者加入项目。我们不断向我们的年度计划中添加新的活动。今年七月，我们在俄勒冈州波特兰举办的 FOSSY 新开源大会上举办了研讨会并设立了展台。除了参加和策划会议外，我们还在不断努力推动新的培训计划，并更新我们的操作指南选择，以促使更多的人尝试 FreeBSD。

查看我们的一些倡导工作：

  * 在 FOSSY 于 2023 年 7 月 13 至 16 日在俄勒冈州波特兰举行的研讨会上设立了展台。

  * COSCUP 于 2023 年 7 月 27 至 29 日在新北市举行，担任友情赞助商。

  * 在 EuroBSDCon 2023 于 2023 年 9 月 14 至 17 日在葡萄牙科英布拉举行的 FreeBSD 开发者峰会上发表演讲，并赞助并设立了展台。

  * 参加了 2023 年 9 月 19 至 21 日在西班牙毕尔巴鄂举办的欧洲开源峰会。

  * 继续策划于 2023 年 11 月 2 至 3 日在加利福尼亚州圣何塞举行的 FreeBSD 供应商峰会。

  * 继续管理我们的 Google Summer of Code 计划。

  * 发布了七月份的新闻通讯。

  * 其他博客文章

      * 在活动中倡导：2023 年 5 月 FreeBSD 开发者峰会和 BSDCan

      * 升级到 FreeBSD 13.2 的前十大原因

      * 2023 年 7 月软件开发项目更新

      * 用于研究的 FreeBSD：CHERI/Morello

      * 了解 FreeBSD Google Summer of Code 学生

          * Soobin Rho

          * Raghav Sharma

          * Sudhanshu Mohan Kashyap

          * Aymeric Wibo

      * 了解 2023 年水印大学暑期实习生：Naman Sood

      * 了解 FreeBSD 基金会 2023 年暑期实习生：Jake Freeland

  * FreeBSD 在新闻中

      * FreeBSD 基金会加入 OSI 的开放政策联盟

      * Hackernoon：我们将开源 FreeBSD 作为企业操作系统的 5 个原因

      * What the Dev Podcast：FreeBSD 项目的演进。

我们通过出版专业制作的 FreeBSD Journal 来帮助世界了解 FreeBSD。正如我们之前提到的，FreeBSD Journal 现在是一份免费出版物。了解更多信息并访问最新期刊，请访问 https://www.freebsdfoundation.org/journal/。

您可以在 https://freebsdfoundation.org/our-work/events/ 上了解我们参加的事件以及即将举行的事件。

**操作系统改进**

在 2023 年第三季度，有 282 个 src、652 个 ports 和 24 个 doc 树提交被标识为 FreeBSD 基金会的赞助。其中一些基金会赞助的工作在单独的报告条目中有所描述：

  * 在使用日志软更新的文件系统上启用快照

  * 登录类修复和改进

  * OpenSSL 3 集成基础 — 改进

  * FreeBSD 上的 OpenStack

  * 进程可见性安全策略

  * amd64 的 SIMD 增强。

技术团队的成员参加了在葡萄牙科英布拉举行的 EuroBSDCon 2023。徐立文为新手提供了一个有助于贡献 FreeBSD 的教程。在大会之前，FreeBSD 开发者峰会举行，团队对他们最近的工作进行了简短的更新。

六个暑期实习或项目已经完成。

  * Jake Freeland 在夏季致力于一个 Capsicum 项目，用于跟踪违规行为，调整各种守护进程，如 syslogd(8)，并编写文档。

  * Naman Sood 主要从事与网络相关的各种任务。

  * 吴恩伟完成了另一个无线实习，改进和扩展 net80211(4) Wi-Fi 模拟器。

  * 王彦豪致力于一个文档和测试项目，例如构建在线手册编辑器并为一些用户空间工具添加测试用例。

  * Christos Margiolis 完成了他的项目，通过实现内联函数跟踪和将 kinst 移植到 arm64 和 riscv，改进了 kinst DTrace 提供程序。

  * 为了 FreeBSD 14.0 的准备，Muhammad Moinur（Moin）Rahman提交了超过 700 个用于受到最近的 OpenSSL 和 LLVM 更新影响的端口的修复或解决方案。

有关当前和过去的基金会承包工作的更多信息，请访问基金会项目页面。

以下是在本季度完成的其他基金会赞助的工作的一小部分：

  * 改进了 riscv64 CPU 的身份和特征检测

  * 从头开始重写 intro(9) 手册页

  * 在 hwpmc(4) 模块和 pmc(3) 库以及工具中进行了代码维护和错误修复

  * 在准备 FreeBSD 14.0 之前，提交了各种 freebsd-update(8) 修复

  * 向 LinuxKPI、iwlwifi 和 net802.11 代码提交了许多（37 个）更新和修复

  * 首先将 SSH 更新到 OpenSSH 9.3p2，然后是 9.4p1

  * 修补了 ssh-keygen，在无参数调用时生成 Ed25519 密钥

  * 添加了 Linux membarrier(2) 系统调用的清洁室实现

  * 在 amd64 和 arm64 上将 MAXCPU 增加到 1024

  * 为受影响的机器（通过 chicken bit）提交了自动防止 Zenbleed 不当行为/数据泄漏的修复

  * 对内核中整个调度优先级的使用进行了审查，以加强 rtprio() 系统调用并在某些情况下使其更有用。

**支持 FreeBSD 基础设施**

基金会提供硬件和两名员工来帮助支持 FreeBSD 集群。通过您的捐赠，基金会与集群管理团队协调购买了五台新的软件包构建服务器、三台新的 Web 服务器、一台新的防火墙/路由器、两个软件包镜像服务器和两台用于持续集成的新服务器。除了其中一个软件包镜像服务器外，所有新硬件将位于美国东海岸。

**持续集成和质量保证**

基金会提供一名全职员工和资金来支持 FreeBSD 项目的持续集成、自动化测试和整体质量保证工作。您可以在专门的报告条目中阅读有关持续集成工作的更多信息。

**法律/FreeBSD 知识产权**

基金会拥有 FreeBSD 商标，并且我们有责任保护这些商标。我们还为核心团队提供法律支持，以调查可能出现的问题。

请访问 https://freebsdfoundation.org 了解有关我们如何支持 FreeBSD 以及我们如何帮助您的更多信息！

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**FreeBSD 发布工程团队**

链接：

FreeBSD 14.0-RELEASE 计划 URL: https://www.freebsd.org/releases/14.0R/schedule/

FreeBSD 发布 URL: https://download.freebsd.org/releases/ISO-IMAGES/

FreeBSD 开发快照 URL: https://download.freebsd.org/snapshots/ISO-IMAGES/

联系方式：FreeBSD 发布工程团队，<re@FreeBSD.org>

FreeBSD 发布工程团队负责制定和发布 FreeBSD 官方项目发布的发布计划，宣布代码冻结并维护相应的分支，等等。

在今年的第三季度，FreeBSD 发布工程团队开始了即将到来的 14.0-RELEASE 循环的工作。截至目前，已发布了 BETA3 版本，BETA4 版本将很快发布。

发布工程团队继续为主分支和 stable/13 分支提供每周开发快照构建。

赞助商：Tarsnap
赞助商：https://www.gofundme.com/f/gjbbsd/
赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**持续集成**

链接：
FreeBSD Jenkins 实例 URL: https://ci.FreeBSD.org

FreeBSD CI Tinderbox 视图 URL: https://https://tinderbox.freebsd.org

FreeBSD CI 构件存档 URL: https://artifact.ci.FreeBSD.org

托管 CI Wiki URL: https://wiki.FreeBSD.org/HostedCI

第三方软件 CI URL: https://wiki.FreeBSD.org/3rdPartySoftwareCI

与 freebsd-testing@ 相关的工单 URL: https://bugs.freebsd.org/bugzilla/buglist.cgi?bug_status=open&email1=testing%40FreeBSD.org&emailassigned_to1=1&emailcc1=1&emailtype1=equals

FreeBSD CI 代码库 URL: https://github.com/freebsd/freebsd-ci

dev-ci 邮件列表 URL: https://lists.FreeBSD.org/subscription/dev-ci

联系方式：Jenkins 管理员 <jenkins-admin@FreeBSD.org>
联系方式：Li-Wen Hsu <lwhsu@FreeBSD.org>
联系方式：freebsd-testing 邮件列表
联系方式：IRC #freebsd-ci 频道（在 EFNet 上）

在2023年第三季度，我们与项目贡献者和开发人员合作，以满足其测试需求。与此同时，我们与外部项目和公司合作，通过在 FreeBSD 上进行更多测试来增强其产品。

重要的已完成任务：

  * 为 stable/14 分支添加作业

  * 更新 CI 结果的 "Tinderbox" 视图，现在包括测试结果和当前失败或不稳定系列的 "起点"。

  * 这主要由基金会实习生王彦豪完成。他的其他贡献在本报告的其他条目中。

正在进行中的任务：

  * 设计和实现预提交 CI 构建和测试以及基于 pull/merged-request 的系统（以支持工作流工作组的工作流程）

  * 概念验证系统正在进行中。

  * 设计和实现使用 CI 集群构建发行工件，就像发布工程一样

  * 简化贡献者和开发人员的 CI/测试环境设置

  * 设置 CI 阶段环境并在其中放置实验性作业

  * 改进硬件测试实验室并添加更多的测试硬件

  * 合并 https://reviews.freebsd.org/D38815

  * 合并 https://reviews.freebsd.org/D36257

打开或排队的任务：

  * 收集和整理 CI 任务和想法

  * 为运行测试的 VM 客户端设置公共网络访问

  * 实施使用裸金属硬件来运行测试套件

  * 添加针对 -CURRENT 的 drm 端口构建测试

  * 计划运行 ztest 测试

  * 帮助更多软件在其 CI 流水线中获得 FreeBSD 支持（Wiki 页面：
    3rdPartySoftwareCI，HostedCI）

  * 与托管 CI 提供商合作，以提供更好的 FreeBSD 支持

请查看与 freebsd-testing@ 相关的工单以获取更多进行中的信息，并请毫不犹豫地加入这一努力！
赞助商：FreeBSD 基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Ports Collection**

链接：

关于 FreeBSD Ports URL: https://www.FreeBSD.org/ports/

贡献到 Ports URL: https://docs.freebsd.org/en/articles/contributing/#ports-contributing

FreeBSD Ports Monitoring URL: http://portsmon.freebsd.org/

Ports Management Team URL: https://www.freebsd.org/portmgr/

Ports Tarball URL: http://ftp.freebsd.org/pub/FreeBSD/ports/ports/

联系方式：René Ladan <portmgr-secretary@FreeBSD.org>
联系方式：FreeBSD Ports 管理团队 <portmgr@FreeBSD.org>

Ports 管理团队负责监督 Ports 树的整体方向、构建软件包以及人事事务。以下是上一季度的情况。

  * 根据 INDEX，Ports 集合当前包含 34,600 个端口。当前有 3,000 个未解决的端口问题（PRs），其中大约有 730 个未分配。上一季度，在主分支上进行了 130 位贡献者的 11,454 次提交，2023Q3 分支上进行了 37 位贡献者的 828 次提交。与上一季度相比，这意味着未解决的 PR 数量略有减少，主分支上的提交数量增加了 10％，但季度分支上的回溯提交较少。端口数量也略有增长。

在第三季度，我们欢迎 Joel Bodenmann（jbo@）成为新的 Ports 提交者，并授予 mizhka@ 一个 ports 提交权限，他已经是一个 src 提交者，还在一年的不活跃后将 knu@ 和 uqs@ 的提交权限保存在安全中。

Portgmr 在第三季度讨论和处理了以下事项：

  * 在子软件包和 pizzamig@ 在 EuroBSDCon 上进行了闪电演讲

  * 对 Ports 树的某些部分进行了全面改进（LIB_DEPENDS、PREFIX、MANPREFIX、MANPATH）

支持 FreeBSD 13.1 的端口已从 Ports 树中删除，因为它于 8 月 1 日到达了生命周期终点。

基础设施方面发生了以下变化：

  * 添加了 ebur128 和 guile 的 USES

  * 将 Mono、Perl 和 PostgreSQL 的默认版本更新为分别为 5.20、5.34 和 15

  * 将 ebur128、guile 和 pycryptography 的默认版本分别添加到 "rust"、2.2 和 "rust"

  * 发生的主要端口更新包括：

      * 将 pkg 更新到 1.20.7

      * 将 chromium 更新到 117.0.5938.132

      * 将 Firefox 更新到 118.0.1

      * 将 KDE 更新到 5.27.8

      * 将 Rust 更新到 1.72.0

      * 将 Wine 更新到 8.0.2

在上一季度，pgkmgr@ 运行了 18 次 exp-runs，以测试各种端口升级、端口的默认版本更新以及对 pycryptography 的更改。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**项目**

这些项目跨足多个类别，涉及内核和用户空间，还包括Ports Collection或外部项目。

**填补FreeBSD桌面体验中的空白**

链接：

外部媒体管理器网址：https://github.com/outpaddling/qmediamanager

基于devd的自动挂载工具网址：https://github.com/outpaddling/devd-mount

SUID挂载工具网址：https://github.com/outpaddling/npmount

更新弹窗通知网址：https://github.com/outpaddling/freebsd-update-notify


联系人：Jason Bacon <jwb@FreeBSD.org>

已有十多年历史的sysutils/desktop-installer端口可以快速配置裸露的FreeBSD系统，配备任何桌面环境或窗口管理器。然而，FreeBSD基础和Ports Collection缺少一些用户在桌面操作系统中期望的常见功能。

desktop-installer电池监视脚本已经增强，以在不同电荷/放电水平时显示弹出通知。

deskutils/qmediamanager与sysutils/devd-mount和sysutils/npmount一起，在从devd接收到通知后挂载插入的媒体，并显示一个弹出窗口，为用户提供显示文件系统信息、打开文件管理器、重新格式化、将磁盘映像复制到设备或卸载等选项。它为处理外部媒体（如USB闪存驱动器）提供了一种便捷而安全的方式。

第四个新端口——deskutils/freebsd-update-notify——在新的基本更新可用或已经过可配置的时间限制时显示一个弹出窗口。如果用户选择进行更新，整个系统将使用auto-update-system(1)（sysutils/auto-admin的一个功能）进行更新，包括软件包、端口和基本系统。

这些新工具使FreeBSD桌面体验更接近于最受欢迎的桌面操作系统的便利性。

这些工具实际上是原型，稳定可靠，但需要审查。我们欢迎用户就默认行为和配置选项提供反馈。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**LLDB内核模块改进**

链接：

GSoC Wiki 项目网址：https://wiki.freebsd.org/SummerOfCode2023Projects/LLDBKernelModuleImprovement

项目代码库网址：https://github.com/aokblast/freebsd-src/tree/lldb_dynamicloader_freebsd_kernel

LLVM PullRequest 网址：https://github.com/llvm/llvm-project/pull/67106


联系人：洪晟毅 Sheng-Yi Hong <aokblast@FreeBSD.org>

在上一季度的报告中描述的LLDB内核模块改进项目实现了LLDB在FreeBSD内核上的DynamicLoader插件。

所有工作已经完成，也就是说，该插件可以正确加载从内核核心转储中提取的所有内核模块及其调试文件。

该插件已在x86-64平台上测试通过，用于可重定位类型内核模块，同时也在arm64（EC2）上测试通过，用于共享库类型的内核模块。这两个平台都表明该插件运作良好。

目前，该插件准备着陆到LLVM代码库中，通过LLVM PullRequest 进行提交。

赞助商：Google Summer of Code '23项目


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**用户空间**

指的是影响基本系统及其中程序的变更。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**OpenSSL 3在基本系统中的改进**

链接：

OpenSSL 下载网址：https://www.openssl.org/source/

联系人：Pierre Pronchery <pierre@freebsdfoundation.org>

这是对之前季度关于将 OpenSSL 3 集成到基本系统中的报告的跟进。

自上一份报告以来，最明显的更新无疑是3.0.10和随后的3.0.11发布，修复了一些低到中等严重性的CVE问题（CVE-2023-2975、CVE-2023-3446、CVE-2023-3817、CVE-2023-4807）。

然而，这并不是唯一的变更，本季度解决了一些与集成相关的问题，其中大部分是在使用基本系统中的OpenSSL 3构建端口时发现的。

修复包括：

  * 将引擎和传统提供程序与 libcrypto.so 共享对象链接，以确保符号的正确可见性，为此在构建系统中需要进行一些修改。

  * 修正FIPS提供程序的源文件列表。

  * 确保对已弃用的0.9.8 API的向后兼容性，这对于基于OpenSSH的ssh-agent(1)身份验证机制的安全/pam_ssh_agent_auth模块特别有帮助。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**登录类修复与改进**

链接：
审查堆栈的开始网址：https://reviews.freebsd.org/D40339

联系人：Olivier Certner <olce.freebsd.statusreports@certner.fr>

**背景**

登录类是一个主要用于在登录时根据登录用户和其所属登录类设置各种进程属性和属性的机制。登录类通常指定资源限制、环境变量和进程属性，如调度优先级和umask。有关更多信息，请参阅login.conf(5)。

**变更**

现在，优先级和umask功能现在接受特殊值inherit，以显式请求从登录过程继承属性。例如，在从具有非默认优先级的进程临时切换到另一个用户时，确保由该用户启动的进程仍具有相同的优先级级别。

用户现在可以在其本地配置文件（~/.login_conf）中覆盖全局设置的优先级功能（在/etc/login.conf中）。但请注意，如果用户没有特权，则不能增加其优先级，并且在这种情况下使用inherit没有意义，因为全局设置总是首先应用。

修复：

  * 修复一个错误，当优先级功能指定实时优先级时，使用的最终优先级存在偏差（实时类别中的数值最高优先级（31）永远无法设置）。

  * 安全性：防止setuid/setgid进程应用来自某个用户的~/.login_conf的指令（由于特权不足而无法应用的那里的指令在这样的进程中可能突然变得适用）。

我们还更新了相关手册页面，以反映新的功能，并改进了login.conf(5)中有关优先级和umask功能的描述。

**状态**

由于Konstantin Belousov和Warner Losh的帮助，该系列中的一些补丁已经得到了审查。其他补丁正在等待审查（和审查者，欢迎志愿者！），预计不会太费力。

我们计划通过弃用在未明确指定能力优先级的情况下将优先级重置为0的方式来提高一致性，这在umask的情况下已经存在了15多年。

赞助商：Kumacom SAS（用于开发工作）
赞助商：FreeBSD基金会（用于一些审查）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
**内核**

更新内核子系统/特性、驱动程序支持、文件系统等等。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
启用使用日志软更新的文件系统快照

联系人：Marshall Kirk McKusick <mckusick@FreeBSD.org>

该项目使得在运行时使用日志软更新时，UFS/FFS文件系统的快照功能得以实现。该项目的详细信息已在2022年第四季度报告中进行了描述。

该项目有两个关键阶段：

该项目的第一个阶段是在运行时启用使用日志软更新，并在活动文件系统上进行后台转储时，实现快照的功能。后台转储通过使用 -L 标志来请求 dump(8) 完成。该阶段于2022年第四季度完成，并在2023年第一季度报告中描述后，作为13.2版本的一部分提供。

该项目的第二个阶段是在运行时使用日志软更新的文件系统上，通过快照进行后台检查。该阶段于2023年第三季度完成，及时纳入14.0版本的发布。它也作为13.2-STABLE版本的一部分提供。

赞助方：FreeBSD基金会
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
FreeBSD内核的SquashFS驱动程序

链接：

维基页面URL: https://wiki.freebsd.org/SummerOfCode2023Projects/PortSquashFuseToTheFreeBSDKernel

源代码URL: https://github.com/Mashijams/freebsd-src/tree/gsoc/testing


联系人：Raghav Sharma <raghav@FreeBSD.org>

本季度，我们完成了内核的SquashFS驱动程序工作。我们现在可以在FreeBSD 13.2-RELEASE或更高版本上挂载SquashFS存档，并执行所有基本的只读文件系统操作。

代码工作包括：

- 为目录读取支持实现vop_lookup()和vop_readdir()挂钩。
- 为文件读取支持实现vop_read()和vop_strategy()挂钩。
- 为符号链接读取支持实现vop_readlink()挂钩。

我们还为SquashFS实现了扩展属性接口函数。现在剩下的工作是实现它们的内核接口挂钩。

还进行了许多错误修复。一个主要问题是找出为什么我们无法列出根目录的第一个条目，结果发现SquashFS的inode_number可能为零，而内核因某种原因在列举dirents时跳过了它。目前，我们通过将虚构的inode_number传递给dirent，而不是零，来解决了这个问题。

代码审查目前正在进行中，由我的导师Chuck Tuffli负责。

我很高兴地宣布，SquashFS将在即将发布的FreeBSD版本中找到它的位置。

赞助方：Google Summer of Code 2023计划
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**进程可见性安全策略**

链接：

审查堆栈的开始网址：https://reviews.freebsd.org/D40626


联系人：Olivier Certner <olce.freebsd.statusreports@certner.fr>

**背景**

FreeBSD实现了三种内置的安全策略，限制了特定用户能够看到哪些进程，旨在防止信息泄漏和不必要的交互。

第一种可以防止非特权用户看到或与其真实UID不匹配的进程进行交互。可以通过将sysctl security.bsd.see_other_uids设置为0来激活（默认为1）。

第二种可以防止非特权用户看到或与其凭据中没有用户是其成员的任何组的进程进行交互。可以通过将sysctl security.bsd.see_other_gids设置为0来激活（默认为1）。

第三种可以防止非特权用户的进程看到或与作为前者的严格子监狱中的进程进行交互。监狱子系统已经阻止这样的进程查看不是其自身后代的监狱中的进程（参见jail(8)，特别是"Hierarchical Jails"部分）。这种策略的一个可能用途是与上述第一种策略一起，隐藏具有与祖先监狱中的某个用户相同真实UID的子监狱中的进程，因为在这些不同的监狱中具有相同UID的用户在逻辑上被视为不同的用户。可以通过将sysctl security.bsd.see_jail_proc设置为0来激活（默认为1）。

在审查这些策略的代码并进行实际测试后，我们注意到了一些问题和限制，这促使我们对这个主题进行工作。

**变更**

由security.bsd.see_jail_proc sysctl控制的策略已经接收了以下修复和改进：

  * 加强security.bsd.see_jail_proc策略，防止未经授权的用户尝试随机杀死、更改优先级或调试在子监狱中具有相同（真实）UID的进程，即使这些进程对他们不可见，只要正确猜测了这样的进程的PID，就会成功。

  * 使此策略可以被MAC策略覆盖，就像其他策略一样。

由security.bsd.see_other_gids控制的策略已经修复，以考虑进程的真实组而不是其有效组，从而确定试图访问该进程的用户是否是该进程的任何组的成员。其理念是，一些用户应该继续看到它们启动的进程，即使它们通过setgid位获得了进一步的特权。反之，他们不应该看到由特权用户启动的暂时加入用户主要组的进程。这种新行为与security.bsd.see_other_uids一直在为用户ID（即考虑某个进程的真实用户ID而不是有效ID）执行的操作是一致的。

我们已更新与这些安全策略相关的手册页面，包括security(7)，sysctl(8)和ptrace(2)。一些实施或利用这些策略的内部功能的手册页面也进行了翻新。

**状态**

在Mitchell Horne、Pau Amma、Benedict Reuschling和Ed Maste的帮助下，大部分提交的更改已经得到审查和批准，因此它们应该很快就会到达树中。该补丁系列始于审查D40626。从那里，点击"Stack"选项卡，以查看实施更改的所有审查列表。

作为后续步骤，我们正在考虑默认情况下打开security.bsd.see_jail_proc策略（即，sysctl的默认值将变为0），除非有异议。

赞助商：Kumacom SAS（用于开发工作）
赞助商：FreeBSD基金会（用于大部分审查）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Linux兼容层更新**

链接：

Linuxulator状态Wiki页面网址：https://wiki.freebsd.org/Linuxulator

Linux应用程序状态Wiki页面网址：https://wiki.freebsd.org/LinuxApps



联系人：Dmitry Chagin <dchagin@FreeBSD.org>

该项目的目标是改进FreeBSD执行未修改的linux(4)二进制文件的能力。

截至22dca7acf775，已实现xattr系统调用。这使得可以使用Linux rsync。

截至bbe017e0415a，已实现ioprio系统调用。这使得可以使用debootstrap在Ubuntu 23.04中进行操作。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**架构**

更新特定平台的功能并为新的硬件平台提供支持。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**NXP DPAA2支持**

链接：
FreeBSD源代码树中的DPAA2网址：https://cgit.freebsd.org/src/tree/sys/dev/dpaa2
GitHub上的DPAA2网址：https://github.com/mcusim/freebsd-src

联系人：Dmitry Salychev <dsl@FreeBSD.org>
联系人：Bjoern A. Zeeb <bz@FreeBSD.org>

**什么是DPAA2？**

DPAA2是一种硬件级别的网络架构，存在于一些NXP SoCs中，包括硬件块，包括管理复杂（MC，用于操作DPAA2对象的命令接口）、线速I/O处理器（WRIOP，数据包分发、排队、丢弃决策）、队列和缓冲管理器（QBMan，Rx/Tx队列控制、Rx缓冲池）等。管理复杂运行由NXP提供的固件，该固件提供DPAA2对象作为对这些块的抽象层，以简化对底层硬件的访问。

**与上一份报告的变更**

  * 改善了DPAA2通道之间的隔离。

  * 在大量网络负载下修复了恐慌。

  * FDT/ACPI MDIO支持。

  * NFS根挂载在通过DPAA2进行网络引导时不再挂起。

  * 驱动程序开始通过自己的命令门户（DPMCP）与MC进行通信。

  * 所有已关闭问题的列表。

**正在进行的工作**

开始在dev/sff上进行工作，以支持SFF/SFP模块，以便在1 Gbit/s以上的链路上测试DPAA2驱动程序。

**计划**

  * 大量网络负载测试（2.5 Gbit/s，10 Gbit/s）和瓶颈缓解。

  * 带有缓存的内存支持的软件门户。

  * 驱动程序资源释放以正确卸载dpaa2.ko。

  * 进一步支持硬件的其他部分（DPSW、DCE等）。

赞助商：Traverse Technologies（提供Ten64硬件进行测试）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**为amd64进行的SIMD增强**

链接：

项目提案网址：http://fuz.su/~fuz/freebsd/2023-04-05_libc-proposal.txt

simd(7)网址：https://man.freebsd.org/cgi/man.cgi?query=simd&sektion=7&manpath=FreeBSD+15.0-CURRENT



联系人：Robert Clausecker <fuz@FreeBSD.org>

SIMD指令集扩展，如SSE、AVX和NEON，在现代计算机上是普遍存在的，对许多应用程序提供性能优势。该项目的目标是提供常见libc函数（主要是在string(3)中描述的函数）的SIMD增强版本，加速大多数C程序。

对于每个经过优化的函数，将提供最多四个实现：

  * 一个标量实现，针对amd64进行了优化，但没有使用任何SIMD，

  * 一个基线实现，使用SSE和SSE2，或者一个使用所有SSE扩展直到SSE4.2的x86-64-v2实现，

  * 一个使用AVX和AVX2的x86-64-v3实现，

  * 一个使用AVX-512F/BW/CD/DQ的x86-64-v4实现。

用户将能够通过设置ARCHLEVEL环境变量来选择使用哪个级别的SIMD增强。

尽管当前项目只涉及amd64，但未来可能会扩展到其他架构，如arm64。

在过去的几个月里，该项目取得了显著的进展。已经实现了bcmp(3)、index(3)、memchr(3)、memcmp(3)、stpcpy(3)、strchr(3)、strchrnul(3)、strcpy(3)、strcspn(3)、strlen(3)、strnlen(3)和strspn(3)的SIMD增强版本。函数memcpy(3)、memmove(3)、strcmp(3)、timingsafe_bcmp(3)（参见D41673）和timingsafe_memcmp(3)（参见D41696）正在进行中。不幸的是，该工作没有进入FreeBSD 14.0的发布版本，但计划作为FreeBSD 14.1的一部分。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**将mfsBSD集成到发布构建工具中**

链接：

Wiki文章网址：https://wiki.freebsd.org/SummerOfCode2023Projects/IntegrateMfsBSDIntoTheReleaseBuildingTools

Phabricator上的代码审查网址：https://reviews.freebsd.org/D41705

FreeBSD基金会博客文章网址：https://freebsdfoundation.org/blog/meet-the-2023-freebsd-google-summer-of-code-students-soobin-rho/


联系人：Soobin Rho <soobinrho@FreeBSD.org>

**什么是mfsBSD？**

"mfsBSD是一个用于创建基于mfsroot的小巧但功能齐全的FreeBSD分发的工具集，它将所有文件存储在内存（MFS）[内存文件系统]中，并从硬盘、USB存储设备或光盘加载。它可用于各种用途，包括无盘系统、恢复分区以及远程覆盖其他操作系统。"

Martin Matuška是mfsBSD的创作者。他还是原始的（2009年）mfsBSD白皮书的作者，上面的摘录就来自于该白皮书。上游mfsBSD在GitHub上的仓库中进行维护。

**该项目的目的**

此项目将mfsBSD集成到FreeBSD发布工具集中，在/usr/src/release/Makefile中创建mfsBSD映像（.img和.iso文件）的附加目标。在集成之前，mfsBSD仅存在于FreeBSD发布工具链之外，并且仅生成-RELEASE版本。

通过此项目，mfsBSD映像将在官方FreeBSD发布页面上可用。您还可以通过调用cd /usr/src/release && make release WITH_MFSBSD=1来构建mfsBSD，然后将在/usr/obj/usr/src/${ARCH}/release/中创建mfsbsd-se.img和mfsbsd-se.iso。

**与上一季度相比的变化**

代码已经准备就绪，目前正在进行审查。如果您希望参与审查过程，请随时参与！这是我的修订。

赞助商：Google，Inc.（GSoC 2023）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**云**

更新云特定功能，并为新的云平台提供支持。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**在FreeBSD上运行OpenStack**

链接：

OpenStack网址：https://www.openstack.org/

FreeBSD上的OpenStack网址：https://github.com/openstack-on-freebsd



联系人：Chih-Hsin Chang <starbops@hey.com>
联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

OpenStack是一个开源的云操作系统，用于在云平台上部署各种资源类型。然而，挑战在于在FreeBSD主机上运行OpenStack的控制平面。我们项目的使命是使FreeBSD能够无缝地作为OpenStack主机运行。

在本季度，我们重点关注整个概念验证（POC）的最后一部分，即VM控制台集成。目标是让用户通过OpenStack客户端获取串行控制台，以访问运行在基于FreeBSD的OpenStack集群上的VM实例。这也很重要，因为我们目前没有Neutron中托管DHCP服务的端口。用户需要手动配置VM实例的正确IP地址，以确保网络连通性。然而，bhyve(8)不会本地公开串行控制台，因此我们需要通过网络导出nmdm(4)设备。这是通过一个名为socat-manager的自定义代理完成的，是的，我们利用socat(1)监听由OpenStack nova-compute分配的特定端口，以集成到其工作流程中。借助另一个关键部分，即用于bhyve的自定义Libvirt挂钩，我们可以连接两个端点，并使控制台对用户可访问。在编写挂钩脚本的过程中，我们发现Libvirt专门为bhyve提供的挂钩接口实现不好。幸运的是，Libvirt的开发人员迅速修复了这个问题，我们计划在将来的版本中发布此修复时进一步完善我们的挂钩脚本。

我们还解决了在上一季度报告中提到的开发环境中的嵌套bhyve问题（在Linux KVM之上运行bhyve VM）。这是由于两个VT-x功能的APIC仿真引起的：VID和PostIntr。

我们主机的CPU具有这两个功能，因此我们需要在L1 guest（充当bhyve主机的角色）中禁用它们，以使L2 guest不挂起。对我们来说，在完全虚拟化的环境中进行项目工作至关重要，因为缺乏物理资源。这对于对项目感兴趣的人来说可能同样重要，降低了在其环境中尝试或验证整个POC的门槛，而无需太高的设置要求。

展望第四季度，我们的重点是通过修订文档和移植到FreeBSD 14.0-RELEASE来完成POC。缺少相应FreeBSD软件包的依赖关系将逐个移植。我们还计划将我们的工作重新基于OpenStack 2023.1 Antelope。我们邀请对此项目感兴趣的人探索我们的文档，并为该项目的成功做出贡献。

赞助商：FreeBSD基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**FreeBSD在Microsoft HyperV和Azure上的支持**

链接：

FreeBSD维基上有关Microsoft Azure的文章网址：https://wiki.freebsd.org/MicrosoftAzure

FreeBSD维基上有关Microsoft HyperV的文章网址：https://wiki.freebsd.org/HyperV



联系人：Microsoft FreeBSD Integration Services Team <bsdic@microsoft.com>
联系人：freebsd-cloud邮件列表
联系人：FreeBSD Azure Release Engineering Team <releng-azure@FreeBSD.org>
联系人：Wei Hu <whu@FreeBSD.org>
联系人：Souradeep Chakrabarti <schakrabarti@microsoft.com>
联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

在这个季度，我们主要致力于ARM64体系结构的支持，以及构建并将基于UFS和ZFS的映像发布到Azure社区库。在项目的测试公共库中有一些可用的测试映像，名为FreeBSDCGTest-d8a43fa5-745a-4910-9f71-0c9da2ac22bf：

  * FreeBSD-CURRENT-testing

  * FreeBSD-CURRENT-gen2-testing

  * FreeBSD-CURRENT-arm64-testing

  * FreeBSD-CURRENT-zfs-testing

  * FreeBSD-CURRENT-zfs-gen1-testing

要使用它们，在创建虚拟机时：

 1. 在选择映像步骤中，选择Other items中的Community Images

 2. 搜索FreeBSD

我们的目标是为14.0-RELEASE提供所有这些映像。

正在进行的工作任务：

  * 自动化映像构建和发布过程，并合并到src/release/。

  * 将所有支持的VM映像构建并发布到Azure Marketplace

  * 将快照构建并发布到Azure社区库

上述任务由FreeBSD基金会赞助，由Microsoft提供资源。

Wei Hu和Souradeep Chakrabarti已经在arm64中修复了一些关键错误：

  * https://bugs.freebsd.org/267654

  * https://bugs.freebsd.org/272461

  * https://bugs.freebsd.org/272666

根本原因在e7a9817b8d32中得到了确认并修复：Hyper-V: vmbus:在vmbus中实现bus_get_dma_tag

并继续努力改进Microsoft Azure Network Adapter（MANA）的支持。

未完成的任务：

  * 在Microsoft Learn上更新有关FreeBSD的文档

  * 在Azure Pipelines中支持FreeBSD

  * 将Azure代理端口更新到最新版本

  * 上游Azure代理的本地修改

赞助商：对于Microsoft内部的人员以及其余人员的资源，由Microsoft提供；对于其他一切，由FreeBSD基金会提供。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD在EC2上**

链接：

FreeBSD/EC2 Patreon网址：https://www.patreon.com/cperciva


联系人：Colin Percival <cperciva@FreeBSD.org>

FreeBSD可以在x86（Intel和AMD）和ARM64（Graviton）EC2实例上使用。正在进行的工作确保未来的实例类型将得到支持。

每周的FreeBSD快照现在包括14.0和15.0的实验性ZFS根AMI。这一变更将在FreeBSD 14.0-RELEASE中存在。

正在进行的工作是开始发布实验性的“cloud-init” AMI。预计将在FreeBSD 14.0-RELEASE发布时推出。

这项工作得到了Colin的FreeBSD/EC2 Patreon的支持。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**文档**

文档树、手册页面或新的外部书籍/文档中的重要变更。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**文档工程团队**


链接：FreeBSD文档项目 URL：https://www.freebsd.org/docproj/

链接：FreeBSD文档项目新贡献者入门指南 URL：https://docs.freebsd.org/en/books/fdp-primer/

链接：文档工程团队 URL：https://www.freebsd.org/administration/#t-doceng

联系方式：FreeBSD文档工程团队 <doceng@FreeBSD.org>

doceng@ 团队是一个负责处理与FreeBSD文档项目相关的一些元项目问题的组织；更多信息，请参阅FreeBSD Doceng Team章程。

在本季度：

  * 文档门户的搜索功能已从DuckDuckGo迁移到我们自己的搜索引擎；更多信息，请参阅此提交

  * 根据grahamperrin@的要求，他的文档提交权限已被保留

  * 根据pluknet@的要求，他的文档提交权限已被保留。

**Porter's Handbook**

Handbook中已添加新的USES标志：

  * USES= ebur128。

  * USES= guile。

**FreeBSD在Weblate上的翻译**

链接：在Weblate上翻译FreeBSD URL：https://wiki.freebsd.org/Doc/Translation/Weblate
链接：FreeBSD Weblate实例 URL：https://translate-dev.freebsd.org/

2023年第三季度状态

  * 17个团队语言

  * 189名注册用户

有四名新的翻译者加入了Weblate：

  * minso，韩语（ko）和法语（fr_FR）

  * strgalt-t，德语（de_DE）

  * bsdmeg，德语（de_DE）

  * mvsf，葡萄牙语（pt_BR）

语言

  * 中文（简体）（zh-cn）（进度：7%）

  * 中文（繁体）（zh-tw）（进度：3%）

  * 荷兰语（nl）（进度：1%）

  * 法语（fr）（进度：1%）

  * 德语（de）（进度：1%）

  * 印尼语（id）（进度：1%）

  * 意大利语（it）（进度：5%）

  * 韩语（ko）（进度：33%）

  * 挪威语（nb-no）（进度：1%）

  * 波斯语（fa-ir）（进度：2%）

  * 波兰语（进度：1%）

  * 葡萄牙语（进度：0%）

  * 葡萄牙语（pt-br）（进度：22%）

  * 西班牙语（es）（进度：35%）

  * 土耳其语（tr）（进度：2%）

我们要感谢所有为翻译或审阅文档作出贡献的人。

请帮助在您的本地用户组推广这个努力，我们始终需要更多志愿者。

**FreeBSD Handbook工作组**

联系人：Sergio Carlavilla <carlavilla@FreeBSD.org>

  * 网络章节已重写

  * Jails章节已重写

  * 下一步要着手处理的部分将是文件系统部分：UFS、OpenZFS、其他文件系统。

**FAQ工作组**

联系人：Sergio Carlavilla <carlavilla@FreeBSD.org>

这个工作组的目标是编写一个新的常见问题解答（FAQ）。将会与FreeBSD 14.0一同发布。

**FreeBSD网站改版 - WebApps工作组**

联系人：Sergio Carlavilla <carlavilla@FreeBSD.org>

负责创建新的FreeBSD文档门户并重新设计FreeBSD主网站及其组件的工作组。FreeBSD开发者可以在FreeBSD Slack频道#wg-www21中关注并加入工作组。工作将分为三个阶段：

 1. 在Web上重新设计手册页

    使用mandoc生成HTML页面的脚本。（已完成，已获Doceng批准，部署日期尚未确定）公共实例在https://man-dev.FreeBSD.org上

 2. 在Web上重新设计FreeBSD主网站

    新设计，响应式和深色主题。（几乎完成，在EuroBSDCon上展示）

 3. 在Web上重新设计Ports页面

    用于创建应用程序门户的Ports脚本。（进行中）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD在线编辑器和手册页编辑器**

链接：

FreeBSD在线文档编辑器 URL: https://github.com/Wang-Yan-Hao/FreeBSD-Online-Document-Editor

FreeBSD在线手册页编辑器 URL: https://github.com/Wang-Yan-Hao/man_page_editor

联系人：Yan-Hao Wang <bses30074@gmail.com>
联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

目前，我们的文档翻译过程涉及使用Weblate和直接编辑文档存储库。我们意识到这个过程可能有些繁琐，因此我们正在努力提供一种更方便的替代方案，类似于维基社区的做法。介绍一下在线文档编辑器和手册页编辑器，这是一个用户友好的所见即所得（WYSIWYG）静态站点，专为翻译文档和手册页而设计。我们的目标是将所有翻译功能集中在一个平台上，使翻译过程尽可能简单。

然而，我们仍然需要这两个项目的帮助，具体如下：

 1. 文档编辑器和手册页编辑器是使用简单的JavaScript开发的。我们正在寻找一位Web开发人员来评估代码的效率，因为我（Yan-Hao Wang）在前端开发方面不是很熟练。

 2. 我们还在寻找一位网络安全开发人员，协助我们识别和解决这两个项目中的安全问题。这对于确保这些项目的安全托管并减轻任何潜在漏洞至关重要。

 3. 由于目前没有现成的JavaScript库来渲染mandoc，我不得不创建自己的库。然而，在编辑过程中仍然存在一些隐藏的错误。我们需要一位JavaScript开发人员来帮助纠正这些渲染问题。

赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD专家系统**

链接：

FreeBSD专家系统 URL: https://github.com/Wang-Yan-Hao/freebsd_expert_system


联系人：Yan-Hao Wang <bses30074@gmail.com>
联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

在今天的世界中，机器学习和深度学习技术变得越来越普遍，就像ChatGPT的普及一样。我们正在开发一个ChatGPT插件，可以访问最新的FreeBSD数据，将ChatGPT转变为一个FreeBSD专家系统。我们已经脚本化了数据清理，并建立了一个嵌入式模型来搜索相关信息。

然而，我们在这个项目中需要以下方面的帮助：

  * 虽然我不是机器学习或深度学习方面的专家，但我们在这些领域遇到了许多挑战，比如数据清理的充分性以及最终插件开发过程中的不确定性。我们将不胜感激地接受在这方面的指导。

赞助商：FreeBSD基金会


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Ports**

涉及Ports集合的变更，无论是触及大部分树木的全面变更，还是影响个别端口本身的变更。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**KDE在FreeBSD上**

链接：

KDE/FreeBSD计划 URL: https://freebsd.kde.org/

FreeBSD — KDE社区维基 URL: https://community.kde.org/FreeBSD


联系人：Adriaan de Groot <kde@FreeBSD.org>

KDE在FreeBSD项目中为FreeBSD ports树打包了CMake、Qt和来自KDE社区的软件。该软件包括一个名为KDE Plasma的完整桌面环境（适用于X11和Wayland），以及数百个可在任何FreeBSD机器上使用的应用程序。

KDE团队（kde@）是desktop@和x11@的一部分，构建软件堆栈，使FreeBSD成为一个美观且可用作每日驱动的图形桌面工作站的平台。下面的说明主要描述了KDE的端口，但也包括对整个桌面堆栈重要的项目。

**基础设施**

Qt5现在处于长期支持状态，只偶尔更新。在本季度更新到了5.15.10。Qt6现在以常规的上游发布更新，7月底发布了6.5.2版本，随后是6.5.3。

本季度CMake没有更新，因此我们现在至少滞后了一个次要版本。最新版本的更改日志对FreeBSD没有太多内容，因此没有特殊原因升级。

sysutils/polkit和sysutils/consolekit2都得到了更新，为FreeBSD桌面提供了改进的安全策略和控制台处理。x11/sddm已更新，提供更好的图形登录管理器。

multimedia/pipewire更新到了0.3.81版本。这为KDE和GNOME等桌面提供了多媒体支持。

**KDE堆栈**

KDE Gear每个季度发布一次，KDE Plasma每月更新一次，KDE Frameworks每月发布一次。这些（大型）更新在上游发布后不久就会到来，不会单独列出。

  * KDE Frameworks达到了5.110版本。KDE Frameworks 5系列正在逐渐结束，尽管在上游进入长期支持之前还需要大约六个月。

  * KDE Plasma桌面更新到了5.27.8版本。与框架一样，上游对KDE Plasma 5的工作正在减少，以支持KDE Plasma 6。

  * KDE Gear更新到了23.08.1。

**相关端口**

KDE生态系统包括各种端口，大多由kde@维护，都构建在共享的Qt和KDE Frameworks基础上。kde@团队会根据需要更新它们。例如，在本季度，tcberner@和arrowd@更新或修复了以下（远不止）这些端口的选择：

  * astro/merkaartor

  * devel/massif-visualizer

  * finance/alkimia

  * irc/quassel

  * net-im/kaidan

  * sysutils/bsdisks

  * sysutils/k3b

感谢jhale@，devel/qtcreator已更新到11.0.3，提供了另一个功能丰富的集成开发环境，用于创建Qt和KDE应用程序。

**弃用**

Web浏览器庞大，具有相当大的安全表面。备受尊敬的www/qt5-webkit WebKit端口已被计划移除，并且使用者已被迁移到WebEngine。我们依赖的WebKit分支已不再得到积极维护。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD上的Pantheon桌面**

链接：

elementary OS URL: https://elementary.io/

开发存储库 URL: https://codeberg.org/olivierd/freebsd-ports-elementary


联系人：Olivier Duchateau <duchateau.olivier@gmail.com>

Pantheon桌面环境是为elementary OS设计的。它基于GNOME技术（如Mutter、GTK 3和4），并用Vala编写。其目标是为终端用户提供完整的桌面环境。

要求13.2-RELEASE或更高版本，因为一些核心组件依赖于deskutils/xdg-desktop-portal。

存储库包含一个名为elementary.mk的Mk/Uses框架文件，官方应用程序以及依赖于x11-toolkits/granite7的精选端口。

我已经提交了几个补丁，以保持这些端口的最新状态：

  * deskutils/iconbrowser

  * multimedia/elementary-videos

  * x11-themes/gnome-icons-elementary

  * editors/elementary-code

以下端口的更新bug报告仍然在bugzilla上开放：

  * x11-toolkits/granite7: 更新到7.3.0

  * deskutils/elementary-calendar: 更新到7.0.0

  * x11/elementary-terminal: 更新到6.1.2

与此同时，我还致力于更新GNOME堆栈（特别是WebKitGTK、libwnck、Mutter、Vala）。我注意到了一些回归问题，特别是与x11/plank（与监视打开的应用程序有关）有关。

在开发存储库中添加了三个新应用程序：

  * deskutils/atlas，地图查看器

  * deskutils/nimbus，天气小部件

  * audio/leopod，播客客户端


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD办公团队**

链接：

FreeBSD办公项目 URL: https://wiki.freebsd.org/Office

FreeBSD办公邮件列表 URL: https://lists.freebsd.org/subscription/freebsd-office


联系人：FreeBSD办公团队邮件列表 <office@FreeBSD.org>
联系人：Dima Panov <fluffy@FreeBSD.org>
联系人：Li-Wen Hsu <lwhsu@FreeBSD.org>

FreeBSD办公团队致力于开发一系列与办公相关的软件套件和工具，如OpenOffice和LibreOffice。

在本季度，我们的工作重点是为所有FreeBSD用户提供最新的LibreOffice套件及其伴随应用的稳定版本。

在2023年第三季度，我们推送了LibreOffice端口的维护补丁，并将最新的7.6.2版本以及所有伴随库，如MDDS、libIxion等，引入了Ports树。所有LibreOffice端口的预发布开发都在LibreOffice WIP存储库中进行。

除了LibreOffice，我们还将Boost更新到最新的1.83版本。所有对Boost的端口感兴趣的人都可以向Boost WIP存储库提交补丁。

我们正在寻找愿意协助完成以下任务的人：

  * 开放的错误列表包含所有需要关注的已提交问题

  * 在Ports中上游本地补丁

欢迎在邮件列表和Bugzilla中提交补丁、评论和异议。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**Wifibox：使用Linux驱动FreeBSD上的无线网卡**

链接：

项目GitHub页面 URL: https://github.com/pgj/freebsd-wifibox

net/wifibox端口 URL: https://cgit.freebsd.org/ports/tree/net/wifibox


联系人：PÁLI Gábor János <pali.gabor@gmail.com>

Wifibox是一个实验性项目，旨在探索在FreeBSD主机系统上部署虚拟化Linux客户机以驱动无线网络卡的方法。已经有一些指南描述了如何手动设置此项功能，而Wifibox旨在将这些想法实现为一个易于使用的单一软件包。

  * 它使用bhyve(8)运行嵌入式Linux系统。这有助于实现低资源占用。它需要带有I/O MMU（AMD-Vi、Intel VT-d）的x64 CPU，约150 MB物理内存，以及一些用于虚拟磁盘映像的磁盘空间，具体取决于特定情况可能仅为约30 MB。它适用于FreeBSD 12及更高版本，但某些卡可能需要FreeBSD 13。

  * 客户机使用Alpine Linux构建，这是一个以musl libc和BusyBox为基础的面向安全、轻量级的分发，其中包含从Arch Linux导入的一些自定义扩展和补丁。它附带了一些诊断工具，以更好地管理正在使用的硬件。最新版本使用Linux 6.1，但也提供Linux 6.5作为替代选择。

  * 配置文件与主机系统共享。客户机使用wpa_supplicant(8)或hostapd(8)（取决于配置），因此可以导入主机的wpa_supplicant.conf(5)或hostapd.conf(5)文件而无需更改。

  * 配置后，wpa_supplicant(8)和hostapd(8)控制套接字可以由客户机暴露，从而使主机可以直接使用相关工具，如来自net/wpa_supplicant_gui包的wpa_cli(8)或wpa_gui(8)，或hostapd_cli(8)。

  * 一切都打包在一个可以轻松安装和卸载的软件包中。这带有一个rc(8)系统服务，它在启动时自动启动客户机，并在关闭时停止它。

  * 它可以配置为转发IPv6流量，这目前是一个实验性选项，但默认已打开。

Wifibox主要经过Intel芯片组的测试，表现出色且稳定。因此，在FreeBSD对这些芯片组的支持成熟之前，它可能作为一种临时解决方案。

已确认Wifibox也适用于Atheros、Realtek和Mediatek芯片组，对其他芯片组的反馈更是欢迎。Broadcom芯片（通常在MacBook Pro上找到）也可以工作，但已知存在稳定性问题。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**在FreeBSD上的GCC**


链接：

GCC 项目 URL: https://gcc.gnu.org/

GCC 10 发布系列 URL: https://gcc.gnu.org/gcc-10/

GCC 11 发布系列 URL: https://gcc.gnu.org/gcc-11/

GCC 12 发布系列 URL: https://gcc.gnu.org/gcc-12/

GCC 13 发布系列 URL: https://gcc.gnu.org/gcc-13/




联系人：Lorenzo Salvadore <salvadore@FreeBSD.org>

将GCC默认版本更新到GCC 13的过程已经开始，通过进行了exp-run。感谢运行exp-run的Antoine Brodin以及所有其他参与其中的开发人员和端口维护者。

相同的exp-run包含了上个季度状态报告中提前预期的额外补丁。特别是，它包含了更新：

  * lang/gcc11 到版本11.4.0的补丁；

  * lang/gcc12 到版本12.3.0的补丁；

  * lang/gcc13 到版本13.2.0的补丁。

读者可能还记得我计划在GCC 13.1.0发布后立即将GCC默认版本更新为GCC 13，但正如可以注意到的，GCC开发人员发布GCC 13.2.0的速度比我在进行GCC端口的工作要快。

在exp-run中报告的大多数错误都是相同的错误：error: 在 '__is_convertible' 之前预期标识符。似乎问题是FreeBSD 12的libcxx和GCC 13头文件之间的不兼容性。请查看exp-run中的讨论以获取更多信息并提供反馈。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**Valgrind：valgrind-devel 已更新，适用于 FreeBSD 15**

链接：

Valgrind 主页 URL: https://www.valgrind.org/

Valgrind 新闻 URL: https://www.valgrind.org/docs/manual/dist.news.html


联系人：Paul Floyd <pjfloyd@wanadoo.fr>

devel/valgrind-devel 正在更新中。这包含了将于十月发布的 Valgrind 3.22 官方版本的大部分内容。

memcheck 已经通过一些额外的检查进行了增强。现在，它将报告使用大小为零的 realloc。这样的使用是不可移植的，已被弃用（C23 将使其成为未定义行为）。memcheck 现在验证了用于 memalign、posix_memalign、aligned_alloc 以及所有 operator new 和 operator delete 的对齐和大小删除的值。现在以一种懒惰的方式读取 DWARF 调试信息，这可以提高性能。

像往常一样，有许多小的错误修复。

针对 FreeBSD 的特定更新包括对 FreeBSD 15 的支持。现在支持两个额外的 _umtx_op 操作，UMTX_OP_GET_MIN_TIMEOUT 和 UMTX_OP_SET_MIN_TIMEOUT。修复了对 sysctl kern proc pathname 使用 guest pid 或 -1 时的问题，之前返回 Valgrind 主机的路径。现在 sysctl 将返回 guest 的路径。还添加了对 close_range 系统调用的支持。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**GitLab 16.3 已发布**

链接：
Gitlab 16.3 新功能 URL: https://about.gitlab.com/releases/2023/08/22/gitlab-16-3-released/

联系人：Matthias Fechner <mfechner@FreeBSD.org>

GitLab是一个DevOps平台，它带来了速度和信心、安全而无损、以及对DevOps成功的可见性。

版本16.3现在已在FreeBSD上可用：请查看 www/gitlab-ce 端口。升级非常重要，因为所有后续升级都将需要版本16.3。只有从 GitLab 16.3 才能升级到 16.4。

安装文档可以在 https://gitlab.fechner.net/mfechner/Gitlab-docu/-/blob/master/install/16.3-freebsd.md?ref_type=heads 找到。升级文档可以在 https://gitlab.fechner.net/mfechner/Gitlab-docu/-/blob/master/update/16.1-16.3-freebsd.md?ref_type=heads 找到。

我将等待升级到 16.4（大约在 20.9 或 22.9 发布，不确定），直到创建 ports 季度分支 2023Q4，以避免破坏不使用主分支（latest）的系统。GitLab 用户应始终选择主分支，如安装手册中所述。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**PortOptsCLI — 端口集合可访问性**

链接：

项目仓库 URL: https://gitlab.com/alfix/portoptscli

联系人：Alfonso Sabato Siciliano <asiciliano@FreeBSD.org>
联系人：FreeBSD 可访问性邮件列表 <freebsd-accessibility@FreeBSD.org>

FreeBSD提供了Ports Collection，以便用户和管理员可以简单地安装应用程序。在构建和安装之前，可以配置端口。命令 make config 使用 ports-mgmt/dialog4ports 和 ports-mgmt/portconfig 通过文本用户界面（TUI）交互式设置端口。

不幸的是，屏幕阅读器在TUI上的性能表现不佳；这是一个众所周知的可访问性问题。FreeBSD提供了成千上万的端口；端口配置是一个关键功能，但对视力受损的用户来说是不可访问的。

PortOptsCLI（Port Options CLI）是一个通过命令行界面设置端口选项的新实用工具。PortOptsCLI正确地提供了用于导航配置对话框（复选框和/或单选按钮）并交互式设置其项目的命令。它也适用于语音合成器；目前已使用 accessibility/orca 进行测试。PortOptsCLI 可以通过 ports-mgmt/portoptscli 端口或软件包进行安装。

欢迎提供提示和新的想法。如果可能，请将报告发送到 FreeBSD 可访问性邮件列表，以在公共场所分享和跟踪讨论。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Third Party Projects**

许多项目基于FreeBSD或将FreeBSD组件纳入其项目。由于这些项目可能对广大FreeBSD社区感兴趣，因此我们有时会在季度报告中包含这些项目提交的简要更新。FreeBSD项目对这些提交中的任何声明的准确性或真实性不作表示。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**BSD Cafe 项目介绍**

链接：

BSD Cafe 项目主页 URL: https://wiki.bsd.cafe/

BSD Cafe Mastodon 实例 URL: https://mastodon.bsd.cafe/


联系人：Stefano Marinelli <stefano@dragas.it>

我们很高兴地推出 BSD Cafe 项目的首个组成部分！

数月前，当我首次注册 bsd.cafe 域名时，我设想了一个主题酒吧，在那里朋友、熟人和客人可以聚集，进行关于 *BSD 系统、Linux 和开源技术的非正式对话。就像任何酒吧一样，我们的讨论可以涉及各种各样的话题，同时保持相互尊重的精神。

BSD Cafe 有望成为各种工具和服务的中心，所有这些都由 *BSD 提供支持。

我们的初始提供是一个全新的 Mastodon 实例（开源微博软件和服务），作为通往联邦网络的门户——联邦网络是许多使用 ActivityPub 分散式社交网络协议的服务的联合体。现在已经开放注册。该服务器遵循明确定义的指南，促进积极行为，并明确禁止任何形式的仇恨。包容性、尊重和建设性对话是该实例的基石。

我们的主服务器目前托管在芬兰的一台小型虚拟机上，运行在 FreeBSD 上。服务被分为 VNET jails，在本地区域网络中通过专用桥接连接。此外，我们实施了一个 VPN 系统，并有灵活性将单个 jails 迁移到更强大的机器上。

对于多媒体数据和缓存托管，我们使用一个单独的物理服务器（也是基于 FreeBSD，在一个 jail 中），由 Cloudflare 管理前端。这里的目标是缓存和地理分布数据，有效减少主 VPS 上的网络拥塞。

我们的反向代理（前端）、邮件服务器、媒体服务器和实例本身都可以通过 IPv6 访问。

在初始阶段，这个 Mastodon 实例没有预加载的内容。我们的意图是让它根据用户的兴趣和关注者有机地成长。在这个阶段，我们已经避免了预先的屏蔽。我们强烈鼓励用户迅速报告任何他们认为需要关注的事项。

我们邀请您加入我们，参与 https://mastodon.bsd.cafe/，以培养一个重视建设性互动并拥抱包容性的社区——一个为所有人提供安全宁静空间的社区。

此外，我们建立了一个网站 https://wiki.bsd.cafe/，将提供我们的工具、服务、规则、正常运行时间等的概述。

最近，已经安装了 Miniflux，因此 BSD Cafe 用户可以将其用作个人 RSS 订阅阅读器。更多信息请参阅 https://wiki.bsd.cafe/miniflux-bsd-cafe。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━


**容器与FreeBSD：Pot、Potluck 和 Potman**

链接：

Pot 在 GitHub 上的组织 URL: https://github.com/bsdpot


联系人：Luca Pizzamiglio (Pot) <pizzamig@FreeBSD.org>
联系人：Bretton Vine (Potluck) <bv@honeyguide.eu>
联系人：Michael Gmelin (Potman) <grembo@FreeBSD.org>

Pot 是一个管理 jail 的工具，同时支持通过 Nomad 进行编排。

在本季度，完成了 Pot 0.15.6 版本，新增了自定义 pf(4) 规则配置钩子。

此外，发布了 Nomad Pot Driver 0.9.1 版本，允许在 Nomad 作业描述中设置 Pot 属性。

Potluck 的目标是成为 FreeBSD 和 Pot 的 Dockerhub：一个 Pot 风格和完整容器镜像的存储库，可在 Pot 中使用，在许多情况下也可以在 Nomad 中使用。

新增了不少新的容器镜像，例如 Caddy S3 代理、Mastodon 实例和 Redis 容器。总共有 50 个容器可用，可以在 Potluck 图像注册表上下载为现成的镜像（如果信任我们的构建过程），或者可以从存储在 Potluck GitHub 存储库中的 Pot 风格文件中构建。

2023 年 7 月/8 月版的 FreeBSD Journal 中包含 Luca 的文章《使用 pot 和 nomad 进行 jail 编排》，解释了如何使用 Pot 和 Potluck 与 Nomad 一起在多个主机上编排容器。

最后，一个补丁（90b1184d93c8）为 devel/sccache 端口添加了构建集群支持。

如常，欢迎反馈和补丁。

赞助商：Nikulipe UAB，Honeyguide Group

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

# FreeBSD 2023 年第一季度 季度状况报告

这是 2023 年第一季度的首份状态报告，共包括 25 份报告。除了我们习惯的团队报告，还包含云项目的一些新闻，以及 src、ports 和 doc 方面的进展等内容。

我们还介绍了 13.2-RELEASE 的一些信息，该版本被推迟到了 2023Q2 的开头。不过，由于这份报告的发布时间在 FreeBSD 新版本发布之后，因此该版本现在已经可以安装了。RELEASE 版本的用户现在可以受益于许多改进，例如更好的 iwlwifi（4）驱动程序支持或新的 rtw88（4）驱动程序。这些主题在过去的状态报告中也有涉及。

祝你愉快阅读。

状态团队代表 Lorenzo Salvadore

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

这份报告的网页版本可以在此处查看：

https://www.freebsd.org/status/report-2023-01-2023-03/

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### FreeBSD 团队报告

这里是来自各个官方和半官方团队的条目，可在管理页面中找到。

**FreeBSD 核心团队**

联系方式：FreeBSD 核心团队 [core@FreeBSD.org](mailto:core@FreeBSD.org)

FreeBSD 核心团队是 FreeBSD 的管理机构。

**项目**

**核心团队章程：草稿**

2023 年第一次核心团队会议上，来自 12 月份在美国博尔德举行的会议的代表向整个团队呈报了他们的结论。团队将继续讨论这些问题，并与 FreeBSD 基金会一道努力。

**FreeBSD 年度开发者调查**

核心团队与 FreeBSD 基金会决定，由 FreeBSD 基金会负责进行年度开发者调查。

**Matrix 即时通讯方案**

核心团队继续评估 Matrix 作为 FreeBSD 开发者的即时通讯方案。一个实例已经准备好并正在进行测试。【译者注：Matrix 是一个开源的、去中心化的即时通讯协议和网络】

**提交权限**

- 核心团队批准了 Cheng Cui（cc@）的 src 提交权限。
- 核心团队批准恢复了 Joseph Koshy（jkoshy@）的 src 提交权限。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD 基金会**

链接：

FreeBSD 基金会网址：https://www.freebsdfoundation.org

技术路线图网址：https://freebsdfoundation.org/blog/technology-roadmap/

捐赠网址：https://www.freebsdfoundation.org/donate/

基金会合作伙伴计划网址：https://freebsdfoundation.org/our-donors/freebsd-foundation-partnership-program/

FreeBSD 杂志网址：https://www.freebsdfoundation.org/journal/

基金会新闻和事件网址：https://www.freebsdfoundation.org/news-and-events/

联系人：Deb Goodkin [deb@FreeBSDFoundation.org](mailto:deb@FreeBSDFoundation.org)

FreeBSD 基金会是一个 501(c)(3)非营利组织，致力于支持和推广全球的 FreeBSD 项目和社区。个人和企业的捐赠资金将用于资助和管理软件开发项目、会议和开发者峰会。我们还为 FreeBSD 贡献者提供旅行补助金，购买和支持硬件以改进和维护 FreeBSD 基础设施，并提供资源以改进安全、质量保证和发布工程方面的工作。我们出版营销材料以推广、教育和宣传 FreeBSD 项目，促进商业供应商和 FreeBSD 开发者之间的合作，并最终代表 FreeBSD 项目执行合同、许可协议和其他需要认可法律实体的法律安排。

**募捐工作**

我们终于得到了 2022 年的筹款数额，总共筹集了 $1,231,096！虽然我们没有达到预定目标，导致我们不得不从我们的长期投资中撤回了约 $74,000。

除了从我们的用户和贡献者那里获得了许多捐赠外，我们还从 Juniper、Meta、Arm、Netflix、Beckhoff、Tarsnap、Modirum、Koum 家族基金会和 Stormshield 等公司获得了较大的捐赠。我代表基金会向所有个人和企业，包括捐赠者，对你们在 2022 年的财政贡献表示衷心感谢！

今年我们的预算约为 2,230,000 美元，其中包括增加对 FreeBSD 宣传和软件开发的支出。超过一半的预算被分配给与改进 FreeBSD 和保持其安全性直接相关的工作。为了给 2023 年的预算提供资金，我们提高了筹款目标，并计划使用一些投资资金。当我们收到第一笔百万美元的捐款时，我们的计划是每年最多使用其中的 10% 来增加我们改进 FreeBSD 的工作，所以这已经是我们几年来资金计划的一部分。【译者注：我也没看懂最后一句话是什么意思】

2023 年的预算正在董事会的审批过程中，并将在获批后发布。

本季度我们收到了来自 Juniper、Tarsnap、微软和 Stormshield 的捐赠。所以，我们已经有了一个很好的开端！但是，我们绝对需要更多的支持来支持我们 2023 年的计划。

如果你想帮助我们继续努力，请考虑向我们的 2023 年筹款活动捐款！https://www.freebsdfoundation.org/donate/

我们还有一个针对更大的商业捐赠者的合作伙伴计划。你可以在https://freebsdfoundation.org/our-donors/freebsd-foundation-partnership-program/了解详情。

**系统优化**

在 2023 年第一季度，有 226 个 src、39 个 port 和 12 个 doc 提交的改动中，有一些是由 FreeBSD 基金会赞助的。其中一些受赞助的工作在单独的报告条目中有所描述，包括：

- 持续集成
- 在使用日志软更新的文件系统上启用快照
- 将 FreeBSD 作为一级 cloud-init 平台
- FreeBSD 发布工程团队
- 改进 kinst DTrace provider
- 在 FreeBSD 上使用 OpenStack

基金会赞助的其他工作包括：

- 修复和更新 OpenSSH 到 9.2p1 和 9.3p1 版本
- 厂商将 libpcap 导入和更新到 1.10.3 版本【译者注："vendor import" 意味着该更新是由软件供应商导入的，可能是为了提高该软件库与其它软件之间的兼容性。】
- 改进 tmpfs、msdosfs 和 makefs
- 添加新的 kqueue1 系统调用
- 更新 man 页面
- 修复 dtrace 和 bhyve 问题
- LinuxKPI 的工作

**持续集成和质量保证**

基金会为 FreeBSD 项目提供流量全职员工和资金，以改进持续集成、自动化测试和整体质量保证工作。你可以在专门的报告中阅读有关 CI 工作的更多信息。FreeBSD 基金会目前资助的一个项目是开发一组脚本，帮助 src 开发人员自行进行 CI 测试。其中的主要目标之一是在提交前提供更多的可见性。[第一个里程碑式的代码审查](https://reviews.freebsd.org/D38815)已经提交。

**FreeBSD 的宣传和教育**

我们的大部分工作都致力于推广 FreeBSD 项目。这可能包括推广有趣的 FreeBSD 项目，制作文献和视频教程，参加活动或者进行演讲。我们制作的文献旨在教授人们 FreeBSD 基础知识，帮助他们更容易地使用或者为项目做出贡献。除了参加活动和演讲，我们还鼓励和帮助社区成员自行组织 FreeBSD 活动、演讲或者承担 FreeBSD 展台。

FreeBSD 基金会赞助了全球许多会议、活动和峰会。这些活动可能与 BSD 相关，也可能与开源或者技术有关，面向的人群可能是被较少关注的群体。我们支持以 FreeBSD 为主题的活动，帮助为分享知识、共同开发项目以及促进开发者和商业用户之间的协作提供场所，从而提供健康的生态环境。我们支持非 FreeBSD 相关的活动，以促进和提高对 FreeBSD 的认识，扩大 FreeBSD 在不同应用领域的使用，并招募更多项目贡献者。我们现在大部分时间都是亲自参加活动，并开始计划于 2023 年 5 月举办的 BSDCan 开发者峰会。除了参加和计划活动外，我们还在不断制定新的培训计划，更新我们的指南，以帮助更多人尝试使用 FreeBSD。

看看我们的宣传和教育工作：

- 在 2023 年 2 月 4-5 日比利时布鲁塞尔举办的 FOSDEM 上设置了展台。查看旅行报告。
- 在 2023 年 2 月 7-8 日英国伦敦举办的“开放状态”（State of Open Con）上设立了桌子。阅读更多信息。
- 在 2023 年 3 月 9-12 日加利福尼亚州帕萨迪纳举办了 SCALE 20x 的工作坊和展台。查看旅行报告。
- 在 2023 年 3 月 23 日，赞助了在北卡罗来纳州夏洛特市举办的“开源 101”活动。
- 赞助并开始策划于 2023 年 5 月 17-18 日在安大略省渥太华举行的 2023 年 5 月开发者峰会。
- 获得了媒体合作伙伴赞助地位，并为 2023 年 10 月 15-17 日在北卡罗来纳州罗利举办的“All Things Open”提交了工作坊申请。
- 提交了在 2023 年 7 月 13-16 日在俄勒冈州波特兰举办的 FOSSY 的工作坊提案。
- FreeBSD 项目被接纳为谷歌代码之夏的参与组织。
- 我们举办了 GSoC Office Hours，以帮助有问题的潜在参与者。
- 发布了三月份的通讯。
- 其他博客文章
  - [了解 FreeBSD 和 Ampere Altra 的内部结构](https://freebsdfoundation.org/blog/under-the-hood-with-freebsd-and-ampere-altra/)
  - [新的开放职位：FreeBSD 用户空间软件开发人员](https://freebsdfoundation.org/blog/under-the-hood-with-freebsd-and-ampere-altra/) - 注意：此招聘已关闭。
  - [BSDCan 2023 旅行补助申请现已开放](https://freebsdfoundation.org/blog/bsdcan-2023-travel-grant-application-now-open/) - 注意：申请已关闭。
- FreeBSD 在新闻中的表现
  - [VMBlog 与 Deb Goodkin 关于开放状态的问答](https://freebsdfoundation.org/news-and-events/latest-news/vmblog-state-of-open-con-qa-with-deb-goodkin/)

我们通过出版专业制作的 FreeBSD Journal 来帮助全球了解 FreeBSD。正如我们之前提到的，FreeBSD Journal 现在是免费的出版物。你可以在 https://www.freebsdfoundation.org/journal/ 了解更多信息并访问最新问题。

你可以在 https://www.FreeBSDfoundation.org/news-and-events/ 了解我们参加的活动和即将举行的活动。

**法律/FreeBSD 知识产权**

基金会拥有 FreeBSD 商标，并有责任保护它们。我们还为核心团队提供法律支持，以调查出现的问题。【译者注：基金会至今为止并未就 FreeBSD 在中国境内的商标被抢注一事给出解决方案】

请访问 https://www.freebsdfoundation.org 了解有关我们如何支持 FreeBSD 以及如何帮助你的更多信息！

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD 发布工程团队**

链接：

FreeBSD 13.2-RELEASE 日程安排网址：https://www.freebsd.org/releases/13.2R/schedule/

FreeBSD 14.0-RELEASE 日程安排网址：https://www.freebsd.org/releases/14.0R/schedule/

FreeBSD releases 版本网址：https://download.freebsd.org/releases/ISO-IMAGES/

FreeBSD 开发快照网址：https://download.freebsd.org/snapshots/ISO-IMAGES/

联系人：FreeBSD 发布工程团队，re@FreeBSD.org

FreeBSD 发布工程团队负责制定和发布 FreeBSD 官方项目的发布时间表，宣布代码冻结并维护相应的分支，等等。

在 2023 年第一季度，发布工程团队开始着手筹备即将到来的 13.2-RELEASE 版本。截至本文写作时，13.2 版本的开发已经按照最初设定的时间表进行，只不过增加了第四、第五和第六个 RC 版本的构建，将最终版本的发布时间从 3 月底推迟到了 4 月初。

发布工程团队继续为主分支、stable/13 分支和 stable/12 分支提供每周开发快照版本的构建。

赞助商：Rubicon Communications，LLC（“Netgate”）

赞助商：Tarsnap

赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**集群管理团队**

链接： 集群管理团队成员链接：https://www.freebsd.org/administration/#t-clusteradm 联系方式：集群管理团队 clusteradm@FreeBSD.org

FreeBSD 集群管理团队负责管理项目所依赖的机器，以同步分布式工作和通信。

在本季度中，该团队开展了以下工作：

- 定期支持 FreeBSD.org 用户账户。
- 为所有物理主机和镜像提供定期的磁盘和零件支持（和更换）。
- 改进 PowerPC 软件包构建器。
  - 借助 FreeBSD 基金会获得的新部件，构建器现在具有新的带散热片和带有更多缓存的 NVME。它有助于解决散热问题，现在他们正在更快地构建软件包。
- 将动态资源从主网站中解耦。
  - 与 doceng 和 webmaster 协调工作，从网站 www.FreeBSD.org 和 docs.FreeBSD.org 中解耦动态资源。

**正在进行的工作**

- 在我们的主站点进行大规模的网络升级。
  - 新的 Juniper 交换机已经到达我们的主站点，以替换以前的交换机。我们感谢 Juniper 的捐赠。
- 替换我们主站点和几个镜像中的旧服务器。
  - 除了已经损坏的 CI 服务器外，我们还有一些带有损坏磁盘和有故障电源的旧服务器。这项任务与 FreeBSD 基金会和捐助者/赞助商协作。
- 部署基础设施以镜像网站。
  - 由于 FreeBSD 网站现在基本上是静态的，我们已经开始部署基础设施，在由 FreeBSD 项目管理的镜像中在全球范围内镜像 www.FreeBSD.org 和 docs.FreeBSD.org。
- 为内部 FreeBSD.org 搜索需求（如邮件列表和文档）创建新的搜索数据库引擎。

**FreeBSD 官方镜像概述**

当前位置包括澳大利亚、巴西、德国、日本（两个完整的镜像站点）、马来西亚、南非、台湾、英国（完整的镜像站点）和美国（加利福尼亚州、新泽西州\[主站点]和华盛顿州）。

硬件和网络连接由以下机构慷慨地提供：

- [Bytemark Hosting](https://www.bytemark.co.uk/)
- [BroadBand Tower 公司的云和 SDN 实验室](https://www.bbtower.co.jp/)
- [国立阳明交通大学计算机科学系](https://www.cs.nycu.edu.tw/)
- [Equinix](https://deploy.equinix.com/)
- [澳大利亚互联网协会](https://internet.asn.au/)
- [互联网系统协会](https://www.isc.org/)
- [INX-ZAv](https://www.inx.net.za/)
- [KDDI Web Communications 公司](https://www.kddi-webcommunications.co.jp/)
- [马来西亚研究和教育网络](https://myren.net.my/)
- [Metapeer](https://www.metapeer.com/)
- [New York Internet](https://www.nyi.net/)
- [NIC.br](https://nic.br/)
- [Your.Org](https://your.org/)

法兰克福单服务器镜像是欧洲带宽和使用率方面的主要镜像。

我们仍在寻找一个额外的全镜像站点（五台服务器）来取代英国的全镜像站点中的旧服务器。

我们发现在全球互联网交换点拥有单个镜像的模式非常好（在澳大利亚，巴西和南非）；如果你知道或在这些机构工作，可以赞助单个镜像服务器，请与我们联系。美国（西海岸）和欧洲（任何地方）是首选地点。

请查看完整镜像站点规格的[通用镜像布局](https://wiki.freebsd.org/Teams/clusteradm/generic-mirror-layout)和单个镜像站点的 [Tiny Mirror](https://wiki.freebsd.org/Teams/clusteradm/tiny-mirror)。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**连续集成**

链接：

FreeBSD Jenkins 实例网址：https://ci.FreeBSD.org

FreeBSD CI 构件存档网址：https://artifact.ci.FreeBSD.org

FreeBSD Jenkins wiki 网址：https://wiki.FreeBSD.org/Jenkins

托管 CI wiki 网址：https://wiki.FreeBSD.org/HostedCI

第三方软件 CI 网址：https://wiki.FreeBSD.org/3rdPartySoftwareCI

与 freebsd-testing@ 相关的工单网址：https://bugs.freebsd.org/bugzilla/buglist.cgi?bug\_status=open\&email1=testing%40FreeBSD.org\&emailassigned\_to1=1\&emailcc1=1\&emailtype1=equals

FreeBSD CI 代码库网址：https://github.com/freebsd/freebsd-ci

dev-ci 邮件列表网址：https://lists.FreeBSD.org/subscription/dev-ci

联系人：Jenkins 管理员 jenkins-admin@FreeBSD.org

联系人：Li-Wen Hsu lwhsu@FreeBSD.org

联系人：freebsd-testing 邮件列表

联系人：IRC EFNet 上的 #freebsd-ci 频道

2023 年第一季度，我们与项目的贡献者和开发人员合作，满足他们的测试需求。同时，我们与外部项目和公司合作，通过在 FreeBSD 上进行更多测试来增强他们的产品。

重要的已完成的任务：

- 添加了 FreeBSD-main-aarch64-KASAN_test 及其支持任务。
- 添加了 FreeBSD-stable-13-amd64-KASAN_test 及其支持任务。
- FreeBSD-main-amd64-gcc12_build 现在会将失败的报告发送给可能相关的提交者。
- trasz@ 修复或解决了非 x86 架构测试中的各种问题。
- 在 AsiaBSDCon 2023 开发者峰会上呈现测试/CI 状态更新。

正在进行的任务：

- 设计并实施预提交 CI 构建和测试（以支持工作流工作组）。
- 设计并实施使用 CI 集群来构建发布产品，就像发布工程所做的那样。
- 简化为贡献者和开发者设置 CI/测试环境的步骤。
- 设置 CI 阶段环境并在其中放置实验性任务。
- 整理 freebsd-ci 存储库中的脚本，为合并到 src 存储库做准备。
- 改进硬件测试实验室并添加更多硬件进行测试。
- 合并 https://reviews.freebsd.org/D38815。
- 合并 https://reviews.freebsd.org/D36257。

开放或等待中的任务：

- 收集和分类 CI 任务和想法。
- 为运行测试的 VM 客户机设置公共网络访问。
- 实现使用裸金属硬件运行测试套件。
- 添加对 -CURRENT 的 drm port 构建测试。
- 计划运行 ztest 测试。
- 帮助更多软件在其 CI 流水线中获得 FreeBSD 支持（Wiki 页面：3rdPartySoftwareCI、HostedCI）。
- 与托管 CI 服务提供商合作，以获得更好的 FreeBSD 支持。

请参阅与 freebsd-testing@ 相关的工单，以获取更多正在进行的信息，也欢迎加入我们的努力！

赞助：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Ports**

链接：

FreeBSD Ports 简介：https://www.FreeBSD.org/ports/

贡献 Ports：https://docs.freebsd.org/en/articles/contributing/#ports-contributing

FreeBSD Ports 监控：http://portsmon.freebsd.org/

Ports 管理团队：https://www.freebsd.org/portmgr/

Ports 压缩包：http://ftp.freebsd.org/pub/FreeBSD/ports/ports/

联系人：René Ladan portmgr-secretary@FreeBSD.org

联系人：FreeBSD Ports 管理团队 portmgr@FreeBSD.org

Ports 管理团队负责监督 Ports 的整体方向、构建软件包（通过其附属项 pkgmgr），以及人员问题。以下是本季度的情况。

目前，我们的 Ports 中大约有 33,500 个 port。对于这些 port，共有 3,021 个待解决的 bug 报告，其中 764 个未分配。今年前三个月，主分支有 163 名提交者提交了 9,021 个 commit，2023Q1 分支有 55 名提交者提交了 701 个 commit。与 2022Q4 相比，这意味着在 port 数量、ports PR、ports commit 和活跃的 port 提交者数量略有增加。

在本季度，我们欢迎了 Robert Clausecker (fuz@)、Vladimir Druzenko (vvd@)、Robert Nagy (rnagy@)，并欢迎 Norikatsu Shigemura (nork@) 回归，同时告别了 Marius Strobl (marius@)。Portgmr 在成功地担任 lurkership 后，新增了 Muhammad Moinur Rahman (bofh@) 为新成员。

在 portmgr 双周会议期间，讨论了以下话题：

- 改善内核模块二进制包的情况
- 如何衡量 ports 对它们的依赖项的影响以及如何维护高影响力的 ports。

在本季度，进行了 32 次 exp-run 来测试 port 更新、更新默认版本（LLVM 到 15、MySQL 到 8.0、Ruby 到 3.1）以及在基础设施中更新 byacc。此外，Go 的默认版本更改为 1.20，Lazarus 的默认版本更改为 2.2.6。

引入了四个新的 USES：

- `budgie` 用于支持与 Budgie 桌面相关的 port
- `ldap` 提供对 OpenLDAP 的支持，新的默认版本为 2.6
- `nextcloud` 用于支持 Nextcloud 应用程序
- `ruby` 用于提供对 Ruby ports 的支持（前身为 bsd.ruby.mk）。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**状态团队**

链接:

FreeBSD 状态报告网址: https://www.freebsd.org/status/

FreeBSD 状态报告流程网址: https://docs.freebsd.org/en/articles/freebsd-status-report-process/

归档状态报告的 GitHub 仓库网址: https://github.com/freebsd/freebsd-quarterly

联系: status@FreeBSD.org

**新的工作计划已经启动**

在今年的第一季度，状态团队开始实施在 2022 年底宣布的新的工作流。以下是一些详细信息。

新的电子邮件地址

上一季度，我们宣布创建了新的电子邮件地址:

• status@FreeBSD.org, 用于直接与状态团队互动；

• status-submissions@FreeBSD.org, 用于发送报告提交；

• freebsd-status-calls@FreeBSD.org, 一个邮件列表，你可以订阅以获得有关状态报告提交截止日期的提醒。

不幸的是，邮件列表目前无法正常工作。该问题已报告，但尚未找到解决方案。但是，通过一种变通方法，第二和最后一个提醒可以发送到该列表。

**自动化**

为了确保没有报告遗漏，一些自动化措施已经被引入：

- 在 Phabricator 上，引入了一个 Heral 规则，自动阻止任何与状态报告目录相关的代码评审：即使报告提交者忘记将状态团队添加为评审人，Salvadore@（状态团队成员）也会阻止补丁的合并。同样的规则还会阻止任何将状态团队列为评审人的评审，以确保提交之前至少有一个状态团队成员审核了补丁。
- 一个 GitHub action 自动将新引入的状态报告标签添加到任何涉及状态报告目录的 pull request 中。该 GitHub action 应该可以轻松地由任何人进行修改，以便根据修改文件的路径自动应用更多标签。

计划引入更多自动化。

**文档重组**

状态报告的 README 和 How To 已经更新并合并为一个独特的文档：FreeBSD 状态报告过程。你可以查看该文档以了解有关报告提交和发布的详细信息。随着状态团队继续实施其新工作流程，该文档将定期更新。特别是，有关自动化的新材料即将推出。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 用户空间

影响基本系统和其中程序的更改。

**改进 daemon(8)**

链接: daemon(8) 网址: https://man.freebsd.org/daemon/8

Libera IRC 网址: https://libera.chat/

联系人: Ihor Antonov ihor@antonovs.family

联系人: Kyle Evans kevans@FreeBSD.org

一项持续改进的工作正在进行，旨在提高 daemon 实用工具的代码质量和监督能力。daemon 是一个工具，可以将任何运行中的进程守护化（发送到后台）或监督它，如果它崩溃则自动重启。Daemon 在 port 中被广泛使用，并可以在基本系统中更多地使用。

本季度添加了 `long_opts` 支持，代码库经过了初始的重构阶段，以准备进行进一步的更改。目前还没有功能性的更改，但是更多的更改即将到来。如果遇到意外的错误，请直接联系或在 Libera IRC 的 #freebsd-dev 上进行反馈。

下一季度计划的工作项：

- 使用 kqueue 作为所有事件源【译者注：利用 kqueue 作为事件驱动的框架，来监听并响应所有的事件】
- 修复 Bug #268580
- 修复 Bug #236117
- 修复 Bug #254511
- 修复 Bug #212829
- `procctl PROC_REAP_ACQUIRE`

我们正在寻求反馈、错误报告（旧和新）和功能请求。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 内核

在内核子系统、驱动程序支持、文件系统等方面的更新。

**在 13.2 上启用基于日志软更新的文件系统快照**

联系人：Marshall Kirk McKusick [mckusick@freebsd.org](mailto:mckusick@freebsd.org)

在 2023 年第一季度，能够在运行日志软更新时对 UFS/FFS 文件系统进行快照，并使用它们对活动文件系统进行后台转储的功能被合并到 releng/13.2，将在 FreeBSD 13.2-RELEASE 中发布。

使用 `-L` 参数请求后台转储。

这个项目的详细信息在 [2022 年第四季度的报告](https://www.freebsd.org/status/report-2022-10-2022-12/#_enabling_snapshots_on_filesystems_using_journaled_soft_updates)中有说明。

赞助：FreeBSD 基金会 ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**改进 kinst DTrace provider**

链接：

libdtrace: 实现内联函数跟踪网址：https://reviews.freebsd.org/D38825

dtrace(1): 添加 -d 参数以在 post-dt_sugar 后转储 D 脚本网址：https://reviews.freebsd.org/D38732

联系人：Christos Margiolis [christos@FreeBSD.org](mailto:christos@FreeBSD.org)

联系人：Mark Johnston [markj@FreeBSD.org](mailto:markj@FreeBSD.org)

kinst 是由 christos@ 和 markj@ 创建的新的 DTrace provider，允许对内核函数进行任意指令跟踪。kinst 已经添加到 FreeBSD 14.0 的基本系统中。

2022Q3 状态报告简要介绍了 kinst。我们现在正在进行内联函数跟踪（请参见上面的 D38825 审阅）-这是一个备受期待的 DTrace 功能-通过使用内核 DWARF 和 ELF 信息找到每个内联副本的调用点，并使用该信息转换 D 语法，将 kinst 探针转换为以下形式：

```shell-session
   kinst::<inline_func>:<entry/return>
        /<pred>/
        {
                <acts>
        }
```

变为：

```shell-session
   kinst::<caller_func1>:<offset>,
        kinst::<caller_func2>:<offset>,
        kinst::<caller_func3>:<offset>
        /<pred>/
        {
                <acts>
        }
```

示例：

```shell-session
   # dtrace -dn 'kinst::cam_iosched_has_more_trim:entry { printf("\t%d\t%s", pid, execname); }'
        kinst::cam_iosched_get_trim:13,
        kinst::cam_iosched_next_bio:13,
        kinst::cam_iosched_schedule:40
        {
                printf("\t%d\t%s", pid, execname);
        }

        dtrace: description 'kinst::cam_iosched_has_more_trim:entry ' matched 3 probes
        CPU     ID                    FUNCTION:NAME
          2  79315          cam_iosched_next_bio:13     0       kernel
          2  79316          cam_iosched_schedule:40     0       kernel
          0  79316          cam_iosched_schedule:40     12      intr
          2  79315          cam_iosched_next_bio:13     0       kernel
          2  79316          cam_iosched_schedule:40     0       kernel
          0  79316          cam_iosched_schedule:40     12      intr
        ^C
```

dtrace(1) 新增了一个 `-d` 参数 ，它在 libdtrace 应用语法转换后会将 D 脚本进行转储。

其他的目标包括：

- 在 D 中实现一个 `locals` 结构，用于存储跟踪函数的局部变量。例如，在 `kinst::foo:<x>` 中，我们可以通过在 D 脚本中使用 `print(locals→bar)` 来打印局部变量 bar。
- 将 kinst 移植到 RISC-V / ARM64。

赞助者：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**原生的 Linux timerfd**

链接:

Differential revision 网址: https://reviews.freebsd.org/D38459

联系人: Jake Freeland jfree@FreeBSD.org

timerfd 是一组 Linux 标准系统调用，可操作间隔定时器。这些定时器类似于每个进程的定时器，但由文件描述符表示，而不是进程。这些文件描述符可以传递给其他进程，在 fork(2) 时保留，并可以通过 kevent(2)、poll(2) 或 select(2) 进行监视。

FreeBSD 已经存在一个 timerfd 实现，用于 Linux 兼容性，但此差异修订使接口本地化。这个更改的目标是为了方便在包含 timerfd 的程序的 FreeBSD 移植过程。

此特定实现避免向系统调用表中添加新名称。相反，timerfd_create() 被 specialfd() 系统调用包装。timerfd_gettime() 和 timerfd_settime() 调用由 ioctl() 包装。

希望支持 FreeBSD 的开发人员应避免使用 timerfd。首选使用 kqueue() EVFILT_TIMER 过滤器来建立任意定时器。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 架构

更新平台特定功能并为新硬件平台带来支持。

**AArch64 上的内核地址消毒剂（Kernel Address Sanitizer）**

联系人：Kyle Evans kevans@FreeBSD.org

内核地址消毒剂是一种检测 bug 的设施，它使用编译器（在本例中为 LLVM）插入的仪器和运行时状态跟踪的组合来检测 C 代码中的 bug。它们可以自动检测许多类型的 C 语言编程 bug，例如使用后释放和使用未初始化的变量，否则可能需要大量工作才能确定。它们特别适用于与回归测试套件或模糊工具（如 syzkaller）组合使用。与 Valgrind 等工具不同，必须重新编译软件才能启用给定的内核地址消毒剂，但内核地址消毒剂可以在内核中使用。启用了内核地址消毒剂的内核会在运行时产生显着的性能开销，包括 CPU 利用率和内存使用。

自 [89c52f9d59fa](https://cgit.freebsd.org/src/commit/?id=89c52f9d59fa) 以来，先前仅限于 amd64 的内核地址消毒剂已经被移植到了 arm64。

此前已在多种机器上进行了测试，包括：

- 各种 Ampere Altra 机器
- QEMU
- 微软的“Volterra”Devkit
- bhyve（正在进行中）。

欢迎和感激在其他硬件上进行进一步测试。

赞助：Juniper Networks，Inc.

赞助：Klara，Inc.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**bsd-user：上游支持和状态报告**

【译者注：bsd-user 是 QEMU（Quick Emulator）项目的一部分，它是一个用户空间模拟器，可以在不同的操作系统之间进行二进制指令的转换，从而实现在一个操作系统上运行另一个操作系统的程序。具体来说，bsd-user 是 QEMU 中用于模拟 BSD 系统调用的部分。通过 bsd-user，用户可以在基于 BSD 的操作系统之间运行二进制程序，而无需重新编译它们。】

链接：

QEMU 项目网址：https://qemu.org

FreeBSD bsd-user qemu fork 网址：https://github.com/qemu-bsd-user/qemu-bsd-user

QEMU 项目的 GitLab 镜像网址：https://gitlab.com/qemu-project/qemu

联系人：Warner Losh imp@FreeBSD.org

在这一季度中，Warner Losh 在 qemu-project 仓库上提交了两个 patch 集（第三个还在等待中）。Doug Rabson 提交了一些优化，以保存 qemu-user 模拟器的句柄供未来的 exec 使用。联系了一些希望在 NetBSD 上让 bsd-user 工作的人。代码之夏上游的项目表现出了一些兴趣。

**上游的努力**

本季度 sysctl 系统调用被上游了。Doug 的一些更改也被上游了（见下文）。在 NetBSD 和 OpenBSD 上进行一些清理以及在运行时动态生成系统调用仍在等待上游。

**Doug Rabson 的更改**

在他的容器工作的一部分中，Doug 提交了一些更改，允许内核缓存用于运行程序的模拟器。这使得内核可以使用缓存的模拟器直接 exec 新二进制文件。这简化了 bsd-user 并消除了它与 linux-user 之间的一个差异。Doug 还提供了一个重要的修复，防止 aarch64 运行失败。

**Bug 修复和改进**

除了 Doug 的修复外，这一季度 Warner 还进行了一些清理工作：

- Warner 移除了仿真器中存在的“运行在任何 BSD 代码上”的最后几个部分。
- 虽然基本的系统调用可以在所有 BSD 之间进行仿真，但它们的系统调用接口已经分化太多，太过丰富，因此短期内无法实现。
- Warner 原计划只移除 NetBSD 和 OpenBSD 的部分，但至少 NetBSD 的人员对构建这些东西表现出了兴趣。
- 现在，NetBSD 的人员已经有了联系方式并知道了方向，Warner 希望他们会提交一个 pull 请求，用于在 NetBSD 上构建 bsd-user。
- Warner 添加了 SIGSYS 支持，以便我们能够更早地捕获未实现的系统调用，并改进了有关它们的报告，以获取更多关于失败原因的数据。
- Warner 在 `blitz` 分支中清理了一些代码。
- 我们已经在使用的 `blitz` 分支中合并了上游最新的 8.0rc1。

**代码之夏项目**

对于 Qemu 的 project 列表中添加的 bsd-user upstreaming 任务，有很大的兴趣。运气好的话，我们将有一个学生来完成上游化所有运行简单程序所需的系统调用的工作。运气更好的话，我们将能够运行任何执行与 clang 相同的操作的程序（其中一个目标是使其编译 helloworld）。如果我们有机会得到这个位置，未来的季度报告将提供详细信息。

**需要帮助**

我们始终需要关于 bsd-user 的帮助。

- 欢迎为新系统调用提交 pull 请求。
- 自动生成我们手动完成的许多工作的自动化将会有所帮助（例如系统调用参数跟踪）。
- 热情的志愿者想要帮助我进行上游（如果你不想提交代码，许多任务都很简单和快速）。
- 与 NetBSD 人员协调和清理他们提出的内容。
- 需要修复 bug（特别是线程的 bug）。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 云计算

更新云计算特定功能并引入对新云平台的支持。

**FreeBSD 作为一级 Cloud-init 平台**

链接：

cloud-init 网站 网址: https://cloud-init.io/

cloud-init 文档 网址: https://cloudinit.readthedocs.io/en/latest/

cloud-init 持续重构 网址: https://github.com/canonical/cloud-init/blob/main/WIP-ONGOING-REFACTORIZATION.rst

联系人：Mina Galić freebsd@igalic.co

Cloud-init 是云中配置服务器的标准方式。不幸的是，除 Linux 外，其他操作系统的 cloud-init 支持相对较差，而 FreeBSD 上缺乏 cloud-init 支持则妨碍了那些希望将 FreeBSD 作为一级平台提供的云服务提供商。为了解决这个问题，该项目旨在使 FreeBSD 的 cloud-init 支持与 Linux 支持相当。更广泛的计划是提高所有 BSD 的支持。

由于个人原因，本季度进展非常缓慢，也因为缺乏正确资源的访问。我一直在尝试移植 Infiniband 功能。这证明很困难，因为它推翻了我的观点，即 ifconfig(8) 是在 FreeBSD 上了解网络接口所需的全部内容。

在等待资源的同时，我调试了引导 pamic 并解决了它：[499171a98c88](https://cgit.freebsd.org/src/commit/?id=499171a98c8813e4dc6e085461d5c47750efa555)。这使得可以在 LXD 上引导 FreeBSD，即 cloud-init 的 CI 平台。我们仍然需要解决高 CPU 使用率问题，但已经有一个已接受的审核：D38898。

一个 cloud-init 的同事在 Azure 工作，他成功让我使用 Azure 上的 HPC VM。不幸的是，这只是一个有限的时间，并不足以弄清楚如何在 FreeBSD 上启用 Infiniband，这是由 Linux 上的 Azure Agent 处理的任务，但 FreeBSD 的 sysutils/azure-agent 相当缺乏。

对此项目感兴趣的人可以提供来自其 Infiniband 系统的 ifconfig(8)、ibstat(8)、ibv_devinfo(1) 等复制。我也非常希望获得配有 Infiniband NIC 的硬件访问权限，或者听到在 Azure HPC 上成功使用 FreeBSD 的人的消息。

如果对该平台感兴趣，我将把一些精力用于修复 Azure Agent。

赞助商：FreeBSD 基金会

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**在 FreeBSD 上运行 OpenStack**

链接：

OpenStack 网址: https://www.openstack.org/

FreeBSD 上的 OpenStack 网址: https://github.com/openstack-on-freebsd

联系人：Chih-Hsin Chang [starbops@hey.com](mailto:starbops@hey.com)

联系人：Li-Wen Hsu [lwhsu@FreeBSD.org](mailto:lwhsu@FreeBSD.org)

该项目旨在移植关键的 OpenStack 组件，以便 FreeBSD 可以作为 OpenStack 主机运行。

在 2023 年第一季度，最重要的消息是我们能够在 OpenStack 平台上使用 bhyve(8) 生成 FreeBSD 实例。但仍存在一些需要解决的主要限制，包括：

- 没有自助网络（仅支持平面网络）【译者注：即在 FreeBSD 上使用 OpenStack 平台时，没有自动创建虚拟网络的能力。只能使用 "flat network"，这意味着所有虚拟机都连接到同一网络中，并且需要手动进行网络配置。】
- 实例内没有网络连接
- 仅支持 FreeBSD RAW 镜像（已测试 FreeBSD-13.1-RELEASE-amd64.raw）
- 无法调整磁盘大小
- 没有控制台集成（需要手动使用 cu(1)命令）

在文档存储库中可以找到构建 POC 站点的逐步文档。每个 OpenStack 组件的修补版本都在同一个 GitHub 组织下。

此外，我们在三月底参加了 AsiaBSDCon 2023，并在开发者峰会上就当前项目状态发表了短暂的演讲。我们在活动中得到了宝贵的反馈，下一季度将专注于以下事项：

- 解决 Open vSwitch 网络问题
- 将每个 OpenStack 组件转换为 FreeBSD port

有兴趣帮助该项目的人可以首先按照安装指南检查文档。以下是该项目的一个开放任务：

- oslo.privsep 库的 FreeBSD 特定实现

欢迎提供反馈和帮助。

赞助商：The FreeBSD Foundation

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 文档

文档、手册页面或新外部书籍/文档的重要更改。

#### 文档工程团队

链接：

FreeBSD 文档项目网址: https://www.freebsd.org/docproj/

FreeBSD 文档项目新贡献者指南网址: https://docs.freebsd.org/en/books/fdp-primer/

文档工程团队网址: https://www.freebsd.org/administration/#t-doceng

联系方式：FreeBSD 文档工程团队 [doceng@FreeBSD.org](mailto:doceng@FreeBSD.org)

doceng@ 团队是处理 FreeBSD 文档项目中一些元项目问题的机构。有关详细信息，请参见 FreeBSD 文档工程团队章程。

在最近的季度中：

- Pau Amma 获得了 doc 提交权限。
- 提议将 Lorenzo Salvadore 作为 doc 提交者。carlavilla@ 和 dbaio@ 将担任他的导师。
- Ryusuke SUZUKI 从 doceng 中退出。doceng 感谢 ryusuke@ 的贡献。

待处理和讨论的事项：

- 添加了有关许可证的新文档。

Port 开发者手册:

已向手册添加了三个新的 `Uses` 开关：

- 新的 Uses = ruby。
- 新的 Uses = ldap。
- 新的 Uses = budgie。

此外：

- 修复了 NVIDIA 的安装和配置选项。
- 改进了高级网络章节。

**在 Weblate 上的 FreeBSD 翻译**

链接：在 Weblate 上翻译 FreeBSD

链接：FreeBSD Weblate 实例

**Q4 202 2 状态**

- 12 种语言
- 150 名注册用户

**语言**

- 简体中文(zh-cn) (进度：14%)【译者注：实际进度应该是 0%。本社区项目因为种种原因无法合并，现在需要人手来合并，要求了解 adoc 和 markdown 语法，能找到对应英语的中文翻译译文】
- 繁体中文(zh-tw) (进度：11%)
- 荷兰语(nl) (进度：1%)
- 法语(fr) (进度：1%)
- 德语(de) (进度：1%)
- 印尼语(id) (进度：1%)
- 意大利语(it) (进度：10%)
- 韩语(ko) (进度：11%)
- 挪威语(nb-no) (进度：1%)
- 波斯语(fa-ir) (进度：6%)
- 葡萄牙语(pt-br) (进度：29%)
- 锡兰语(si) (进度：1%)
- 西班牙语(es) (进度：37%)
- 土耳其语(tr) (进度：5%)

我们要感谢所有翻译或审核文档的贡献者。

请帮助在你的本地用户组推广此项目，我们总是需要更多的志愿者。

**FreeBSD 手册工作组**

联系方式：Sergio Carlavilla [carlavilla@FreeBSD.org](mailto:carlavilla@FreeBSD.org)

已更新第 1 到 6 章。第 7 章正在进行中。

FreeBSD 网站翻新-WebApps 工作组

联系人：Sergio Carlavilla carlavilla@FreeBSD.org

工作组负责创建新的 FreeBSD 文档门户网站和重新设计 FreeBSD 主要网站及其组件。FreeBSD 开发人员可以关注并加入 FreeBSD Slack 频道 #wg-www21 的工作组。该工作将分为四个阶段：

- 重新设计文档门户网站

创建一个新的设计，具有响应式和全局搜索功能。（已完成）

- 重新设计 Web 上的手册页面

使用 mandoc 生成 HTML 页面的脚本。（已完成）公共实例在 https://man-dev.FreeBSD.org上

- 重新设计 Web 上的 Ports 页面

Ports 脚本用于创建应用程序门户网站。（正在进行中）

- 重新设计 FreeBSD 主要网站

新的设计，响应式和暗色主题。（正在进行中）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD 俄语文档项目**

链接：

FAQ 网址: https://docs.freebsd.org/ru/books/faq/

网址: https://www.freebsd.org/ru/

联系人：Andrey Zakhvatov [andrey.zakhvatov@gmail.com](mailto:andrey.zakhvatov@gmail.com)

FreeBSD 俄语文档项目的目标是提供最新的 FreeBSD 文档（FAQ，Handbook，Web）的俄语翻译。为了让说俄语的人们使用高质量的官方技术材料，并增加这个操作系统在全球的接受度。我们希望这项活动能够得到俄语社区的支持，并带来更多的翻译材料。

FAQ 的翻译已经更新并与最新的原版同步。网页更新方面也有一些微小的进展。

如果你想帮助翻译，可以查看官方的翻译指南。我们会感激你帮助翻译以下材料：

- 网页（简单的）
- Handbook 章节（目前只有 X11 部分正在进行中）
- 文章

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### Ports

影响到 Ports 的更改，无论是影响整个结构的全面变化，还是单个 port 本身的变化。

#### Freshports: SQL 注入攻击和求助请求

链接：

FreshPorts 网址: freshports.org

FreshPorts 博客网址: https://news.freshports.org/

联系人：Dan Langille dvl@FreeBSD.org

FreshPorts 和 FreshSource 已经报道了 FreeBSD 提交记录 20 年了。它们涉及了所有提交，而不仅是 port。

FreshPorts 跟踪提交并从 portMakefiles 中提取数据，以创建对 port 维护者和 port 用户都有用的信息数据库。

例如，https://www.freshports.org/security/acme.sh/ 显示了 security/acme.shport 的历史记录，从 2017 年 5 月的创建到现在。还提供了依赖关系、风格、配置选项和可用包等。所有这些对 port 的用户和开发人员都很有用。

**SQL 注入攻击**

三月份，发现了一次 SQL 注入攻击，网站已被修补。通知已通过我们的 Twitter 账户、我们的状态页面以及网站每个页面顶部的通知发送。立即关闭了攻击向量\[译者注：攻击向量（attack vector）是指攻击者利用安全漏洞或弱点，进入目标系统或者攻击目标的途径和手段】，并很快进行了修补。网站上还添加了额外的预防性补丁。我们所知道的所有问题都已经修复。用户已被通知并建议更改密码。

详情请见：

- https://news.freshports.org/2023/03/24/sql-inejection-issues-fixed/
- https://news.freshports.org/2023/03/24/freshsource-code-fixes/

需要帮助

FreshPorts 已经成立超过 22 年了。最后必须有其他人将其接过来。FreshPorts 有几个方面：

- FreeBSD 管理员（更新操作系统和软件包）
- 前端代码（网站 - 大多数是 PHP）
- 后端代码（提交处理 - Perl、Python、shell）
- 数据库设计（PostgreSQL）。

与应用程序和操作系统相比，数据库的更改不经常发生，并且需要很少的维护。网站几乎自己运行。偶尔会出现对 FreeBSDport 基础架构的更改会破坏某些内容或需要进行修改，但很少有紧急情况需要修复。这不是一个巨大的时间承诺。有很多东西需要学习。虽然 FreshPorts 不是一个复杂的应用程序，但也不是微不足道的。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**DRM 驱动程序（即 GPU 驱动程序）**

链接：

GitHub 上的 Git 存储库网址：https://github.com/freebsd/drm-kmod

联系人：Emmanuel Vadot manu@FreeBSD.org

联系人：Jean-Sébastien Pédron dumbbell@FreeBSD.org

联系人：图形团队 freebsd-x11@FreeBSD.org

GPU 由 DRM 驱动程序驱动。它们是专门为 Linux 开发的，使用宽松的许可证。我们的使命是将这些驱动程序移植到 FreeBSD，以确保现代 GPU 得到充分支持。

我们很长时间没有发布报告来分享我们的进展。因此，本状态报告条目将涵盖不止上一季度的情况。

**更新到了 Linux 5.15 LTS 和 Linux 5.16**

截至本状态报告，graphics/drm-kmod 元 port 仍在 FreeBSD 13.1 及更高版本上安装来自 Linux 5.10（发布于 2020 年 12 月 13 日）的 DRM 驱动程序。该驱动程序版本不支持最近的 GPU，特别是英特尔第 12 代 Alder Lake。在过去的几个月中，我们致力于更新 DRM 驱动程序，以支持更现代的 AMD 和 Intel GPU。

drm-kmod Git 存储库主分支首先更新到 Linux 5.15（于 2021 年 10 月 31 日发布）。这是 Linux 中的 LTS 分支，我们想利用这个机会。因此，在那个时候，我们走了两条路：

- 创建了一个 5.15-lts 分支，用于将所有错误修复从 Linux 5.15.x 补丁版本中回溯。这项工作现在在 drm-515-kmodport 中可用。
- 继续从随后的 Linux 版本进行移植工作。主分支现在位于 Linux 5.16（于 2022 年 1 月 9 日发布）。

来自 Linux 5.15 LTS 的英特尔驱动程序支持第 12 代 GPU（Alder Lake）。它似乎在 FreeBSD 上运行良好，但我们迄今为止只进行了轻微的测试。我们仍然需要更多的测试，这就是为什么 graphics/drm-kmod 仍然安装 graphics/drm-510-kmod 而不是 graphics/drm-515-kmod 的原因。最后，FreeBSD 应该可以在这一代 GPU 和几款新的 AMD GPU 上运行桌面，尽管在实际测试和使用中肯定会出现问题。

在此过程中，我们将固件更新为 linux-firmware 20230210。

**Linux 5.17 和未来的工作**

Linux 5.17 中的 DRM 驱动程序（发布于 2022 年 3 月 20 日）已经被移植，但这项工作仍然停留在自己的分支中。

有几个问题阻碍了进一步的测试和合并到主分支中：

- 我们当前与 vt（4）的集成，即控制台/终端驱动程序，与基于 Linux 的 fbdev KPI 的 DRM 驱动程序的期望相去甚远。在英特尔和 AMD 驱动程序中都发生了变化，这意味着 vt（4）会在更新到 5.17 版本时出现问题。
- 初始的 Linux 5.17 版本不包含被反向移植到 Linux 5.15 LTS 的修复程序。它在先前提到的英特尔第 12 代 GPU 上似乎非常不稳定。

为了解决我们的 vt（4）集成层的问题，我们开始编写一个新的 vt 后端，专门使用 DRM 驱动程序公开的 fbdev 回调。该后端将随着 DRM 驱动程序而提供，而不是随 FreeBSD 内核提供，以使得随着驱动程序的发展更易于维护。这仍然是一项正在进行中的工作，特别是锁定的正确使用比较棘手。

关于 5.17 更新中对英特尔第 12 代支持不佳的问题，Linux 5.17.x 补丁程序中反向移植的错误修复可能不会作为此项工作的一部分进行移植。相反，我们将专注于 Linux 5.18（发布于 2022 年 5 月 22 日）和随后的版本。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FreeBSD 上的 KDE**

链接：

KDE FreeBSD 网址：https://freebsd.kde.org/

KDE 社区 FreeBSD 网址：https://community.kde.org/FreeBSD

联系人：Adriaan de Groot [kde@FreeBSD.org](mailto:kde@FreeBSD.org)

KDE on FreeBSD 项目为 FreeBSD 的 port 打包了 CMake、Qt 和 KDE 社区的软件。该软件包括一个完整的桌面环境 KDE Plasma（适用于 X11 和 Wayland）以及数百个可在任何 FreeBSD 机器上使用的应用程序。

KDE 团队（kde@）是 desktop@ 和 x11@ 的一部分，构建软件堆栈，使 FreeBSD 美观易用，成为日常使用的基于图形界面的桌面机器。以下说明主要说明了 KDE 的 port，但也包括整个桌面堆栈的重要内容。

**基础设施**

- Qt5 port 更新到了 KDE patch collection 5.15.8 发行版。
- Qt6 port - KDE 尚未使用这些 port，但有许多 port 可以使用 Qt6 并具有 Qt6 flavor，已更新到了 6.4.2 版本。新增了 Qt6 发行版的 WebEngine 的 Python 绑定。
- Cmake port 已更新到 3.25.1 版本，FreeBSD 软件包的 CPack 生成器已修复。
- graphics/poppler port——许多 PDF 阅读器使用 - 已更新到 23.01 版本。
- sysutils/bsdisks port——用作应用程序的 shim，这些应用程序需要 Linux udisk，这意味着大多数桌面环境——已更新到 0.29 版本。

**KDE 软件堆栈**

KDE Gear 每季度发布一次，KDE Plasma 每月更新一次，KDE Framework 每月都有新版本发布。这些（大型）更新会在上游发布后不久到达，不会单独列出。

- KDE Framework 更新到 5.104 版本。
- KDE Gear 更新到 22.12.3 版本。
- KDE Plasma Desktop 更新到了 5.27 版本。由于支持堆栈中的未解决问题和 KDE Plasma 早期版本中的误置补丁，这是一个迟来的更新。感谢 arrowd@ 和 Serenity Cybersecurity, LLC 排解了这个问题。
- 新的 devel/ktextaddons port 已添加到 ports 中。这是 KDE PIM 套件的一部分，并计划在未来某个版本中成为新的 KDE Framework。

**相关的软件包**

- 音频播放器 amarok 是 KDE 最受欢迎的播放器之一，但已被标记为 ports 中弃用，它不再得到上游的维护。
- 星空模拟软件 kstars 更新至 3.6.3 版本。
- git 的图形用户界面 gitqlient 更新至 1.6.1 版本，并支持新的 git 命令。
- 二进制文件的十六进制查看器和编辑器 okteta 更新至 0.26.10 版本。
- 带有 Qt 支持的 C++ 协程库 qcoro 更新至 0.8.0 版本。
- 绘画和图形工作应用 krita 更新至 5.1.5 版本。
- 图形可视化库 quickqanava 发布了一个真正的版本，并在 ports 中进行了更新。
- IRC 客户端 kvirc 被更新至最新的提交版本。虽然没有真正的发布版本，但有一些 bug 修复。
- 视频和音频播放器 haruna 更新至 0.10.3 版本。
- 一款 Matrix 客户端 neochat 更新以追踪新版本的 net-im/libquotient。由于与较旧的 FreeBSD 版本的兼容性问题，KDE-FreeBSD 团队宣布 FreeBSD 12 发行版“已被有效地停止支持”。
- Rocket Chat 客户端 ruqola 更新至 1.9.1 版本。
- 双因素认证支持应用 keysmith 更新至 23.01.0 版本。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**FSX**

链接：

GitHub 网址: https://github.com/asomers/fsx-rs

FreshPorts 网址: https://www.freshports.org/devel/fsx/

联系人：Alan Somers [asomers@freebsd.org](mailto:asomers@freebsd.org)

FSX (File System eXerciser) 工具最初在九十年代由苹果公司开发，一直作为 FreeBSD 的一部分存在，自 5.0 版本以来就一直存在。该工具通过一系列随机生成的操作对文件系统进行压力测试，在每次读取后验证文件数据。然而，它从未作为操作系统的一部分安装；它只存在于源代码中。这使得它在 CI 管道中使用起来很困难。它还有其他一些限制。

因此，在本季度，我使用 Rust 对整个工具进行了重写。新版本与原版本完全兼容，只要种子值相同。然而，未来版本将打破向后兼容性，以添加新功能，如 fspacectl 和 copy_file_range。新版本可以在 ports 中找到，我会逐步移除原版本。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**在 FreeBSD 上的 GCC**

链接：

GCC 项目网址: https://gcc.gnu.org

GCC 11 发行系列网址: https://gcc.gnu.org/gcc-11/

GCC 12 发行系列网址: https://gcc.gnu.org/gcc-12/

联系人：Lorenzo Salvadore [salvadore@FreeBSD.org](mailto:salvadore@FreeBSD.org)

联系人：Gerald Pfeifer [gerald@pfeifer.com](mailto:gerald@pfeifer.com)

本季度的主要消息是从 ports 中清除旧的 GCC 版本：这将允许更有效地处理错误。

**废弃旧的 GCC port**

ports 仍然包含多个与旧且不受支持的 GCC 版本相关的 port。它们通常作为一些旧 port 的依赖项，最好的方法是将其更新为使用受支持的 GCC 版本或废弃。已创建错误报告以跟踪此问题，并已经开始了解决该问题的工作。感谢所有贡献者的帮助。

**废弃 USE_GCC=X+**

Gerald 曾长期维护 FreeBSD 上的 GCC port，最近仍在通过帮助简化 ports 中的 GCC 基础架构来为 GCC 的维护做出贡献，例如通过删除处理旧不受支持的 GCC 版本的特殊情况。

本季度他最重要的更改可能是删除对 `USE_GCC=X+` 结构的支持：任何依赖于 GCC 的 port 都应该设置 `USE_GCC=yes`，如果 `GCC_DEFAULT` 可用的话；如果不是，则应该要求特定版本（例如 `USE_GCC=11`）；它不能再要求最小版本（例如 `USE_GCC=11+`）。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Valgrind——为 Valgrind 3.21 做准备**

链接：

Valgrind 官方网站网址: https://www.valgrind.org/

Valgrind 新闻页面网址: https://www.valgrind.org/docs/manual/dist.news.html

联系人：Paul Floyd [pjfloyd@wanadoo.fr](mailto:pjfloyd@wanadoo.fr)

devel/valgrind-devel port 于 2023-02-20 提交了一个中间更新，其中包含了即将发布的 Valgrind 3.21 正式版本的大部分内容，正式版本将会在本状态报告之后不久发布。

vgdb 接口得到了一个不错的改进。现在更容易看到哪些内存位被初始化和哪些没有。Helgrind 执行的线程检查也进行了一些修复。

特别是对于 FreeBSD，地址空间限制已经被提高到与 Linux 和 Solaris 上的 amd64 相同。之前是 32G 字节，现在是 128G 字节。`kern.proc.pathname.PID` sysctl(3) 已经修复，使其返回 guest exe 的路径而不是 Valgrind 主机的路径。同时，我还修复了一些 `_umtx_op` 的误报，并以与 `kern.proc.pathname.PID` 相似的方式纠正了 auxv AT_EXECPATH。还添加了 sctp_generic_sendmsg(2) 和 sctp_generic_recvmsg(2) 的系统调用包装器。

Valgrind 的 port 版本中尚不可用，有一个用于 rfork(2) 的解决方法。之前，由于不支持，它会导致 Valgrind 中止。现在它会以优雅的方式失败并设置 EINVAL 或 ENOSYS。这个系统调用的主要用途是在 posix_spawn(3) 中，它会回退到使用 vfork(2)。

mknodat(2) 系统调用包装器在 i386 上被错误地实现了，现在已经修复。

所有对齐分配函数都进行了重新设计，使其的行为更像 Valgrind 的构建平台，而不是像 Linux glibc。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 第三方项目

许多项目基于 FreeBSD 或将 FreeBSD 组件合并到其项目中。由于这些项目可能会引起更广泛的 FreeBSD 社区的兴趣，因此我们有时会在我们的季度报告中包括这些项目提交的简要更新。FreeBSD 项目不对这些提交中的任何声明的准确性或真实性做出陈述。

**PkgBase.live**

链接:

网站(archive.org) 网址: https://web.archive.org/web/20221220222828/https://alpha.pkgbase.live/

网站源代码网址: https://codeberg.org/pkgbase/website

联系人: Mina Galić [freebsd@igalic.co](mailto:freebsd@igalic.co)

PkgBase.live 是一个非官方的 FreeBSD PkgBase 项目存储库。作为一个服务，PkgBase.live 的灵感来自于 https://up.bsd.lv/，为 STABLE 和 CURRENT 分支提供 freebsd-update(8)。

PkgBase 的硬件由 FreeBSD 社区的一位成员慷慨赞助。然而，随着生活和项目的变化，他们不得不废弃硬件，给了我三个月的通知时间。在那段时间里，由于最近搬到了另一个国家，我的生活相当动荡，所以我没有能够找到替代品。

目前，PkgBase.live 已经关闭。

该网站及其 [How Did She Do it？！](https://codeberg.org/pkgbase/website/src/branch/main/howto/howdo.md)仍然在 [Git](https://codeberg.org/pkgbase/website) 中提供。我强烈鼓励模仿。

我也会很乐意接受新的硬件赞助商！

请注意，我已经联系了 FreeBSD 项目，他们正在将 PkgBase 集成到发布工程中。然而，他们还没有准备好，也不能“简单地”接管 PkgBase.live，因为它使用完全不同的过程。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**容器和 FreeBSD：Pot、Potluck 和 Potman**

链接： Pot 在 GitHub 上的组织网址：https://github.com/bsdpot

联系人：Luca Pizzamiglio（Pot）[pizzamig@freebsd.org](mailto:pizzamig@freebsd.org)

联系人：Bretton Vine（Potluck）[bv@honeyguide.eu](mailto:bv@honeyguide.eu)

联系人：Michael Gmelin（Potman）[grembo@freebsd.org](mailto:grembo@freebsd.org)

Pot 是一个 jail 管理工具，也支持通过 Nomad 进行编排。

在上个季度，Pot 收到了一些次要修复，但尚未发布新版本。

Potluck 旨在成为 FreeBSD 和 pot 的 Dockerhub，提供 pot 风味和完整的容器镜像，可用于与 pot 配合使用，而在许多情况下还可用于 Nomad。

所有 Potluck 镜像都已重新构建以包含最新的 FreeBSD 安全公告，新增了一个 Smokeping 网络延迟监视镜像，对 Jitsi 镜像进行了大量的工作，但不幸的是似乎仍存在一些可靠性问题。

此外，有两篇新的博客文章介绍使用 Potluck 镜像的简单方法，一篇解释如何使用 Minio 作为对象存储和 Prometheus 进行监视来设置 Nextcloud，一篇展示如何使用 OpenLDAP 运行自己的 Matrix Synapse 服务器以进行访问管理。

像往常一样，欢迎反馈和补丁。

### FreeBSD 2022 年第三季度 季度状况报告

> 原文地址 [https://www.freebsd.org/status/report-2022-07-2022-09/](https://www.freebsd.org/status/report-2022-07-2022-09/)

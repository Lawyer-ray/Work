## 敏捷软件测试：测试人员与敏捷团队的时间指南

目前的开发主要测试是由我自己负责，小项目还好，但是大项目就会感觉有点力不从心，比如迷衣App，其实有很多肉眼可见的Bug，稍微注意一点点就能发现，但工程师好像就没有发现，可能是因为数据不准确或者是因为其他原因，Anyway，为了提升自己的测试水平，减轻部分工作压力，特地拜读此书。

em...目标总是好的，路程总是要曲折一点，这本书的翻译过于生硬啦！而且书的内容也过于冗余，如果不关心过程，只需要知道答案的同学，可以直接翻开第21章“关键成功要素”，进行学习与回顾。前面Lisa的故事简直多到可怕。。。就是完全不想看。

### 成功要素之一：使用团队整体参与的方法。

当整个开发团队负责测试和质量问题，你会拥有很多不同的技能集合和经验等级来处理测试可能发生的问题。测试自动化对于技能高超的开发人员来说不是大问题。当测试置于团队的优先权，任何人都参与测试任务，团队才会设计可测试的代码。

敏捷开发的目的是质量，而不是速度。团队需要测试人员帮助客户理清需求，转化为指导开发的测试。确保测试人员能够将技能和长处转移到其他成员身上。确保他们不是局限于一种角色，如只做手动测试。确保当他们需要帮助时（可能需要极大的勇气），团队成员能够提供。反过来也是如此。测试人员应该随时准备帮助那些需要他们帮助的队友。

和开发人员一起参加会议，提出三方协作，测试人员、开发人员和业务专家。谨慎地提供您反馈并帮助客户提供示例。让你的问题成为团队的问题，让他们的问题成为你的问题。

#### 感想

之前做了一个拼团的活动，研发团队内部自测过关了，然后交给我，结果我发现问题百出。然后我发现他们只是主流程测试，甚至说主流程都没有完全跑通就交给了我，我也很悲伤，那个时候技术总监正准备离职，以前都是CTO在帮我把关，然后我就直接挪位置，坐到了前后端工程师旁边，开始写测试用例，一个个案例开始测试。我测试的时候，向工程师描述为什么会出这个问题，他们都在惊叹为什么我能测出各种问题，其实不难，就是基于业务出发，以用户的视角为基础，就是类似上文中所提到的三方协作，我扮演了两个角色：测试人员和业务专家。让技术人员像我一样那么了解每个业务细节是不太可能的，所以后来，我们每次开完冲刺启动会，我都直接开始着手于写测试用例，甚至说，都没有开冲刺启动会，我都已经开始准备测试用例了。

测试是整个团队的事情，我深有感触，有些新手工程师开发完自己的部分就说完了，测试都不测试，直接丢给我，结果我一看又是一大堆问题，所以说呢，还是坚持写单元测试，工程师至少是要对自己的代码负责，Bug这种东西谁都不想发生，老老实实写好单元测试。

### 成功要素之二：采用敏捷测试思维

抛弃“质量警察”的思维。在敏捷团队中，开发人员参与测试，测试人员可以做任何事情以帮助团队生产最优秀的产品。

不应该披上超级测试王的斗篷，去保护世界免受缺陷的危害。在敏捷团队中不存在妄自非大。团队成员需要理解你对质量的追求。关注团队目标，帮助每个成员更好地工作。

不断尝试最简单的方法来满足测试需要。勇敢地追寻帮助和实验新想法。尽可能多地直接交流。灵活地应对变化。记住敏捷开发以人为中心，应该享受工作。当对此产生怀疑时，回顾敏捷价值和准则来决定怎么做。

敏捷测试思维的一个重要部分是不断想办法改进工作。成功的敏捷测试人员会持续地磨练技能。读好书、博客和文章以获得新想法和技能。

实验新的实践、工具和技术。鼓励团队尝试新办法。短期迭代非常适合这种实验。你可能会失败，但是很快你可以尝试其他的。

当你面对影响测试的问题时，让团队都知道这些问题。可通过头脑风暴的方式克服这些障碍回顾会议可以讨论这些问题并想办法解决。

#### 感想

我司的测试之前很不敏捷，直到有一天，我自己也提出了敏捷测试的概念（是在看这本书的好几个月前），敏捷开发带来的就是敏捷测试，开发前写好测试用例，工程师甚至能对着我的测试用例去开发，以防会出现Bug，以及帮助其完善业务思维，让其代码更稳健。

遇到Bug的时候，最好前后端工程师，甚至说团队成员都知道，大家的经验水平以及问题的判断能力均不相同，一起解决，总比我自己想的好。开发迷衣App的时候我们发现的帖子不能像小程序那样分享就自动截图取页面的80%，后来问了志宏，我们干脆做个更简单的，直接取第一张图片，混合发帖又分享的时候，取第一件商品第一张图片，取第一张图片，取专题图片，取视频第一帧，完美解决！沟通的力量！

### 成功要素之三：自动化回归测试

敏捷开发利用测试来指导开发。为了编写代码使测试通过，需要快速、简单地运行测试。没有短期反馈周期和安全的回归测试，团队将很快陷入技术宅舞，缺陷不断增加，速度越来越慢。

从简单入手，一些基本的自动化冒烟测试或者自动化单元测试会发挥很大作用。

自动化测试在开始的时候会很艰苦，需要克服很大的痛苦。如果你管理或测试团队，赢确保在时间、培训和激励上提供了足够的支持。如果你是没有自动化测试的团队的测试人员，开发人员疯狂地编写代码以至于不会停下来考虑测试，那么你会面临很大的挑战。应尝试从管理层和团队成员中获得支持以开始最小规模的自动化工作。

#### 感想

我们团队至今没有真正应用起自动化测试，比较惭愧，不发表太多意见。

### 成功要素之四：提供并获取反馈

敏捷就是反馈。反馈就是敏捷的核心，短期的迭代为的就是快速反馈以帮助团队正常运转。

#### 感想

没有反馈，工程师就永远不知道自己的代码有Bug！

### 成功要素之五：构建核心实践的基础

* 持续集成
  * 每一个开发团队都需要代码管理和集成。——已经做到啦！
* 测试环境——做得不太好噢！
  * 没有可控的测试黄静就无法有效地测试。你需要知道部署了什么版本、使用的数据库模式是什么、其他人是不是正在更新模式，其他进程是否运行在那台服务器上。
  * 如果测试环境出现问题，应该赶紧说出来，让全队一起解决。
* 管理技术债务
  * 团队必须不断地评估技术债务的数量，并努力减少和避免技术债务。
  * 管理层不会给我们时间做这些吗？没有时间重构？日程很紧？但是，我们可以举一个业务用例来显示增长的技术债务如何耗费公司的成本。仅仅指出不断下降的速度就足够了。
  * 自动化测试的良好覆盖率是最小化技术债务的关键。如果缺少，那就在每个迭代中拿出时间来构建自动化测试，规划一个重构迭代以升级或添加必要的工具。在每个迭代中花时间通过测试指导代码，重构必要的代码，添加丢失的自动化测试。
---
title: 受过教育的公民应该知道哪些统计与概率知识
excerpt: '自从统计学课程被广泛引入大学课程以来，很多方面都发生了变化，但是统计学入门课程的教学方式却没有跟上这些变化。本文讨论这些变化，以及入门教学大纲应该如何改变来反映这些变化。特别讨论了七点想法，即每个接受初级统计的学生都应该学习和理解，才能成为一个受过教育的公民。'
author: Jessica UTTS
tags:
  - 转载
categories:
  - Area
date: 2023-01-16 13:12:59 
---

本文翻译自 [What Educated Citizens Should Know About Statistics and Probability](https://www.ics.uci.edu/~jutts/AmerStat2003.pdf)

by Jessica UTTS[^1] 

自从统计学课程被广泛引入大学课程以来，很多方面都发生了变化，但是统计学入门课程的教学方式却没有跟上这些变化。本文讨论这些变化，以及入门教学大纲应该如何改变来反映这些变化。特别讨论了七点想法，即每个接受初级统计的学生都应该学习和理解，才能成为一个受过教育的公民。对这些问题的误解，充其量会导致公众的犬儒主义，最糟糕的是政策制定者、医生等人对研究结果的误用。关键词：巧合；实践意义；统计学教育；统计素养；调查偏倚。


## 1. 导言

统计研究在大多数主要报纸的日报或周报中占据显著地位，但大多数公民，甚至许多记者，并不具备批判性阅读所需的知识。当统计学课程首次被引入时，它们主要是由那些打算从事自己的研究的学生，或者是那些要求他们分析数据的学科，作为他们训练的一部分。这些课程的重点是计算，很少强调如何以有意义的方式整合从研究设计到最终结论的信息。从那时以来，在三个方面发生了很大的变化：观众、学生可用的工具和我们周围的世界。

在许多大学中，有相当大比例的专业要求学生修读统计学入门课程。这些学生中的大多数实际上从来不会自己做统计分析。因此，我们应该让他们阅读和理解他人进行的、分析的、发表在期刊上的、由媒体报道的研究。传闻中，观众也以另外两种方式发生了变化。首先，在统计学入门课程中，学生似乎比早期更不擅长定量推理，也许是因为专业代表性更广。而且回国学生较多，他们可能与传统的大学生有不同的兴趣。

毫无疑问，学生可使用的工具在最近几年发生了变化，学院配备了精密的计算器，至少能够计算均值和标准差，而且往往能够完成统计学入门课程中讲授的大部分程序。此外，计算机的普及，Excel 等程序具有标准的统计功能。甚至统计软件的使用在过去的几十年中也发生了变化，Minitab 和 SPSS 等程序是菜单驱动的，使新手更容易学习和使用。

我们周围的世界也发生了变化。统计研究定期在报刊杂志上进行报道，因此学生很可能会在常规基础上遇到它们。而且，对于课堂使用，互联网上有大量的例子，如盖洛普组织、《今日美国》、劳工统计局等。更进一步，许多期刊论文可在线获得，因此教师和学生很容易完成统计研究的设计、实施、分析和结论的示例。

所有这些变化的后果是，不再需要强调计算，而更需要关注理解统计研究是如何进行和解释的。相关和有趣的例子是现成可用的。然而，许多教师在如何教授入门统计学方面并没有做出任何改变。


## 2. 七大重要议题

在基础统计学课程中，当然有许多重要的话题需要讨论。对于这篇文章，我选择了7个我发现被市民普遍误解的话题，包括向公众介绍统计研究的记者。事实上，研究人员自己，他们在期刊和科学会议上介绍他们的结果，记者们从他们的故事中剔除，误解了其中的许多主题。如果所有的统计学入门学生都理解了它们，那么与统计和概率相关的混淆和曲解就会少得多。事实上，公众对统计研究往往愤世嫉俗，因为这些误解导致了一连串的研究结果。在医学研究中尤其如此，当医生和患者都不能正确解释统计结果时，误解会产生严重的后果。

首先对本文所涵盖的七个主题进行了总结，然后对每个主题进行了更深入的解释和举例：

1. 当可以得出一种关系是因果关系之一时，和不能得出这种关系时，包括随机实验和观察性研究之间的差异。
2. 统计学意义和实际重要性之间的差异，特别是在使用大样本量时。
3. "无影响"或"无差异"与"无统计学意义的影响或差异"之间的差异，特别是在使用小样本时。
4. 调查和实验中常见的偏见来源，如问题措辞不佳、志愿者反应和社会期望的答案。
5. 认为巧合和看似很不可能的事件并不少见，因为有那么多的可能性。
6. "逆的混淆"，即一个方向上的条件概率与另一个方向上的条件概率相混淆。
7. 理解变异性是自然的，"正常"与"平均"并不相同。


## 3. 因果关系

也许新闻中对统计研究最常见的误读是得出结论：当一个关系具有统计意义时，解释变量的变化是引起响应变量变化的原因。这个结论只有在非常有限的条件下才是合适的，比如对于大型的随机实验。对于单一的观察性研究，得出一个变量引起另一个变量变化的结论是很少合适的。因此，对于统计学专业的学生来说，了解随机实验和观察性研究之间的区别，了解混杂变量的可能性如何限制了从观察性研究中可以得出的结论是很重要的。

作为这个问题的一个例子，《今日美国》上出现了一篇题为"祈祷能降低血压"的文章( Davis 1998 )。本文报告了一项由美国国立卫生研究院资助的观察性研究，该研究对2391名65岁及以上的老年人进行了6年的随访。一项新的研究报告说，文章中报告的结论之一是：

_参加宗教服务比参加宗教电视或广播更能降低血压。每周参加一次宗教仪式、每天祈祷或学习圣经一次的人，其高血压患病的可能性比每周不去教堂、少祈祷和学习圣经的人低40 % ( Davis 1998 )。_

标题和显示的引语都表明，祈祷和参加宗教仪式实际上导致血压降低。但是没有办法根据这项研究来确定因果关系。这可能是因为越健康的人越有能力参加宗教服务，因此因果关系是归因的反向。或者，更倾向于社交的人压力更小，血压更低，更有可能去教堂。本研究中还有许多其他可能的混杂变量可以解释观察到的关系。问题是读者可能会错误地认为如果他们以更多的祈祷和教会出席来改变自己的行为，会导致他们的血压降低。

另一个例子说明即使是研究者也会犯这个错误。《萨克拉门托蜜蜂》( The Sacramento Bee，Perkins 1999 )的一篇文章报道了一项观察性研究，研究开始时随机抽取了6000多名平均年龄为70岁的个体。随着时间的推移，研究发现超过70 %的参与者没有随着时间的推移而失去认知功能。其中一个结果被引用为“那些患有糖尿病或动脉硬化程度高的人与阿尔茨海默病的基因结合在一起，表现出认知功能下降的可能性是8倍“( Perkins 1999 )。到目前为止，这么好，因为报告人并不是暗示风险增加是因果的。然而，最初的研究者之一(如果准确引用)并不是那么小心翼翼。研究者被引述如下："这对预防有影响，这是好消息。如果我们能防止动脉硬化，我们就能防止记忆随着时间的推移而丧失，而我们知道如何通过行为改变来做到这一点。

换句话说，研究者假设高水平的动脉硬化会导致认知功能的下降。但有许多可能的混杂变量既可能导致动脉硬化程度高，又可能导致认知功能下降，如遗传倾向、某些病毒、生活方式选择等。

当一个因果结论是合乎逻辑的，或者当一个人能够想到因果机制可能如何运作的原因时，抵制做出因果结论的诱惑就特别困难。因此，在为学生说明这个概念时，给出许多例子并讨论混淆变量如何解释这种关系是很重要的。幸运的是，例子很容易发现。大多数主要报纸和互联网新闻网每周都会报道几次观察性研究，并且经常会得出一个可能错误的因果结论。


## 4. 统计意义和实践意义

学生需要明白一个统计符号可能没有太大的实际重要性。这在样本量较大时尤其可能出现问题，因此即使存在非常小的效应，也容易拒绝原假设。例如，《纽约时报》刊登了一篇题为"网络空间中发现的悲伤、孤独的世界"的文章( Harmon 1998 )。它说："一周上网几个小时的人比不经常使用计算机网络的人有更高的抑郁和孤独感："这引起了关于'虚拟'交流的本质和在网络空间中经常形成的分离关系的令人不安的问题( Harmon 1998 )。

听起来这项研究为频繁使用互联网的人们揭示了一个重大问题。但在更仔细的检验中，差异的幅度很小。在1 (更孤独)到5的量表上，自评孤独从平均1.99下降到1.89，在0 (更多)到3 (更少)的量表上，自评抑郁从平均0.73下降到0.62。

下面是另一个例子，说明一个非常大的样本量是如何导致统计上的显著差异的，这对一般公众来说似乎没有什么实际意义。最初的报道是在Nature ( Weber ,普罗辛格和赛德勒1998)，路透社在雅虎健康新闻网站上的一篇文章刊登了标题为"春天的生日"的标题。

文章描述了奥地利对507125名新兵身高的研究，其中在春季出生的新兵和秋季出生的新兵之间存在显著差异。平均高度差均为. 6厘米，约1 / 4英寸。虽然这对研究增长问题的研究者来说可能很重要，但这种差异并不是我们大多数人认为的"高度优势"。

一个相关的常见问题是，**当进行多重比较或分析时，只报告那些达到统计显著性的结果。在大多数研究中，多种关系被检验，但只有那些达到统计学意义的关系被媒体报道**。例如，研究服用阿司匹林或激素的效果的随机实验可能会检查它们与多种结果的关系，如心脏病、中风和各种类型的癌症。如果研究者没有对多重比较进行调整，就把注意力集中在那些达到统计显著性的关系上，就好像这些关系是唯一被检验过的关系一样。虽然这里没有详细讨论多元分析问题，但在说明解释统计显著性的注意事项时，与学生一起讨论很重要。


## 5. 低功率对无影响

同样重要的是，**学生要明白样本量在关系或差异是否具有统计学意义上起着很大的作用，而"没有差异"的发现可能仅仅意味着研究的力量不足**。例如，假设进行了一项研究，以确定超过多数的人口是否具有某种意见，因此检验考虑H0：p =：5，而Ha：p >：5。如果事实上有多达60 %的人群有这种观点，那么100的样本量只会有. 64的功效。换言之，仍有36 %的概率原假设不被拒绝。然而，记者经常会大肆渲染这样一个事实，即一项研究"没有复制"一个更早的结果，而在现实中该效应的大小与原始研究相似，但研究的力量太低，无法检测到它的统计意义。

作为一个具有重要影响的例子，1993年2月由美国国家癌症研究所( NCI )主办的会议对八项关于乳腺摄影作为筛查设备有效性的研究进行了荟萃分析。关于40 ~ 49岁女性的结论是："对于这个年龄组，很明显，在进入研究后的前5 ~ 7年，乳腺癌的死亡率没有降低，这可以归因于筛查"。

问题的话是没有还原。NCI与美国癌症协会之间的争论接踵而至。下面再加两句话来说明问题：

_
美国癌症协会的一位发言人星期二说：：研究不会改变该小组的建议，因为它不够大，无法得出确切的结论。由于乳腺癌在年轻女性(《圣何塞水星新闻》1993年11月24日)中如此罕见，该研究需要筛选100万女性才能得到一定的答案。_

_即使将所有8个随机对照试验的数据合并，也会产生足够的统计效力，以显示筛选的好处。在8个试验中，40 ~ 49岁的女性( 30 %的被试)只有16.7万人，数量太少，无法提供有统计学意义的(西克尔斯和Kopans 1993)结果。_

随访7年后相对危险度的置信区间为. 85 ~ 1.39，点估计值为1.08，说明该年龄段女性的死亡率可能有小幅度的降低，也可能有小幅度的上升。最初关于"死亡率没有减少"的说法是危险的误导。

在这一背景下传达的教训是，当学生阅读一项研究没有发现任何效果或关系时，学生应该小心。一般而言，这一结论只有与先前的结论或共同智慧相矛盾时才具有新闻价值。在这种情况下，重要的是找出样本的大小，如果可能的话，找出结果的置信区间。如果置信区间较宽，或者倾向于一方比另一方更倾向于偶然，则有理由怀疑该研究可能没有足够的能力探测到真正的差异或关系。

在入门课程中，"权力"不再是一个需要回避的话题，因为它很容易找到可以进行计算的软件，而且这个概念并不比"类型1 "和"类型2 "错误的概念困难。Minitab将为初级统计课程中教授的大部分测试计算功效，也有网站可用。约翰·佩苏略维护的http://members.aol.com/johnp71/javastat.html,是一个很好的Internet源，它提供了包括电源在内的数百个站点的统计计算链接。


## 6. 调查中的偏倚

有许多不同的来源可以将偏差引入调查。一些更恶劣的情况除非了解所有细节，否则很难发现。例如，1999年7月9日发布的盖洛普民意调查( Gallup Poll )，基于随机抽取的1016名美国成年人，以随机顺序问了两个不同的问题，每个问题都可以用来报告认为美国公立学校应该教授神创论的人的百分比。这两个问题以及回答"喜欢"的比例是：

_问题1：在公立学校中，你是赞成还是反对教学创造论? ( 68 %赞成)。_  
_问题2：你赞成还是反对在公立学校中引入进化论的教学创造论?( 40 %赞成)。_

需要注意的是，根据自己的意见，这些结果可能被误用为有利。赞成创造论的人有68 %认为应该教，反对创造论的人只有40 %认为应该教。

不仅仅是问题的措辞会导致引入偏见。关于如何进行调查，还有许多其他细节可能看起来微不足道，但可能产生重大影响。例如，有时提问的顺序会改变结果。Clark和肖伯( 1992年, p . 41)报告了一项调查，询问了以下两个问题：

1. 总的来说，你的生活有多幸福?
2. 你一般多久出去一次约会，大约一个月几次。

受访者对这两个问题的回答几乎没有关系。但当以问题2再次询问时，答案高度相关。Clark和肖伯猜测，在这种情况下，受访者将问题1解释为"现在，考虑到你刚才告诉我关于约会的事情，你对生活的总体满意度如何? "受访者自然而然地认为调查中的问题应该是相关的，任何一个问题带来的问题都可能影响后续的回答。

还有许多其他方式，其中问题措辞、问题顺序、样本选择方法等问题会对调查结果产生偏误。详见Tanur ( 1992 )，Utts ( 1999 )，Utts和Heckard ( 2003 )。


## 7. 可能的符合

大多数人一生中都经历过一个或多个似乎不太可能发生的事件。有些这样的事件是如此令人惊讶，以至于它们吸引了媒体的关注，往往是对它们的可能性的估计。例如，Plous ( 1993 )报道了一个"先生和太太"的故事。理查德·贝克离开一家购物中心，在停车场发现了他们以为是自己的车，开车离开了。几分钟后，他们意识到自己开错了车。他们回到停车场和警察等待他们。原来他们开的车是属于另一个先生的。贝克，谁有同样的车，用同样的钥匙!普卢斯报告说，警方估计的赔率为百万比一。

这类故事和计算的问题在于它们是基于提出错误的问题。该计算最有可能适用于发生的确切事件。一个更符合逻辑的问题是：对于某个人来说，某个时间、某个地点发生类似事件的概率是多少?在大多数情况下，这种概率会非常大。

例如，我曾经在一个电视谈话节目中与一个两次赢得百万美元纽约州彩票的男人谈论运气，节目主持人认为这显示了非凡的运气。迪亚科尼斯和Mosteller ( 1989 )报告说，虽然这对那个人来说可能是美妙的，但在7年的时间里，同一个人在美国的州彩票中获胜的可能性是相当大的。对于这个人来说，这正是两次获胜之间的间隔。

要计算出巧合的精确概率并不容易，但可以向学生展示近似数量级的计算结果。例如，有很多关于分开长大的双胞胎的故事，他们在成年后相遇，发现他们有惊人的共同特征。也许他们的妻子或孩子有相同的名字，他们开同一种车，他们从事相同的职业。作为一个粗略的近似，假设两个相同年龄和性别的人在任何给定项目上 "匹配 "的概率是1/50，并且在一个项目上是否匹配与在其他项目上是否匹配无关。此外，假设在认识对方的过程中，他们讨论了200个项目，这当然不是一个不现实的数字。那么，"匹配 "的数量是一个二项式随机变量，n=200，p=:02。预期的匹配数量是4，甚至6个或更多匹配的概率也相对较高，约为0.21。但在这种情况下，重点是放在引人注目的匹配上，而不是放在被讨论但不匹配的几十个主题上。

即使报道了发生概率极低的事件，也要记住，世界上有60多亿人，每天都有很多情况发生。因此，肯定会有一些看起来不可思议的。事实上，如果某件事情在某一天发生在某一个人身上的概率只有百万分之一，那么世界上平均每天会有6000多人发生。当媒体报道一个不可思议的巧合时，应该从这个角度来看待。


## 8. 逆的混淆

大多数统计学教师都知道概率对学生来说很容易混淆，对概率的直觉不是很好。心理学家发现了这个问题的一个版本，它导致了重要的误解，被称为"逆的混乱"。其基本问题是将条件概率 P(A∣B) 与条件概率 P(B∣A) 相混淆。

例如，Eddy ( 1982 )将这一情景呈现给了100位医生：

_你的一个病人胸部有个肿块。你几乎可以肯定它是良性的，事实上你会说只有1 %的几率是恶性的。但可以肯定的是，你让患者进行乳房X线检查，这是一个旨在检测癌症的乳房X光片。_

_你从医学文献中知道，乳房X光检查对恶性肿块的准确率为80%，对良性肿块的准确率为90%。 换句话说，如果肿块确实是恶性的，检查结果80%的时候会说是恶性的，20%的时候会谎称是良性的。 如果肿块确实是良性的，检查结果90%的时候会这么说，而只有10%的时候会错误地宣布它是恶性的。 不幸的是，你的病人的乳房X光检查结果显示肿块是恶性的。 它是真正恶性的几率有多大？_

大多数医生的回答接近75%。 但事实上，根据给出的概率，正确答案只有7.5%左右！ 埃迪报告说：当被问及这一点时，犯错误的医生通常会说，他们假定病人X线检查呈阳性时患癌的概率大约等于患癌病人X线检查呈阳性的概率（1982，第254页）。 换句话说，医生们混淆了假定女性患有癌症的阳性检测的概率和假定检测为阳性的女性患有癌症的概率。

大多数医学测试具有较低的假阳性和假阴性率，但如果初始患病概率较低，那么在测试结果为阳性的情况下，患病的概率仍然很低。在这种情况下，大多数的阳性检测结果将是假阳性。

对于学生来说，最容易说明这个概念的方法是通过我所说的"假设的十万" ( Utts和Heckard 2003 , p . 228)，这是一个表，显示了10万人的理论结果。表1以Eddy呈现给医生的例子中的数字为例进行说明。值得注意的是，在10700名检测为恶性的患者中，只有800名，约7.5 %的患者实际患有恶性肿瘤。由于良性肿块女性多于恶性肿块女性，10 %的女性假阳性检测结果占阳性检测结果的绝大部分。

还有许多其他情形可能适用逆的混淆。例如，美国汽车协会交通安全基金会发布的一项研究( Stutts等2001)被广泛宣传，因为它发现事故中只有1.5 %的司机报告说他们在使用手机，而10.9 %的人报告说他们被车上的另一个人分心。许多媒体报道的结论是，这意味着用手机通话比其他分心的事情更不容易发生事故，比如在车上和别人说话，或者听收音机。

见表1。一种罕见疾病的实际状态与测试状态的分解

|       | 试验为恶性 | 试验是良性的 | Total |
| ----------- | ----------- | ----------- |
| 实际上是恶性的 | 800 | 200 | 1000 |
| 其实是良性的 | 9900 | 89100 | 99000 |
| Total | 10700 | 89300 | 1000000 |

但请注意，这混淆了两个条件概率。报告的驾驶人使用手机的事故比例为0.015 ( 1.5 % )，是对驾驶人发生事故时使用手机概率的估计。感兴趣的概率是相反的- -司机在使用手机的情况下发生事故的概率。这一概率无法从报告的数据中找到，因为它取决于手机使用的流行率。但是，几乎可以肯定的是，在任何时候，更多的司机与汽车的其他乘客交谈，而不是在手机上交谈。本研究也受到了其他方面的批评；有趣的评论可参见"汽车对话"电台节目主持人(马廖齐和马廖齐2001)的文章；其中一位(汤姆)有博士学位。来自波士顿大学管理学博士并对统计学有很好的理解。


## 9. 平均与正常

学生需要理解的第七个概念是自然可变性及其在解释什么是"正常"中的作用。这里有一个幽默的例子，Utts和Heckard ( 2003 )对此进行了描述。加利福尼亚州戴维斯附近的一家公司在其废水设施中出现了气味问题，他们试图将其归咎于"异常"的降雨量：

_去年严重的气味问题部分是由于厄尔尼诺现象在林地地区造成的极端天气条件[据一家公司的官员说]。她说林地地区的降雨量是正常降雨量的170%到180%。 “过量意味着蓄水池中的水需要更长的时间才能流出进行灌溉，从而使其有更多的时间产生气味（Goldwitz 1998）。_

这种推理的问题是，年降雨量是极不稳定的。在加利福尼亚州的戴维斯地区，1951 ~ 1997年以英寸为单位的降雨量的平均值为6.1、12.1、16.7、25.4、37.4。(均值汇总包括低值、第一四分位数、中值、第三四分位数和高值。)该年的降雨量为29.7英寸，在"正常"范围内。公司官员和记者"平均"与"正常"混为一谈。这种错误在气温和降水数据的报告中非常常见，在其他情况下也是如此。自然可变性的概念对于理解统计结果至关重要，因此在整个入门课程中应该加强自然可变性的概念。


## 10. 总结

本文所讨论的问题构成了统计学和概率学中一系列常见而重要的误解。 显然还有其他的，但我发现这些是如此普遍，它很可能是数百万人被误导。 我们这些教授统计学导论的人有责任确保我们的学生不在其中。

许多大学现在除了传统的统计学入门课程外，还开设了统计学或数字扫盲课程，人们可能很容易认为这些主题属于这些课程，而不是传统课程。 但这没有抓住重点。 如果一个学生不能阅读报纸文章并确定假设检验被误用，那么知道如何进行 _t_ 检验又有什么用呢？

将本文所涉及的主题纳入传统课程并不困难，事实上，如果有好的例子，学生们会喜欢听这些主题。 关于统计学显著性和样本量之间关系的主题2和3的讨论应作为1类和2类错误讨论的一部分。 主题5和6可以与概率一起纳入教学大纲，事实上它们是寻找概率的有趣例子。 专题7是关于自然变异性是正常现象的一部分，可在本课程的前半部分讨论变异性的平均值和测量值时讲授

专题1，关于避免基于观察研究的因果关系的含义，专题4关于调查中的偏见，是唯一需要增加到教学大纲中的内容。 但
但我认为重要的是至少给予一个统计研究类型的简要概述以及它们是如何完成的，这样数据收集过程对学生来说就不是一个完全的谜。 一堂课解释观察性研究和随机实验之间的区别，以及混杂变量在解释观察性研究中的作用，比十几堂关于统计推断程序的课更能帮助学生为阅读新闻做好准备。

这篇文章的重点是帮助学生解释统计研究。 那些最终将进行自己的研究和数据分析的学生呢？我认为这些想法对那些学生来说更重要。 我在许多博士考试委员会任职，这些委员会为那些在广泛的学科领域做研究的学生服务。 我问每个学生两个问题，一个是解释p值的含义。 另一个是重复一项有重要发现的研究，但是使用的样本量较小研究人员惊讶地发现重复研究在统计学上并不显著。我要求学生给出可能的解释。 我很遗憾地告诉大家，许多学生很难回答这些问题，即使他们事先被告知我要问他们。 当任何一个上过统计学课的学生都能回答这些问题以及本文主题和相关概念主题的类似问题时，我就知道我们已经完成了教育公民的使命。


[^1]: Jessica Utts是加州大学戴维斯分校统计系教授，ca 95616 ( E-mail：Jmutts @ Ucdavis.Edu )。本文改编自2002年7月举行的第六届国际统计学教学会议的特邀论文，经国际统计学教育协会许可，以修订版形式发表。笔者感谢编辑吉姆·艾伯特( Jim Albert )邀请本期「统计素养」专栏，感谢编辑和三位裁判对本文的精辟评论。
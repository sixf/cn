---
title: PeerJ：下一个PLOS ONE？
layout: post
categories: [学术,科研]
tags: [开放获取,影响因子,期刊,生态,公开审稿,预印本,Open Access,Impact factor]
comments: yes
---

PLOS ONE自2006年发展自今，每年[逾万篇](http://en.wikipedia.org/wiki/PLOS_ONE)的发表论文数量，俨然成了学术期刊界的一条大鲇鱼，而且增长趋势不减。庞大的数量，每篇1350美元的发表费用，PLOS ONE的确赚得盆满钵盈。由于数量庞大，论文质量难免参差不齐，国内不少学者和研究单位对于PLOS ONE的评价也是褒贬不一。

现在把目光转向另外一个新创立的同样为开放获取的期刊--[PeerJ](http://peerj.com)。PeerJ由Peter Binfield(曾在PLOS ONE任职)和Jason Hoyt(曾为Mendeley的首席科学家)于2012年6月份正式创立。虽然同为开放获取期刊，但是PeerJ采用了完全不同的[商业运行模式](https://peerj.com/pricing/)：每篇99美元的发表费用，或者选择终身付费发表，即一次性支付299美元便可以终身无限量地在PeerJ发表论文(感觉有点在做广告!!)。相比于PLOS ONE或者其他作者付费期刊，PeerJ的折扣更大、来势更猛。至于PeerJ之后发展状况如何，则需要时间来检验。

最近趁着PeerJ创刊伊始，我尝试着投了[一篇有关红外相机监测的论文](https://peerj.com/articles/374/)，后来被顺利接收。基于这次投稿经历，我想简单谈谈对PeerJ的一点体会。我利用R语言([R代码下载(3KB)](http://sixf.org/files/code/2014/05/peerj.txt))提取了PeerJ已发表的前365篇论文(2013-02-12到2014-4-22)的基本信息([结果下载(43KB)](http://sixf.org/files/code/2014/05/peerj365.txt))，诸如投稿时间、接收时间、刊出时间、是否选择公开审稿过程和被引用次数等等，作一简单分析。

-	**审稿速度**。不得不承认，PeerJ的审稿速度非常快，从投稿至返回第一次审稿结果的平均中值为[24天](http://blog.peerj.com/post/60259877854/peerj-speed)。我分别统计了该365篇论文在2013年及2014的接收时间(投稿到接收的天数)和刊出时间(接收到刊出的天数)，如下表所示：

---

<table>
	<tbody>
		<tr>
			<td>年份</td>
			<td>论文数量</td>
			<td>接收(中值)</td>
			<td>接收(平均值)</td>
			<td>刊出(中值)</td>
			<td>刊出(平均值)</td>
		</tr>
		<tr>
			<td>2013</td>
			<td>232</td>
			<td>56</td>
			<td>69 ± 46</td>
			<td>23</td>
			<td>26 ± 11</td>
		</tr>
		<tr>
			<td>2014</td>
			<td>133</td>
			<td>71</td>
			<td>81 ± 53</td>
			<td>28</td>
			<td>29 ± 11</td>
		</tr>
		<tr>
			<td>总体</td>
			<td>365</td>
			<td>60</td>
			<td>73 ± 49</td>
			<td>24</td>
			<td>27 ± 11</td>
		</tr>
	</tbody>
</table>

---


-	**公开审稿过程**。我认为这一点是[除了较低的发表费用外](http://blog.peerj.com/post/66773028124/peerj-saves-academia-money)，PeerJ胜过PLOS ONE的另一大举措。PeerJ官网[介绍](http://blog.peerj.com/post/58170809555/peerj-six-month-review)超过80%的作者选择[公开审稿过程](https://peerj.com/reviews/)，即读者可以浏览下载该论文从投稿、修改、编辑意见、审者意见和作者回复信等所有有关审稿过程的内容。我同样分析了该365篇论文的是否公开审稿情况：总体为77%的作者选择公开审稿过程，其中2013年为75%，2014年为81%。看来，的确有更多的作者选择公开审稿过程。当然，除了编辑必须是实名外，将近[43%](http://blog.peerj.com/post/58170809555/peerj-six-month-review)的审者也选择了实名审稿。此处不得不提的是，对于类似我这样的学术新手，如何回复审者和编辑的审稿意见，PeerJ的公开审稿过程提供了大量的第一手学习资料！
-	**编辑阵容**。其实一个期刊的论文质量，很大程度上取决于编辑的阵容。PeerJ目前的[845位编辑](https://peerj.com/academic-boards/editors/)队伍，的确堪称豪华，其中亦不乏诸多诺贝尔得主。我好奇的是，PeerJ至今方才发表近370篇论文，其实绝大多数编辑根本没有审过一篇稿件。于是，我分析了这365篇论文的编辑(Academic Editor)，发现这365篇论文总共有190位编辑，占总编辑数的22%。看来，将近78%的编辑至今还没开工，而开工最多的编辑已经审理了[17篇已发表论文](https://peerj.com/JafriMAbdullah/)。这190位已开始干活的编辑中，80%(152位)的编辑审理了1篇稿件，如下图所示(完整名单点击[此处下载(3KB)](http://sixf.org/files/code/2014/05/editors.txt))：

![](http://sixf.org/files/images/2014/05/peerj_editors.png)

-	**影响因子**。由于PeerJ自2013年才开始发表论文，所以还[未曾有影响因子](http://blog.peerj.com/post/81475988271/announcing-new-data-reports-for-peerj-articles)。不过，我通过提取每篇论文的被引用次数，或许可以一窥端倪。此处，为了更加保守估计论文的被引用情况，我直接采用PeerJ网站上的被引用次数，而不是Google Scholar中的数据，因为Google Scholar收录的期刊种类更多，包括许多非SCI期刊。结果发现，截止今日(2014-05-08)，该365篇论文的平均引用率为0.75，换言之，“影响因子”为0.75。其中，2013年论文的平均引用率为1.1，2014年为0.11。当然，计算2014年的“影响因子”意义不大。虽然这是粗略的估计，但我感觉三四年以后，正式公布的影响因子应该会跟当年的PLOS ONE相似，至少有3分。因为随着时间推移，单篇论文被引用次数会越来越多。
-	**学科分布**。虽然PeerJ[明确表示](http://en.wikipedia.org/wiki/PeerJ)只接收生物科学和医学类的论文，但是在二级学科的分布上，有什么偏向吗？我获取了该365篇论文的学科分类信息，罗列了前20的学科类别(如下图所示，完整名录[点击下载(2KB)](http://sixf.org/files/code/2014/05/subjects.txt))。最多的为生态学(80篇)，占总论文数的21.92%，其次为进化生物学(51篇)和动物学(50篇)。排名前三的原来都是宏观生物学的学科，此时不知该高兴还是痛苦。高兴的是宏观方向稿源这么充足；痛苦的是，宏观方向的传统期刊太少了，影响因子也普遍太低了，所以估摸着就往PeerJ投稿来了。

![](http://sixf.org/files/images/2014/05/peerj_subjects.png)

-	**[PeerJ PrePrints](https://peerj.com/about/publications/#PeerJ-PrePrints)**。预印本文献库，想必大家并不陌生，比如最近吵得沸沸扬扬的“[石头剪刀布](http://news.sciencenet.cn/htmlnews/2014/5/293837.shtm)”研究就是先发布在[arXiv](http://arXiv.org)预印本网站上。PeerJ PrePrints也是一个预印本网站，且免费无限量投稿，而且最快会数小时内在线刊出。这也不得不说是PeerJ的一大创举。
-	**"全程服务"**。我自从投稿开始，到动物伦理审核，到最后刊出，编辑部一直有邮件跟作者保持联系，应该说PeerJ的投稿经历还是相当愉快的。最后稿子接收后，责任编辑[Jackie Thai](https://peerj.com/about/)最后还帮忙修改了一些语法小错误，在此相当感谢。当然，如果想听听PeerJ有哪些优势，官方的介绍有一大堆，比如点[这里](http://blog.peerj.com/post/46261563342/6-reasons-to-publish-with-peerj)，或[这里](http://blog.peerj.com/post/54500700950/7-reasons-why-peerj-is-the-perfect-conference-publisher
)。
-	**美中不足**。最后，对于PeerJ的投稿系统，虽然已经做得相当人性化，但熟悉了类似Scholar One的投稿系统后，刚开始还真是摸不着头脑，幸好在投稿过程中可以联系期刊编辑部帮忙。另外一点是，打开PeerJ的主页非常慢，上传几百KB的文件，都得至少五分钟。令人惊奇的是，文件多次上传失败后，PeerJ的首席执行官(CEO)Jason Hoyt立即发来邮件询问是否需要帮忙。难道Jason这家伙一直在后台监视着？当时，不知是因为国内对PeerJ网站进行了特殊呵护，还是PeerJ的主机跟不上，让投稿过程非常受折磨。后来我怀疑是PeerJ受到国内相关部门的呵护，因为当我最后甩出重磅炸弹，利用国外VPN(俗称fan-qiang)上传文件后，投稿过程则相当顺畅。此时，心想国内投稿还需要使用美国的IP，不免感慨良多。

**总结**：虽然感觉PeerJ有八分PLOS ONE的影子，当前的[一些员工](https://peerj.com/about)也多数来自或者曾在PLOS ONE工作，但是凭着更为大胆、创新的商业模式，PeerJ在未来几年应该能杀出另外一条道路，甚至有超过PLOS ONE的趋势。所以，对于刚开始的问题，"PeerJ，会是下一个PLOS ONE吗”？简单的回答是：青出于蓝而胜于蓝。

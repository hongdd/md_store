---
title: OpenAI dota
date: 2018-09-07 20:12:26
tags: rl dota openai
---
# 在职业5V5中,OpenAI输了,为什么?
暑假在家闲的无事,就观看了dota的ti8比赛,其中的几场OpenAI和人类的职业选手的对战引起了我的注意,在去年的ti7上面,OpenAI在1V1已经可以和人类选手一较高下了,并且在去年也说了,今年会挑战5V5.但是没想到,今年却输了(我只看了前两场),虽然我不懂dota，但是伴着解说的阵阵嘲讽，还是可以知道电脑干了很蠢的操作的,那么，为什么在5V5上会输的这么惨呢?相比较而言,DeepMind的AlphaGo在却围棋上面取得了巨大成功,这两者有什么区别么?是什么原因导致AlphaGo大获成功,而OpenAI却没能战胜人类的职业选手?下面是我个人的一些理解.
## 区别
首先，dota的5V5相比较AlphaGo，我认为这个任务是比较更加困难的，原因有几点点，主要存在于围棋和dota的区别上.
### 策略
第一是策略，对于围棋，是单一策略，你的行为只需要完成一个目标就可以了，但是dota是组合策略，虽然最终的目标是赢，但dota中的策略是有很多的策略是组合起来的，比如，你要刷钱，打盾，出装备，插眼，带线等等。在比赛中，电脑在抓人，单杀法方面是比较强的，但是在出装备等等其他策略上，尤其是插眼这方面是很差的，显然是策略的组合上还是有很多问题的。
### 连续
第二呢，就是离散与连续，围棋是一个离散的游戏，所以AlphaGo可以使用蒙特卡罗模拟，对接下来的几步进行模拟。但是反观dota，我认为是一个连续的问题，不管是人物的位置，还有瞬息万变的场上形势，可能出现的情况非常的多，这也造成了训练上的巨大困难。
### 训练
接下来是训练上的，AlphaGo后面有推出的Zero版本是从零开始的，而第一版的是学习的棋谱，最后的情况是Zero比第一版更加出色，而这次的OpenAI应该也是从零开始的，但我觉得AlphaGo从零开始能得到比较好的策略还是因为围棋的简单导致的，而dota则不同，从点电脑经常在家插眼的行为来看，这部分策略显然是没有学好的，面对复杂策略，我认为还是要拿一些比赛的数据当作训练集的，同时也要将explore相对于exploit的值调大一些，让电脑更加倾向于探索而不是利用已知的最好策略，因为在没有足够的探索的情况下，它认为的最好策略很可能会是一个很蠢的策略。
### 其他
其次，还有很多其他的问题，比如开大打野；没大的时候打团；在打团的时候，并不能很好的配合，经常很多人同时被对面大等等，这也是在人多的时候的组合策略的问题。
## 总结
可以看出，强化学习还有很多的路要走，很需要更加强力的模型来应对组合策略的问题，也希望强化学习能更加快速的发展。发现他们的官网有这次相关的博客,https://blog.openai.com/openai-five/ 里面有更详细的解释,还有一些他们的实现方法.有时间我可能会翻译一下,~~发出了咕咕咕的声音~~.
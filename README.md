# ProductionSystem
人工智能产生式系统 - 球星产生式系统案例

人工智能产生式系统

# 实验目的
理解生产式系统结构原理与实际应用。
掌握生产式规则表示及规则库组件的实现方法。
熟悉和掌握生产式系统的运行机制，掌握基于规则推理的基本方法。

# 实验原理
产生式系统用来描述若干个不同的以一个基本概念为基础的系统，这个基本概念就是产生式规则或产生式条件和操作对。在产生式系统中，论域的知识分为两部分：用事实表示静态知识；用产生式规则表示推理过程和行为。

# 实验内容
建立自己的生产式系统（包括规则库和事实），然后进行推理，即可以自己选择事实，并基于原有的规则和输入的事实进行推理。
建造球星识别系统，根据输入的球星特征判断是哪一位球星或给出相应的回答。
# 算法设计
首先建立事实库
　　事实库是程序开始的时候直接选择的，根据用户的需要选择，即要求用户选择球星的特征进行识别。如果未识别出来，则提示输入有误。

## 球星的特征如下：
西部第八	西部第三	东部第四	东部第一	西部第一	 
火箭队	雷霆队	骑士队	热火队	勇士队	 
35号	13号	12号	30号	3号	23号
前锋	后卫	中锋	 	 	 
杜兰特	哈登	霍华德	库里	韦德	詹姆斯

# 建立静态规则库
　　即建立产生式规则，采用产生中间试试的方法，便于建立和使用规则。

　　为了方便设计，我们把要是别的球星限制在6个，这样所需的产生式规则就比较少，本算法一共有11种规则：

　　　　R1：如果是西部第八，则球星为火箭队。

　　　　R2：如果是西部第三，则球星是雷霆队。

　　　　R3：如果是东部第一，则球星是骑士队。

　　　　R4：如果是东部第四，则球星是热火队。

　　　　R5：如果是西部第一，则球星是勇士队。

　　　　R6：如果是雷霆队，且为35号且为前锋，则球星为杜兰特。

　　　　R7：如果是火箭队，且为13号且为后卫，则球星为哈登。

　　　　R8：如果是火箭队，且为12号且为中锋，则球星为霍华德。

　　　　R9：如果是勇士队，且为30号且为后卫，则球星为库里。

　　　　R10：如果是热火队，且为3号且为后卫，则球星为韦德。

　　　　R11：如果是骑士队，且为23号且为前锋，则球星为詹姆斯。

## 正向推导过程
　　从已知事实出发，通过规则库求得结论，或者成为数据驱动方式，推理过程为：

   规则集中的规则前件与事实库中的事件进行匹配，得到符合要求的规则集，将规则集的后件替换到新的事实集作为一条新的事实集，重复这个过程，知道达到最终目标。

# 实验结果及分析
　　比如：西部第八    12号      中锋。则系统推理过程如下：

   事实集为 西部第八 12号 中锋。

   先从规则库中匹配R1，事实集变为 火箭队 12号 中锋。

   再次匹配规则集R8，获得球星霍华德。
   
 # 实验总结
   本系统的规则库是静态的，不能很好的进行增删改操作，这使得在规则的情况下不能及时改变，但是该系统已经能基本满足，对输入的事实给出相应的回答，判断是那个球星。理解了生产式系统结构原理与实际应用。能够掌握生产式规则表示及规则库组件的实现方法。熟悉和掌握了生产式系统的运行机制，掌握了基于规则推理的基本方法。
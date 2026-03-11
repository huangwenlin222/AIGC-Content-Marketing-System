# AIGC-Content-Marketing-System
## 1.概述
1.项目名称：基于多智能体与GEO优化的全链路AIGC内容营销系统

2.系统全链路图

<!-- <img width="1581" height="244" alt="image" src="https://github.com/user-attachments/assets/292e1f5a-2ee1-4e3c-ba78-0c3db4df7d53" /> -->

（2）数据洞察模块：负责全网热点抓取与痛点分析。

（2）多模态生成模块：负责多模态（图文/视频）内容的原始创作。

（3）GEO 质检优化模块：负责内容的标准化评估与自动化优化。

（4）营销钩子植入模块：负责将“线上流量”导向“线下转化”的场景化加工。

（5）全链路调度与交互接口模块：负责逻辑串联与前后端通信，实现可视化操作。

## 2.核心功能模块
### 2.1 数据洞察模块
1.功能概述

全网热点抓取与痛点提炼，从而发现热点话题。将非结构化全网信息转化为结构化营销策略。

2.实现流程

（1）全网泛搜：调用 Tavily API 针对预设领域进行全网扫描。

（2）原始数据清洗：抓取搜索结果中的文本摘要，过滤无关信息。

（3）痛点提炼：利用 LLM 对海量信息进行降维，提炼热点话题列表。

### 2.2 多模态生成模块
1.功能概述

通过CrewAI框架模拟现实“数字营销团队”，构建AIGC双工作流，实现多模态内容生成。

2.实现流程

（1）图文流

<!-- <img width="1484" height="112" alt="image" src="https://github.com/user-attachments/assets/16591c9e-7b53-4731-98b0-726ccaec83db" /> -->

（2）视频流

### 2.3 GEO质检优化模块
1.功能概述

实现GEO自动化质检与迭代优化。引入GEO (生成式引擎优化) 标准，确保内容的高质量。

2.实现流程

（1）分析引擎：从专业度、相关性、互动感三个维度给初稿打分。

（2）逻辑判断：若分数低于阈值，则进入循环。

（3）优化引擎：根据质检报告的“差评”点进行针对性重写。

（4）闭环验证：重写后的文案再次送检，直至合格。

<!-- <img width="200" height="300" alt="image" src="https://github.com/user-attachments/assets/53c16478-6388-4da5-983c-754692a14f97" /> -->

### 2.4 营销钩子植入模块
1.功能概述

实现线下引流闭环。根据文案语境，自动从策略库中挑选最合适的“到店诱因”。

2.实现流程

（1）语境识别：LLM 分析文案 2.0 所在的场景。

（2）钩子匹配：从引流钩子数据库中匹配相关性最高的钩子。

（3）自然融合：将营销信息自然地融合于文案，形成文案 3.0。

## 3.效果示例
1.数据洞察模块的实时热点监测

如图展示系统实时抓取的社交平台热点词云及“痛点降维”后的热点话题列表。

<!-- <img width="200" height="240" alt="image" src="https://github.com/user-attachments/assets/15ba275f-a6ef-489a-80bc-51c5ee13e4fb" /> -->

2.多模态生成模块：自动化AIGC工作流的多模态内容生成

如图以“英语六级听力速成”话题为例，展示了系统生成图文笔记的效果示意图。

<!-- <img width="1257" height="605" alt="image" src="https://github.com/user-attachments/assets/0b2d0f30-9c82-4cf2-a5af-78fd8eccdb81" /> -->

3.GEO质检优化模块

如图展示同一文案在经过分析引擎打分与优化引擎重写后，在语义密度、人称视角及关键词权重上的量化改进。

<!-- <img width="300" height="240" alt="image" src="https://github.com/user-attachments/assets/b89b2fc6-bfad-4344-a6c2-dccfa192804b" /> → <img width="400" height="340" alt="image" src="https://github.com/user-attachments/assets/2b1d3bf7-1bed-48a4-97f9-d8c867da6956" /> -->

## 4.代码说明
1.数据洞察模块：topic_find.py

2.多模态生成模块：aigc_flow5.py

3.GEO质检优化模块：geo_tool2.py

4.营销钩子植入模块：traffic_hook_tool.py；钩子数据库：hooks.json

注：视频脚本处理工具：videocopy_split.py 分割hooked_copy.txt中的文案，返回{"tittle":标题，"content":内容,"tags":标签}的格式

5.全链路调度与交互模块：

全链路调度：main_workflow.py

交互：后端接口，app.py

> - 参考：[Datawhale-every-embodied](https://github.com/datawhalechina/every-embodied/tree/main/07-%E6%9C%BA%E5%99%A8%E4%BA%BA%E6%93%8D%E4%BD%9C%E3%80%81%E8%BF%90%E5%8A%A8%E6%8E%A7%E5%88%B6/Locomotion) 的[07-机器人操作、运动控制/Locomotion/01春晚舞蹈机器人复刻](https://github.com/datawhalechina/every-embodied/blob/main/07-%E6%9C%BA%E5%99%A8%E4%BA%BA%E6%93%8D%E4%BD%9C%E3%80%81%E8%BF%90%E5%8A%A8%E6%8E%A7%E5%88%B6/Locomotion/01%E6%98%A5%E6%99%9A%E8%88%9E%E8%B9%88%E6%9C%BA%E5%99%A8%E4%BA%BA%E5%A4%8D%E5%88%BB.md) 
>   
> - 核心流程参考原教程，仅"**附录：手动配置方案参考(phmr环境)**"替换为本文方法。
> - PS：原教程是**云端部署 & 40系显卡**，本笔记是**本地部署（WSL系统） & 50系显卡（5060Ti）方案**                                                                                     ——郑群 上海大学

### Part1 概述：与原教程的差异

1. 把**环境变量**配置在conda里，而不是系统的`~/.bashrc`里，避免污染系统环境 （参考：[KeyNotes1]()）
2. **编译cpp扩展**时：
	1. （算力自由平台上好似已经配好了可以不用管）安装适配于自己GPU的系统级CUDA Toolkit；并在虚拟环境中配置cuda的路径 （参考：[报错1_OSError]()）
	2. 对于50系显卡（cc：90以上）：编译 `droidcalib` 前需要在`video2robot/third_party/PromptHMR/pipeline/droidcalib/setup.py` 添加对应的`sm_???`  （参考：[报错2_CUDA error: no kernel]()）

| 目录    |                    |                                                  |
| ----- | ------------------ | ------------------------------------------------ |
| Part1 | 概述：与原教程的差异         | 概述                                               |
| Part2 | 方案（简洁/直接版）         | [方案（简洁/直接版）]()                                   |
| Part3 | 原理                 | [KeyNotes1_环境变量配置]()<br>[KeyNotes2_编译cpp扩展]()    |
| Part4 | 报错：原理-问题诊断-解决方式-检验 | [报错1_OSError]()<br>[报错2_CUDA error: no kernel]() |

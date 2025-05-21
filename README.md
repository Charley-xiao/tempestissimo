<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=13&height=250&text=%E7%BC%96%E8%AF%91%E9%A3%8E%E6%9A%B4&fontColor=FFFFFF&fontSize=80">
</div>

> 你知道吗？此段记忆，此篇关于光明与纷争的故事……
> 
> ……以一粒装满了感情的种子被埋进土中为始。
> 
> 然后，在被珍视和被唾弃的回忆的共同滋养下开始生根发芽。
> 
> 再然后，它便茁壮成长，执拗地想去到更高的地方，一如这执拗的时间。
> 
> 随着她们醒来，命运的齿轮也开始转动——一个被祝福的女孩的的命运和一个被诅咒的女孩的命运开始编织。
> 
> 随后，一切便又遗忘于历史的长河之中。
> 
> ——《Arcaea》

在 Arcaea 破碎的玻璃天空中，记忆碎片飘浮不定，光之少女 Hikari 与其影之镜像 Tairitsu 不断分离又重聚。如今，主线已推进至多重世界线交汇的末端――裂隙正在吞噬昔日的旋律，而你被选为「调律者」，携手四位编译伙伴（GNU·光翼、Intel·辉曜、LLVM·灵纹、AOCC·裂电），修复两枚关键主旋律硝片，否则 Hikari 与 Tairitsu 的最终 Reunion 将化为泡影。

<div align="center">
<img src="./assets/teaser.png">
</div>

## 硝片与世界危机

### LULESH：失落的世界

> 在爆裂遗迹中，过量能量令光域土崩瓦解；Hikari 无法稳住冲击波前，世界结构在一呼一吸之间震颤。

LULESH 是 LLNL 发布的冲击流体力学 proxy-app，采用 3-D stencil 近似 Sedov 爆震问题，极度考验编译器的向量化与 OpenMP 调度。该任务要求详见 [docs/lulesh.md](./docs/lulesh.md).

### miniFE：谜域的界外

> 分歧的回响构筑出「谜域」——稀疏通道被噪声遮蔽，Tairitsu 的残响无法回到光域。只有精准重建稀疏网格，才能听见她的求救。

miniFE 来自 Sandia 的 FEM mini-app，内核为稀疏矩阵‐向量乘和共轭梯度迭代；常用来评估 NUMA 亲和、缓存友好布局与编译器 unroll、prefetch 策略。该任务要求详见 [docs/minife.md](./docs/minife.md).


## 编译伙伴

| 编译器 | 代号 | 引导文档 |
|:---:|:---:|:---:|
| GNU | 光翼 | [docs/guide_gnu.md](./docs/guide_gnu.md) |
| Intel | 辉曜 | [docs/guide_intel.md](./docs/guide_intel.md) |
| LLVM | 灵纹 | [docs/guide_llvm.md](./docs/guide_llvm.md) |
| AOCC | 裂电 | [docs/guide_aocc.md](./docs/guide_aocc.md) |

## 评分

世界危机的解决离不开计算的正确性与性能的提升。每个应用都提供了正确性检验的脚本，若无法通过精度检查，该硝片记为无效。在精度检查通过的情况下，评分公式为：
- 性能（满分 70）：$S_{\rm{perf}}=\dfrac{70}{8}\times \sum\limits_{i=1}^2\sum\limits_{j=1}^{4}\dfrac{T_{0,i,j}}{T_{i,j}}$. 其中 $T_{0,i,j}$ 为第 $i$ 个应用应用第 $j$ 种编译器的基准运行时间（详见各应用文档），$T_{i,j}$ 为优化后的运行时间。
- 技术报告（满分 30）：可能包括硬件剖析、flag 对比、误差处理、火焰图等内容。该得分会根据组间对比以及报告质量等进行调整。

## 成就

成就会给予额外的分数奖励，具体如下：

| 成就 | 说明 | 额外分数 |
|:---:|:---:|:---:|
| 流星 | 某一应用在速度榜单上进入过前 20%（榜单总人数不少于五人）| +2%\* |
| 超越领域 | 某一应用在速度榜单上进入过前 10%（榜单总人数不少于五人）| +5%\* |
| 反应训练 | 比赛开始后 48 小时内提交 | +2% |
| 残存的回忆 | 最后一次提交在比赛开始后 168 小时内 | +3% |
| 第一名 | 某一应用在速度榜单上进入过第一名（榜单总人数不少于五人）| +10%\* |
| 再加把劲 | 某一应用在速度榜单上进入过第二名（榜单总人数不少于五人）| +5%\* |
| 优等生 | 某一应用在速度榜单上进入过第三名（榜单总人数不少于五人）| +3%\* |

\*：可逐应用叠加，但不逐时间叠加。

## 攻克路径推荐

### 复现 Baseline

确认各应用在 `gcc -O2` 下全部通过校验脚本。

### Compiler Partner 调参

下面列举一些常用的编译器调参套路，供参考。详细教程见各编译伙伴文档。

| 步骤                  | 目标                    | 技巧 / 参考                                                                                                  |
|:-------------------:|:---------------------:|:--------------------------------------------------------------------------------------------------------:|
| **热点剖析**          | 找到热点函数       | `perf record`, `gprof`, `-qopt-report` (Intel)                                                           |
| **编译选项扫描**          | 快速找到合适编译选项          | `gcc -O3 -march=native -flto`, 再叠加 `-funroll-loops`, `-fprefetch-loop-arrays`；或 `icx -ipo -Ofast -xHost` |
| **向量宽度**          | 利用 AVX‑512 / Zen4 ISA | `-qopt-zmm-usage=high` (Intel)；`-mprefer-vector-width=256` (AOCC)                                        |
| **LTO / ThinLTO** | 跨模块内联、去冗余             | `-flto=thin` (Clang 18)                                                       |
| **PGO**           |  基于 Profiling 调优    | `-fprofile-generate/use` (GCC)；`-prof-gen/use` (Intel)|
| **NUMA 调和**       | miniFE 调优             | `numactl -C 0-111 -m 0`; `KMP_AFFINITY=granularity=fine,compact`                                         |

## 交付方法

### 赛中评测

赛中评测会集中在每周二、五进行，评测结果与榜单会在微信群中公布。请将压缩包命名为 `teamname.tar.gz`，其中 `teamname` 为队名，并作为附件发送邮件至 [12211634@mail.sustech.edu.cn](mailto:12211634@mail.sustech.edu.cn). 压缩包的结构如下：

```
<teamname>.tar.gz
├── lulesh/
│   ├── build.sh # 编译脚本，必须支持 `./build.sh <compiler>`
│   └── run.sh # 运行脚本，必须支持 `./run.sh <compiler> <input_file>`
└── minife/
    ├── build.sh # 编译脚本，必须支持 `./build.sh <compiler>`
    └── run.sh # 运行脚本，必须支持 `./run.sh <compiler> <input_file>`
```

评测流程：
1. 编译：评测组会在 `lulesh` 和 `minife` 目录下运行 `./build.sh <compiler>`，编译器为 `gcc`, `icx`, `clang`, `aocc` 中的一个。
2. 运行：评测组会在 `lulesh` 和 `minife` 目录下运行 `./run.sh <compiler> <input_file>`，`<input_file>` 为各应用的基准输入文件。
3. 正确性检验：评测组会使用正确性检验脚本检查输出结果的正确性，若无法通过精度检查，该硝片记为无效。

评测结束后，评测组会将评测结果与榜单在微信群中公布。请注意，评测组不会提供任何评测反馈。每次评测只会去每队的最新提交进行评测，若有多次提交，非最新的提交不会被评测，请确保最新提交的压缩包符合要求。

### 赛后评测

赛后评测会在比赛结束后进行，比赛最后的分数会在微信群中以及通过邮件公布。请在比赛结束前，将压缩包命名为 `teamname_final.tar.gz`，其中 `teamname` 为队名，并作为附件发送邮件至 [12211634@mail.sustech.edu.cn](mailto:12211634@mail.sustech.edu.cn). 压缩包的结构如下：

```
<teamname>_final.tar.gz
├── lulesh/
│   ├── build.sh # 编译脚本，必须支持 `./build.sh <compiler>`
│   └── run.sh # 运行脚本，必须支持 `./run.sh <compiler> <input_file>`
├── minife/
│   ├── build.sh # 编译脚本，必须支持 `./build.sh <compiler>`
│   └── run.sh # 运行脚本，必须支持 `./run.sh <compiler> <input_file>`
└── report.pdf # 技术报告，PDF 格式
```

## 说明与致谢

本赛题为南方科技大学 2025 年超算比赛基础赛道编译优化赛题。本赛题所有资源遵循 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 协议，允许非商业性使用与修改。同时，[GitHub 仓库]() 已开放讨论区，欢迎大家在此讨论与交流。如有任何问题，请提出 issue 或联系 [12211634@mail.sustech.edu.cn](mailto:12211634@mail.sustech.edu.cn). 出题人：[Charley-xiao](https://github.com/Charley-xiao).

---

> 于某个瞬间，某个地点，回忆的档案开始将它们织成丝线，而于万千丝线之中：
> 
> 命运的丝线牵引着的，是两位少女的灵魂。
> 
> 这通透无色的丝线闪闪发光，未曾受到过伤害，理想地恰如其分：
> 
> 只因它们是关于光明和纷争的丝线。
> 

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=13&height=80&section=footer&fontSize=80">
</div>
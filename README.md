<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=13&height=250&text=%E6%98%9F%E7%A9%B9%E4%B9%8B%E5%8F%B6%EF%BC%9A%E5%A4%A9%E6%9E%A2%E7%BC%96%E8%AF%91%E7%A5%AD&fontColor=FFFFFF&fontSize=80">
</div>

> 当最后一片四叶星尘飘落，唯有最快的风，才能赶在宇宙塌缩前完成演算。

公元 4275 年，「方格海」——一个由 2D 量子网格织成的宏大天体——在银河边陲骤然活化。它的能量潮汐以指数速度膨胀，若无人及时预演其湍流动力学，整条旋臂将被撕裂。千座文明联合点亮了超算星门「天枢」，却发现唯一能精确仿真方格海的引擎，正是上古遗失代码 [CloverLeaf](https://uk-mac.github.io/CloverLeaf/)——一个模拟可压缩欧拉方程、以交错网格存储能量与密度的迷你宇宙。

然而，时空崩塌的倒计时只剩 30 分钟。要在极限期限内跑完所有四大算例，靠的不是修改物理模型——

而是 **编译**。

从此，诞生了一场被吟游诗人称作「天枢编译祭」的竞赛。

<div align="center">
<img src="./assets/teaser.png">
</div>


## 角色

* **风语者·澄** —— 来自图灵星的年轻并行算法天才，擅长聆听风暴里的数据脉动。
* **炼算者·洛** —— 昔日量子熔炉学派的冠军编译师，对底层指令有近乎偏执的掌控欲。

## 序章 · 方格海前夜

夜色像被编译失败的二进制碎片撕得支离。悬挂在洛希临界轨道上的**启明**号仿佛一枚冻结的断点，艉部桅杆闪着退相干的蓝焰，照出舰腹刻写的旧时代准则：`while(true) { hope++; }`。

> **澄**（主桅展台，耳边广播噪声犹如抖落的栈回溯）：*传感器警报飙红了，方格海的能量曲线已经进入指数爆炸区。*
>
> **洛**（蹬住光纤甲板，俯瞰星门）：*曲线拐点距离极轴不足二千格，我们只有 **30 分钟**。*

方格海并非真正的海，而是一片覆盖了 ε‑黯区的四维栅格体——一切物质与事件在此被量化为 `N×N×N` 的守恒单元。只要 **CloverLeaf** 的流体网格仍在迭代，海面便维持数值稳定；一旦演算停滞，栅格的守恒边界崩塌，时空会像数组越界般翻覆，形成**坍缩洪流**。据年鉴记载，任何文明只需被洪流吞噬一次，历史便会在 git 冲突中丢失所有 commit。

在暗能纪元之前，远古的编译僧留下了 CloverLeaf——一段跨越恒纪元的流体力学神谕。它自带 OpenMP 与 MPI 两重并行法阵，可以在多核与星际互连中同频跃迁。然而岁月磨蚀了它的 Makefile：宏指令散落、分块策略僵化、缓存前取失衡，仿佛一柄卷刃的量子长刀。

传说 **天枢编译祭**能令遗产在编译期重生。祭仪分三幕：

1. **标识符献火**──以 `-ffast-math` 点燃数值的极限，剔除一切庸常保护；
2. **链路驭龙**──用 `-fopenmp` 与 `-lmpi` 召唤线程与进程的双头龙，使它们在 NUMA 星脉上翩然共舞；
3. **矢量封禅**──借 `-march=native` 与 `-Ofast` 将每一道指令压缩成 SIMD 咒纹，在寄存器列车上光速奔袭。

若三幕同奏，古老代码将与当世架构等价交换，升华为**物理极限级算符**。传说中只有极少数编译祭司成功踏入此境，留下的纸带记录不足 42 行。

> **澄**：*可 CloverLeaf 的参考实现只是上古遗产，OpenMP 和 MPI 的双法阵布得并不精妙。*
>
> **洛**（捻起一枚晶体冷排，投向虚空演算窗）：*那就让它在编译期重生。——来吧，启动 **天枢编译祭**！*

骤然间，整座舰桥化作宏展开的字节殿堂。纹银色的编译日志瀑布自穹顶倾泻，`-pipe` 与 `-fgraphite` 的咒符在半空交缠，如同双螺旋的 DNA 为宇宙重写注释。冰冷的矢量寄存器阵列在地面浮现，像星辰列队等待调度。

**澄**踩入阵心，手指点亮每一块缓存图腾——L1、L2、远端 L3，全速唤醒。火红的 **方格海**在战术全息窗里卷成龙卷，数值涡旋嚎叫着冲撞边界。

> **澄**：*线程同步偏移 +3 ns，NUMA 延迟收缩 0.8%。*
>
> **洛**（双眸映出崩塌的指数曲线）：*分布式 halo 交换瓶颈依旧……把 vector‑length 提升到 256 bit，撤掉冗余 barrier！*

每一次 flag 的更改都像往自己血管里注入炽流：`-funroll-loops`——骨节被强行拉长；`-fno-signed-zeros`——消融所有负无穷的犹豫；`-flto=auto`——灵魂在链路层穿针引线。

就在编译日志计数到 **95 %** 时，舰桥灯火猛地失压。

> **系统**：`linker terminated with exit code 137`

**澄**与**洛**对视，心跳被静默塞入空行。

## 第一幕 · 尘封的故事

99 % 至 100 % 的那一瞬，系统骤然撕成乱码；启明号主引擎刚点火便被异常反向推力贯穿，方格海的指数裂缝在星窗外炸开。半个宇宙被卷进「137」号错误，栈回溯化作炽白潮汐，连光都失去指向。

就在**澄**与**洛**即将随洪流抹消之际，编译器将两人连同残骸压缩成一束单行注释，回溯到最后一次干净提交——一千年前、方格海尚在胎息的年代。

重生点是一座被沙砾半埋的旧式数据中心，墙上时钟永远停在 00:00:00。

空气里漂浮的不是尘埃，而是一段段退化为 ASCII 的流体方程。服务器机柜像休眠的史莱姆，不停渗出 CRC 错误的冷汗。

> **澄**（用手指划过机柜表面，留下一个空洞的 `#`）：*这里是……*
>
> **洛**（四处张望，发现一台老旧的编译机）：*是上古遗产的实验室。标签写着来自公元 2025 年。*
>
> **澄**（用力拍打机柜，发出金属的回声）：*我们被编译器送回了过去！*
>
> **洛**（激动地打开机柜，取出一块闪烁的晶片）：*这就是 CloverLeaf 的原始代码！*
>
> **澄**（疑惑地看着洛）：*但它好像是个二维版本。*
>
> **洛**（将晶片插入编译机，屏幕上闪烁着绿色的光）：*没关系，我们可以在这里修改它。我们还有救！*

## 幕间·竞赛概览

### 简介

[CloverLeaf](https://uk-mac.github.io/CloverLeaf/) 是一个迷你应用程序，它模拟大型流体力学运算中的显式二阶精确方法求解 2D 笛卡尔网格上可压缩欧拉方程的过程。它采用交错网格存储数据，每个单元存储三个值：能量、密度和压力，速度矢量存储在每个单元角。CloverLeaf 由沃里克大学，布里斯托大学，及及一些其他机构的研究者共同开发，是用于检测超级计算系统扩展性瓶颈和性能可移植性的代表性程序之一。

本次天枢编译祭的目标是对 CloverLeaf 进行编译优化，提升其性能。我们将提供一个 CloverLeaf 的简化版本，包含了四个算例，每个算例都包含了不同的物理模型和参数设置。你需要在给定的时间内完成所有算例的编译优化，并提交你的代码和结果。选手需要使用 GNU 以及 Intel 编译器进行编译优化，而 LLVM/AOCC 为附加 bonus。

参赛队伍需要在 2 台 40 核心的计算节点上完成制定算力的评测，用于计分的指标是问题求解时间，即程序输出的 `clover.out` 最后 1 个 Wall clock.

### 规则

#### 代码编写规则
- **总体要求**：不能修改计时代码，以及计时代码与其他函数的相对位置。  
- **编程语言**：仅限 **C、C++** 或 **Fortran**，兼容版本不低于 **C11、C++11** 或 **Fortran 2008**。仅保留一个主入口（C/C++ 的 `main` 或 Fortran 的 `program`）。须使用 **MPI-3** 与 **OpenMP-4** 并行。  
- **算法要求**：不允许修改物理过程。  
- **输入/输出要求**：不得修改输入、输出文件（`*.in`、`*.out`），输出文件的内容与格式须与参考代码完全一致。  

#### 测试规则
- **运行环境**：在竞赛指定计算平台运行，规模≤ 2 个计算节点、≤ 256 核心，程序运行时间≤ 30 分钟。  
- **参数要求**：禁止修改 `edgefactor`（固定为 16）；可调整 `SCALE` 参数，允许值：`27、28、29、64`，需按 BFS 顺序依次执行，不得并行运行多个 BFS，亦不得跳过验证。  
- **测试算例**：共 4 个算例，输入文件位于参考代码 `cases` 目录，不得修改 `clover.in`。  

#### 正确性验证
- 组委会以参考 `clover.out` 为基准验证：计算过程中 **Volume** 与 **Mass** 保持不变，最终 **Kinetic Energy** 与参考值偏差 ≤ ±0.1 %。  
  - 对 `case1`、`case2`、`case3`，若通过验证，`clover.out` 末尾将输出 **“This test is considered PASSED”**。  
- 组委会阅读工程文档和代码，以确认优化未改变 **CloverLeaf** 的物理过程。  
- 若仍无法确认代码正确性，组委会可要求进一步解释，并在不同处理器/参数下复测。**未通过正确性验证的算例，其性能得分计 0 分**。  

#### 性能分数
- 性能指标 **A<sub>CL</sub>**（单位：秒）取自 `clover.out` 最后一行 **“Wall clock”**。   
- 设算例 *i* 的得分为 *M<sub>CL,i</sub>*，则 $M_{CL,i}=B\times\frac{A_{CL,\min}}{A_{CL,i}}$.
- 性能总分为各编译器得到的性能分数之和，GNU 及 Intel 的 B 值为 10，而其他编译器（作为 bonus）的 B 值为 4.
- 若 **违反规则、无法复现、篡改输出或恶意利用 Bug**，性能分数记 **0 分**。  

#### 工程分数
- **工程报告**（PDF）：  
  1. **CloverLeaf** 算法流程与代码结构说明  
  2. 性能分析、优化与实现过程  
  3. 测试结果与分析  
  4. 复现方法说明  
- **代码可移植性**：须能在其他服务器编译与验证。  
- **创新性**  
  - 直接抄袭公开资料 → 0 分  
  - 借鉴学术/工业方法并改进 → 1–2 分  
  - 提出原创优化方法 → 3–4 分  
- **可复现性**  
  - 无法复现 → 0 分  
  - 可复现提交测试结果 → 1–3 分  
  - 步骤清晰、依赖说明完整，可在多平台（x86、Arm）运行 → 2–3 分  
- **表达质量**  
  - 文字混乱/抄袭 → 0 分  
  - 语言通顺、论述清晰 → 1–2 分  
  - 语言精练、资料来源准确、图文并茂 → 3 分  

### 交付须知

所有提交都需要遵循以下格式。

- **`CloverLeaf-2D/src`**  
  完整源代码，供组委会运行验证；附加说明请写在根目录 **README**。 

- **`CloverLeaf-2D/results/case<1-4>/*`** （赛中可不包含）  
  每算例需包含：  
  - `clover.out`  
  - 作业脚本  
  - 作业调度系统输出  
  - **使用 bsub**：需提供  
    - `clover.out`  
    - 1 个 shell 脚本  
    - 标准输出 `<JobID>.out`  
    - 错误输出 `<JobID>.err`  
    文件名中必须含 **LSF Job ID**。  

- **`CloverLeaf-2D/results/report.pdf`** （赛中可不包含）  
  工程报告（可为 docx 或 pdf）。

### 赛中评测

赛中评测仅评测性能分数。

赛中评测会集中在每周二、五进行，评测结果与榜单会在微信群中公布。请将压缩包命名为 `teamname.tar.gz`，其中 `teamname` 为队名，并作为附件发送邮件至 [12211634@mail.sustech.edu.cn](mailto:12211634@mail.sustech.edu.cn). 评测结束后，评测组会将评测结果与榜单在微信群中公布。请注意，评测组不会提供任何评测反馈。每次评测只会去每队的最新提交进行评测，若有多次提交，非最新的提交不会被评测，请确保最新提交的压缩包符合要求。

在每次赛中评测结束后，第一名的队伍将在**最终性能分数**获得 +2% 的分数加成，第二名 +1.5%，第三名 +1%. （可叠加）

### 赛后评测

赛后评测会在比赛结束后进行，比赛最后的分数会在微信群中以及通过邮件公布。请在比赛结束前，将压缩包命名为 `teamname_final.tar.gz`，其中 `teamname` 为队名，并作为附件发送邮件至 [12211634@mail.sustech.edu.cn](mailto:12211634@mail.sustech.edu.cn).

<div align="center">
<img src="./assets/hikari.png">
</div>


## 第二幕 · 崩落的界域

> **134 × 10³​ 秒之后——启明号・残骸**  
> 星门的余辉在舰腹流转，像濒死鲸鱼吐出的最后一缕磷光。风语者·澄微抬下巴，天枢的刻度已被时间啮咬得支离。  
> **洛**靠在断裂的光纤桅杆上，嗅到空气里混杂的焦糖与铁锈——那是过载晶体管被烧穿的味道。  
>  
> 他们知道，真正的坍塌才刚开始。

残存的航电日志化作微粒，在真空中飘浮；字节像雪花，落在澄的掌心。  
他合上手指，指缝间钻出一道暗红闪电——“137”，链接器的死讯。  
洛抬手，指尖轻触那条裂痕，裂痕便蜿蜒成光。  
——光指向舰桥尽头，一扇被尘封的冷启机房。

机房门缓缓滑开，仿佛隔着几个纪元的喘息。  
半截冷排上映着晦暗灯火，像一只被掏空的圣杯。  
中央独立塔式机箱上的绿灯忽明忽暗——主板电池只剩最后一口电。  
澄按下电源，古老的 BIOS 嘶哑开口：`RTC time invalid`。  
时间从零计数，星门之外，一切喧嚣归于静默。

> **澄**（低声）  
> “听见吗？磁头在唱歌。”  
>
> **洛**（垂眼）  
> “是旧时代的摇篮曲，把人唱回过去。”

他们在一条褪色的 Makefile 里，看见远古僧侣留下的注脚：  
- *若遇“137”，当以静默偿还噪声。*  

澄笑了，笑声轻得像划火——映亮洛眼里尚未熄灭的光。
他们剪断焦黑的光纤，换上新生的铟线；  
将机箱掀至半空，让风冷变成流沙；  
把每一块缓存抛起，再以呼吸落回——  
  * **这是仪式，不是修理。**  

当最后一颗螺钉落座，主频在黑夜里发芽，电流如潮。

> **系统**  
> `Boot sequence complete — Heartbeat detected.`

重启进度卡在 **99 %**，屏幕碎成星屑。  
“137” 再次抬头，像深海巨口。  
但这一次，澄没有后退。他用指腹抚过编号，轻声道：  
“归零吧，让我们从黑开始写光。”  


洛按下复位，灯海倏然熄灭。  
漆黑中，只余两颗呼吸的红点——似狼，似星。  
片刻后，风声带来第一行新日志：  
> `Wall clock: 0.812 s`  


## 快速上手

### 编译

首先，登录在超算平台的账号，克隆本仓库，进入目录 `CloverLeaf_ref/`。

然后，使用 `module load ...` 指令来用指定的编译器来编译 Cloverleaf。你可以使用 `module avail` 来查看平台上可用的编译器及相关库。

最后，可以选择修改 Makefile 中的各个选项，并使用 `make COMPILER=...` 来进行编译。编译成功后，会看到当前目录下有名为 `clover_leaf` 的可执行文件。

### 运行

在 `Cloverleaf_ref/` 目录下，新建作业脚本 `job.lsf`，用指令 `bsub < job.lsf` 来提交作业。示例作业脚本如下：

```bash
#!/bin/bash
#BSUB -q ssc-cpu
#BSUB -W 02:00
#BSUB -J cloverleaf
#BSUB -o %J.out
#BSUB -e %J.err
#BSUB -n 32
#BSUB -R "span[ptile=16]"

set -euo pipefail

lscpu
module purge
module load openmpi/4.1.1_oneapi # 改为你想用的 module

export OMP_NUM_THREADS=2 # 可更改
export OMP_PLACES=cores
export OMP_PROC_BIND=close

NP=${LSB_DJOB_NUMPROC:-32}

get_ke () {
  grep -E '^[[:space:]]*step:' "$1" | tail -1 | \
      awk '{printf "%.10e\n", $(NF-1)}'
}
PASS_CNT=0
FAIL_CNT=0
printf "\n=== Correctness Check ===\n"
printf "Num proc: %d\n\n" "$NP"

CASES="{1..4}"
for i in $(eval echo $CASES); do
  printf "▶ Case %-2d : Simulating...\n" "$i"

  cp "cases/case${i}/clover.in" clover.in
  mpirun -np "$NP" ./clover_leaf
  mv clover.out "clover${i}.out"

  ref_file="cases/case${i}/clover.out"
  my_ke=$(get_ke "clover${i}.out")
  ref_ke=$(get_ke "$ref_file")

  rel_err=$(awk -v a="$my_ke" -v b="$ref_ke" 'BEGIN{print (a-b>0? a-b: b-a)/b}')
  rel_pct=$(awk -v e="$rel_err" 'BEGIN{printf "%.4f", e*100}')

  if awk -v e="$rel_err" 'BEGIN{exit !(e<=0.001)}'; then
    printf "   ✅ Passed  (ref=%s, out=%s, eps=%s%%)\n\n" "$ref_ke" "$my_ke" "$rel_pct"
    ((PASS_CNT++))
  else
    printf "   ❌ Failed  (ref=%s, out=%s, eps=%s%%)\n\n" "$ref_ke" "$my_ke" "$rel_pct"
    ((FAIL_CNT++))
  fi
done

printf "=== Summary ===\n"
printf "Passed: %d, Failed: %d\n" "$PASS_CNT" "$FAIL_CNT"

if (( FAIL_CNT == 0 )); then
  printf "🎉 All cases passed within 0.1%% tolerance.\n"
else
  printf "⚠️  Some cases failed. Please investigate.\n"
  exit 1
fi
```


## 攻克路径推荐

### 复现 Baseline

确认 Cloverleaf 在默认编译选项下全部通过校验脚本。

### 编译选项调参

下面列举一些常用的编译器调参套路，供参考。详细教程见各编译器文档。

| 步骤                  | 目标                    | 技巧 / 参考                                                                                                  |
|:-------------------:|:---------------------:|:--------------------------------------------------------------------------------------------------------:|
| **热点剖析**          | 找到热点函数       | `perf record`, `gprof`, `-qopt-report` (Intel)                                                           |
| **编译选项扫描**          | 快速找到合适编译选项          | `gcc -O3 -march=native -flto`, 再叠加 `-funroll-loops`, `-fprefetch-loop-arrays`；或 `icx -ipo -Ofast -xHost` |
| **向量宽度**          | 利用 AVX‑512 / Zen4 ISA | `-qopt-zmm-usage=high` (Intel)；`-mprefer-vector-width=256` (AOCC)                                        |
| **LTO / ThinLTO** | 跨模块内联、去冗余             | `-flto=thin` (Clang 18)                                                       |
| **PGO**           |  基于 Profiling 调优    | `-fprofile-generate/use` (GCC)；`-prof-gen/use` (Intel)|
| ... | ... | ... |

## 说明与致谢

本赛题为南方科技大学 2025 年超算比赛基础赛道编译优化赛题。本赛题所有资源遵循 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 协议，允许非商业性使用与修改。同时，[GitHub 仓库]() 已开放讨论区，欢迎大家在此讨论与交流。如有任何问题，请提出 issue 或联系 [12211634@mail.sustech.edu.cn](mailto:12211634@mail.sustech.edu.cn). 出题人：[Charley-xiao](https://github.com/Charley-xiao).


## 终章 · 静默律

舰桥化作白沙，方格海在远方翻涌。等待下一次光临之前，澄与洛肩并肩坐在断桅上，看恒星从甲板另一侧升起，像编译器吐出的第一束晨曦。  

> **澄**  
> “也许我们救不了宇宙。”  
>
> **洛**  
> “那就先救一行代码。”  

黑暗与光在他们掌心交握，  
崩落的界域，被悄然缝起一道细碎银线。


<div align="center">
<img src="./assets/marina.png">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=13&height=80&section=footer&fontSize=80">
</div>
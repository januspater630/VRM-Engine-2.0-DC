# VRM Engine 2.0-DC（Verifiable Relational Memory Engine）

> **⚠️ 闭源声明 / NOT OPEN SOURCE**
> 本仓库为**闭源二进制验证包**（closed-source verification build）。它**不包含任何源码**（无 .c/.cpp/.h/.py/.cs 等）、无构建脚本、无内部数据；**未授予任何开源许可或复制/再分发权利**。下载即视为同意：仅用于**独立技术验证（independent technical evaluation）**目的。分发与商业使用需另行书面授权。官方封板哈希见下，任何重打包版本均不作数。

## 这是什么

VRM Engine 2.0-DC 是一个**可验证的关系记忆引擎（Verifiable Relational Memory）**研究实现。它处理的问题不是"检索更多上下文"，而是：把长期 AI memory 变成"用关系种子定位、验证、重建所需上下文"，并保持一条可追溯回底层证据的路径。

它不是又一种向量数据库 / RAG 层。所有实验数字**严格依赖测试条件**，以本仓库 Release 封板包可复现为准，不发布无条件的通用压缩率声明。

## 已完成的技术闭环（F3fix，2026-09-04）

1. **独立验证包**：`ACM_Standalone_公开测试版_v2.0_20260904_F3fix.zip`（1,113,858 B，SHA256=`faf175961f99e650d516fecb5e98aa1911e454bd9194e4d7c538afc8905a17fb`）——黑盒可独立运行，无需我方内部设施。
2. **测试规范与冻结查询集**：identify / state_c / error 三集 + benchmark 规范随包附送；冻结集哈希校验运行时生效。
3. **独立红队闭环**：FL/FK 分离攻击 → C1=0 且 C2=0 → 修复 → 再攻击 → **哈希封板**（字节不变原则：改名可，重打包须重新走安全复核）。
4. **诚实性修复（R4-Q）**：主语未解析时**不猜测**（返回 STATE_C RELATION_UNSUPPORTED），不再以"首出边"兜底作答。
5. **F3fix 全量回归**：CLI 4/4、R4-Q 回归 3/3、HTTP、Benchmark 900/500/3；reason 六码封闭、实现语义词 violations=0、zip 13/13 自检通过。
6. 封板证据链：独立复审签字、上架安全守门 G1~G7 全绿、发布前最终安全复核 PASS。

## 对技术验证方（工程师 / 研究团队）

- **包内**：README / benchmark(6) / bin(2) / checksum / data / docs(3) = 14 文件，零源码、零构建脚本、零内部数据。
- **如何验证**：按 `docs/verification.md` 与 `benchmark/benchmark_spec.md` 黑盒执行；`checksum/SHA256SUMS.txt` 自检 13/13。
- 我们**不要求投资或商业承诺**；欢迎相关团队独立评估该机制是否超越既有 memory/RAG 架构。
- 更深层材料（完整测试数据 / 更大语料 / 架构细节）在独立评估建立后、按 NDA 受控提供。

## 联系与纪律

- 技术验证联络：通过本仓库 Issue 提出，或经仓库维护者指定渠道。
- 官方包只读、字节不变；**闭源，非开源**；对外表述不得声称开源。
- 任何"表示比 / 压缩率"类数字，一律以封板包 + 测试条件可复现为准。

— VRM Engine 2.0-DC（Janus Pater 实验室）

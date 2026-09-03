# VRM Engine 2.0-DC（Verifiable Relational Memory Engine）

**闭源交付 · 非公开货架 · 链接制。Release 资产即官方独立验证包（Independent Verification Package）。**

## 这是什么

VRM Engine 2.0-DC 是一个**可验证的关系记忆引擎**的研究实现。它处理的问题不是"检索更多上下文"，而是：把长期 AI memory 变成"用关系种子定位、验证、重建所需上下文"，并保持一条可追溯回底层证据的路径。

它不是又一种向量数据库 / RAG 层，也不作为通用压缩率声明发布。所有实验数字**严格依赖测试条件**，以本仓库 Release 封板包可复现为准。

## 已完成的技术闭环（截至 2026-09-04，F3fix）

1. **独立验证包**：`ACM_Standalone_公开测试版_v2.0_20260904_F3fix.zip`（1,113,858 B，SHA256=`faf17596…a17fb`），黑盒可独立运行，无需我方内部设施。
2. **测试规范与冻结查询集**：identify / state_c / error 三集 + benchmark 规范随包附送，冻结集哈希校验运行时生效。
3. **独立红队闭环**：FL/FK 分离攻击 → C1=0 且 C2=0 → 修复（strip / 词表处置 / 假证逻辑根治）→ 再攻击 → **哈希封板**（字节不变原则：改名可、重打包须重新走复核）。
4. **诚实性修复（R4-Q）**：主语未解析时**不猜测**（返回 STATE_C RELATION_UNSUPPORTED），不再用"首出边"兜底作答。
5. **F3fix 全量回归**：CLI 4/4、R4-Q 回归 3/3、HTTP、Benchmark 900/500/3；reason 六码封闭、实现语义词 violations=0、zip 13/13 自检通过。
6. 封板证据链：独立复审签字、上架安全守门 G1~G7 全绿、发布前最终安全复核 PASS（详见协作记录）。

## 对技术验证方的说明

- **包内**：README / benchmark(6) / bin(2) / checksum / data / docs(3) = 14 文件，零源码、零构建脚本、零内部数据。
- **如何验证**：按 `docs/verification.md` 与 `benchmark/benchmark_spec.md` 黑盒执行即可；`checksum/SHA256SUMS.txt` 自检 13/13。
- **我们不要求投资或商业承诺**：欢迎合格工程/研究团队独立评估机制本身，判断它是否超越既有 memory/RAG 架构。
- 更深层材料（完整测试数据 / 更大语料 / 架构细节）在独立评估建立后、按 NDA 受控提供。

## 纪律

- 官方包只读、字节不变；本仓库私有，仅对受邀/持链接者可见；对外不声称开源。
- 任何"表示比 / 压缩率"类数字，一律以封板包 + 测试条件可复现为准，不作无条件的通用声明。

— VRM Engine 2.0-DC（Janus Pater 实验室）

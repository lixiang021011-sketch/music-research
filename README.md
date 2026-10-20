# 音乐 AI 研究：从转录误差到表示的可验证性

一段关于「怎么判断音乐 AI 到底对不对」的独立研究。

## 研究问题

音乐 AI 的瓶颈不只在于生成质量和识别精度，还在于一个更基本的问题：**当我们没有唯一可信的音乐表示真值时，怎么解释和验证模型学到的表示？**

核心结论写在 [paper/test_paper.md](paper/test_paper.md)：对 34 首自动转录歌曲的探索性普查，27 项统计检验、Benjamini–Hochberg 校正。结果只报告在这批材料里反复出现的现象，并明确写出局限——不把模型的任务表现等同于结构理解。

## 三个项目

- **Listening AI**：实时节拍、和弦分析与人工聆听标注（Android + ONNX）。在工程里发现 BPM 估计、首拍相位、小节边界、事件时间坐标之间存在误差传递。代码在 [listening-ai](https://github.com/lixiang021011-sketch/listening-ai)。
- **Vibe Transcribing**：基于 REAPER、Lua/ReaScript 和 AI Agent 的转录工作流，处理分轨、音高估计、起音检测、DAW 时间坐标转换。
- **Workbench**：把音乐分析从「不可检查的模型输出」变成「可溯源、统一时间坐标、多尺度、可独立评估」的研究工作流。离散事件张量、GRU/Transformer 遮盖重建、跨维度预测。

## 仓库内容

- `paper/` —— 研究论文
- `research/` —— melody / harmony / groove 三份 grammar 报告（md + json）和研究词典
- `audio/` —— 生成样本：`formula_targeted_v04_preview.mp3`、`formula_targeted_v05_preview.mp3`（公式基线）、`song020_v3_final.mp3`（仿写样例）

## 相关仓库

- [listening-ai](https://github.com/lixiang021011-sketch/listening-ai) —— 移动端和弦 / 节拍工具
- [mgmcs-validator](https://github.com/lixiang021011-sketch/mgmcs-validator) —— 多候选节拍网格准入校验（242 份标定文档）
- [Music_encyclopedia](https://github.com/lixiang021011-sketch/Music_encyclopedia) —— 可检索的编配短语手册

## 限制

数据规模有限，自动转录缺乏充分可靠的人工真值。本仓库只包含聚合统计、结论与生成样本，不包含可还原歌曲的逐音事件。

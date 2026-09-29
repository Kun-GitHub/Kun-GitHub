# Hi there 👋 我是 Kong

**架构师 / 技术负责人** · Go 后端 · 云原生 · AI Agent

在智能硬件公司带一支软件研发团队，日常做架构设计、技术选型、核心功能开发，
以及把需求拆成任务、盯进度和验收。周末把这些年攒下来的后端经验做成开源项目。

我不太相信"选型要靠直觉"，更喜欢先跑通一遍、量出真实占用和吞吐，再决定用不用。

## 🚀 开源项目

| 项目 | 一句话定位 | 语言 | Stars |
|---|---|---|---|
| **[RuoYi-Go](https://github.com/Kun-GitHub/RuoYi-Go)** | 用 DDD 六边形架构重写的 RuoYi 后端（Iris + Gorm），前端配 RuoYi-Vue3 | Go | ![stars](https://img.shields.io/github/stars/Kun-GitHub/RuoYi-Go?style=flat) |
| **[SaaS-Zero](https://github.com/saas-zero/saas-zero)** | 多租户 Go 微服务底座：go-zero + ent + Casbin，开箱带网关 / 认证 / 基础数据 | Go | ![stars](https://img.shields.io/github/stars/saas-zero/saas-zero?style=flat) |
| **[mini-ruoyi](https://github.com/Kun-GitHub/mini-ruoyi)** | 1 核 1G 跑得动的低占用后端，出海项目的服务器开销不再是大头 | Go | ![stars](https://img.shields.io/github/stars/Kun-GitHub/mini-ruoyi?style=flat) |

**三套 Go 后端怎么选**（按你手上的机器和项目体量）：

- 想学 **DDD 分层 / 六边形架构**怎么落到 Go 里 → **RuoYi-Go**
- 要做**多租户的大项目**，需要网关、认证、基础数据一次到位 → **SaaS-Zero**
- 只有 **1 核 1G 的小机器**（个人站、出海小型服务） → **mini-ruoyi**

三份 README 里放了同一张对照表，从任一个仓库进去都能对上。

## 🎙️ 端侧 AI / 语音（在研）

在做一套**端侧语音唤醒**的完整研发流程 —— 从采数据一路做到芯片上跑起来：

```text
麦克风 → AEC / NS / AGC / VAD → MFCC 或 Fbank → DS-CNN / DS-TCN（跑在 NPU 上）
       → 唤醒 → 云端 ASR → LLM / TTS
```

- **数据**：真实录音 + Edge TTS 合成 + 在线增强；真实数据**按说话人分组**划分 train / val / test（防说话人泄漏），TTS 只进训练集；数据分版本、有全局索引，边缘静音和削波都卡在导入阶段

- **模型**：PyTorch 训 DS-CNN（MFCC）与 DS-TCN（Fbank + QAT），指标用 **FAR / FRR / EER**，不是只看准确率

- **部署**：PyTorch → ONNX → RKNN，目标芯片是 Rockchip **RV1103B / RV1106**；板端 C++ 侧自己做前端特征提取。目前还在板端验收阶段，没到量产

- **配套**：Flask 做的 Web 面板管数据 / 训练 / 评估 / 导出，多唤醒词生产流程单独出文档

另外手上有一套**语音识别 / 说话人分离**工具：本地跑 FunASR（paraformer-zh + fsmn-vad + ct-punc + cam++），云端走异步转写；输出 txt / json / srt，长音频自动分段、断点续跑、跨段说话人合并。实时对话与语音通话也在试。

## 💻 技术栈

**语言** · Go · Java · Kotlin · TypeScript / JavaScript · Python · Swift

**后端** · Iris · Gorm · go-zero · ent · Casbin · gRPC · RESTful API · PostgreSQL · Redis

**前端** · Vue 3 · Element Plus · React · Ant Design Pro · Umi · Svelte

**基础设施** · Linux · Docker · Kubernetes / K3s · Nginx · Jenkins · Git

**移动端** · Android（Jetpack Compose） · iOS

**AI / 端侧** · PyTorch · ONNX · RKNN · Rockchip NPU · FunASR · 语音唤醒 · 说话人分离

## 🧭 我在关注的方向

智能硬件 · IoT · 音视频（WebRTC / P2P / LiveKit） · 全球云平台 · 端侧 AI 推理 · AI Agent（LLM / RAG / MCP）

长期的技术积累基本都围着这几条线走，开源的几个后端底座也是从里面的真实需求里长出来的。

## ✍️ 我怎么做事

- **架构优先，但要用数据说话** —— 先量真实占用和性能，再定技术方案
- **控制技术债** —— 能简单就不复杂，宁少不滥
- **对齐竞品** —— 主动找功能缺口，进 Backlog，而不是等别人提
- **进度可见** —— 任务拆分、每日更新、明确验收标准

## 📫 联系

- GitHub：[@Kun-GitHub](https://github.com/Kun-GitHub)
- Email：hot_kun@hotmail.com

---

<details>
<summary><b>English</b></summary>

### Hi there 👋 I'm Kong

**Architect & Tech Lead** · Go backend · Cloud Native · AI Agents

I lead a software team at a smart-hardware company — architecture design, tech
selection, core development, and shipping. On the side I turn years of backend experience
into open-source projects.

I don't like choosing a stack by gut feeling. I'd rather build it once, measure the real
footprint and throughput, and then decide.

**Open Source**

| Project | What it is | Lang |
|---|---|---|
| [RuoYi-Go](https://github.com/Kun-GitHub/RuoYi-Go) | RuoYi backend rewritten with DDD / hexagonal architecture (Iris + Gorm) | Go |
| [SaaS-Zero](https://github.com/saas-zero/saas-zero) | Multi-tenant Go microservice base: go-zero + ent + Casbin, gateway/auth/basedata out of the box | Go |
| [mini-ruoyi](https://github.com/Kun-GitHub/mini-ruoyi) | A backend that actually runs on a 1-core / 1GB box — low footprint for overseas deploys | Go |

Which Go backend to pick: **RuoYi-Go** to learn DDD layering, **SaaS-Zero** for multi-tenant
projects that need a gateway and auth, **mini-ruoyi** when you only have a 1-core 1GB machine.

**On-device AI / Speech (work in progress)** — an end-to-end keyword-spotting pipeline: real
recordings + Edge TTS + augmentation → speaker-isolated train/val/test splits → DS-CNN (MFCC)
and DS-TCN (Fbank + QAT) trained in PyTorch, scored on FAR / FRR / EER → ONNX → RKNN → Rockchip
RV1103B / RV1106 NPU (board-level validation still in progress). Plus an ASR / speaker-diarization toolset (local FunASR, cloud async
transcription, txt / json / srt output).

**Tech** — Go · Java · Kotlin · TypeScript · Python · Swift · Iris · Gorm · go-zero · ent ·
Casbin · gRPC · PostgreSQL · Redis · Vue 3 · React · Svelte · Docker · Kubernetes / K3s · Nginx ·
PyTorch · ONNX · RKNN · Rockchip NPU

**Interests** — IoT · Real-time communication (WebRTC / P2P / LiveKit) · Cloud Native ·
On-device AI inference · AI Agents (LLM / RAG / MCP) · Android reverse engineering

**How I work** — architecture first, but let the measurements decide · keep tech debt low ·
compare against competitors and feed the gaps into a backlog · keep progress visible

📫 [@Kun-GitHub](https://github.com/Kun-GitHub) · hot_kun@hotmail.com

</details>

---

> *先把真实的东西跑起来，再谈架构。*

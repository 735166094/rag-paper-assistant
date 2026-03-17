基于 RAGFlow 定制优化的计算机视觉学术论文智能问答系统
<div align="center">
<img alt="Python" src="https://img.shields.io/badge/Python-3.10+-blue.svg" />
<img alt="Docker" src="https://img.shields.io/badge/Docker-24.0+-blue.svg" />
<img alt="RAGFlow" src="https://img.shields.io/badge/RAGFlow-0.18.0-green.svg" />
<img alt="License" src="https://img.shields.io/badge/License-Apache--2.0-lightgrey.svg" />
</div>

项目仓库
本项目开源地址：https://github.com/735166094/rag-paper-assistant

项目简介
RAG 论文研读助手是专为计算机视觉研究者打造的本地部署 RAG 问答工具，基于 infiniflow/ragflow 开源框架深度定制开发。
本项目参考并遵循 RAGFlow 官方中文 README 文档 的部署规范与架构设计，针对学术论文场景优化了文档解析、文本切片、混合检索全流程，实现公式 / 表格精准识别、低幻觉问答、原文溯源。

核心功能
学术 PDF 深度解析：公式、表格、图表结构化提取
论文专属切片策略：算法细切 + 实验完整保留
混合检索架构：向量检索 + 关键词检索 + BGE 重排序
答案溯源可查：支持引用原文片段，降低生成幻觉
一键容器化部署：支持 CPU/GPU 双版本，本地隐私安全

环境要求
CPU ≥ 4 核 | 内存 ≥ 16GB | 磁盘 ≥ 50GB
Docker ≥ 24.0.0 & Docker Compose ≥ v2.26.1
可选 GPU：RTX 3090 及以上
快速开始

bash
运行
# 1. 克隆项目
git clone https://github.com/735166094/rag-paper-assistant.git
cd rag-paper-assistant

# 2. 系统配置
sudo sysctl -w vm.max_map_count=262144

# 3. 启动服务
cd docker

# CPU版本
docker compose -f docker-compose.yml up -d

# GPU版本
# docker compose -f docker-compose-gpu.yml up -d

访问地址：http://localhost
项目结构
plaintext
rag-paper-assistant/
├── api/            # 后端API服务
├── rag/            # 核心RAG引擎
├── deepdoc/        # 文档深度解析模块
├── docker/         # Docker部署配置
├── web/            # 前端界面
└── docs/           # 项目文档

配置说明
服务端口 / 数据库：docker/.env
LLM 模型配置：docker/service_conf.yaml
部署架构参考：RAGFlow 官方中文 README

致谢
核心基础框架：infiniflow/ragflow
部署与开发规范参考：RAGFlow 官方中文 README 文档
感谢实验室同学的测试与反馈
⭐ 如果本项目对你有帮助，欢迎 Star 支持！

文件说明
已明确标注引用来源：全文清晰指出参考了 https://github.com/infiniflow/ragflow/blob/main/README_zh.md
已添加你的仓库地址：顶部展示项目开源仓库，快速开始中也包含克隆链接
格式规范：简洁通用、可直接下载使用的 README.md 文件
合规性：遵循 RAGFlow 开源协议，明确标注依赖与参考文档







项目结构部分可以再详细展开介绍一下吗？
如何在项目中进行配置？
有哪些优化亮点可以进一步展开说明？

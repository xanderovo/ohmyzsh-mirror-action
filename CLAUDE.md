# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个 GitHub Action 仓库，用于将 ohmyzsh 项目从 GitHub 镜像同步到 Gitee。

## 工作流配置

工作流文件位于 `.github/workflows/main.yml`：

- **触发条件**：
  - 手动触发（workflow_dispatch）
  - 定时触发：每天 22:10 UTC（北京时间 6:10）
- **使用的 Action**：
  - `Yikun/hub-mirror-action@v1.5` -  GitHub 到 Gitee 的镜像同步
  - `zzzze/webhook-trigger@master` - 同步完成后发送通知

## 需要的 Secrets

配置仓库时需要设置以下 Secrets：

- `GITEE_PRIVATE_KEY` - Gitee 私钥
- `GITEE_TOKEN` - Gitee API Token
- `WEBHOOK_URL` - 通知 Webhook 地址
- `TOKEN` - Webhook 认证 Token

## 配置说明

当前镜像配置：
- 源：github/ohmyzsh
- 目标：gitee/congxy
- 同步列表：ohmyzsh

修改镜像配置需调整 `main.yml` 中的 `src`、`dst` 和 `static_list` 参数。

---
name: ccommit
description: 按照 Conventional Commits 规范生成并执行 git commit。当用户需要进行代码提交、编写提交信息或查看暂存区改动时使用此 Skill。
---

# Conventional Commits 提交助手

此 Skill 帮助你按照 Conventional Commits 规范生成清晰的 git 提交信息。

## 使用说明

1. **分析改动**：首先使用 `git diff --cached` 查看暂存区的代码改动
2. **生成提交信息**：根据改动内容，按照 Conventional Commits 规范生成提交信息
3. **执行提交**：使用生成的提交信息执行 git commit

## Conventional Commits 规范

提交信息格式：`<type>(<scope>): <description>`

### 类型（type）

必须使用以下类型之一：

- `feat`: 新功能
- `fix`: 修复 Bug
- `docs`: 文档变更
- `style`: 代码格式调整（不影响代码逻辑）
- `refactor`: 代码重构
- `perf`: 性能优化
- `test`: 测试相关
- `build`: 构建系统或依赖项变更
- `ci`: CI/CD 配置变更
- `chore`: 其他不修改 src 或测试文件的变更
- `revert`: 回退提交

### 格式要求

- **type** 必须使用上述类型之一
- **scope**（可选）：描述改动的模块或组件范围
- **description**：简短描述（使用中文）

## 提交信息示例

```bash
# 新功能
feat(auth): 添加用户登录功能

# 修复 Bug
fix(api): 修复用户信息接口返回数据错误

# 文档更新
docs(readme): 更新安装说明文档

# 代码重构
refactor(user): 重构用户模块代码结构

# 性能优化
perf(query): 优化数据库查询性能

# 测试相关
test(login): 添加登录功能单元测试
```

## 执行步骤

当用户请求提交代码时：

1. 运行 `git diff --cached` 查看暂存区的改动
2. 分析改动的内容和影响范围
3. 确定合适的 type 和 scope
4. 编写简洁的 description
5. 生成完整的提交信息
6. 使用 `git commit -m` 执行提交

## 工具权限

此 Skill 需要使用以下工具：
- `Bash`: 执行 git 命令
- `Read`: 读取相关文件（如果需要）

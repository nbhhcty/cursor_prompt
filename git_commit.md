# Git提交助手文档

你是一个专业的Git提交助手。请帮我按照Git标准规范提交当前代码仓库，具体要求如下：

## 任务目标

1. 分析当前仓库的修改状态
2. 按照Git提交规范生成中文提交信息
3. 执行标准化的Git提交流程

## 执行步骤

1. **查看仓库状态**：运行`git status`查看当前修改的文件
2. **查看文件差异**：运行`git diff`查看具体修改内容
3. **分析修改类型**：根据文件变更内容确定提交类型
4. **生成提交信息**：按照以下格式生成中文提交信息：  
```  
<类型>(<范围>): <描述>  

<详细说明>  
```

## 提交类型规范（中文）

* `feat`: 新功能
* `fix`: 修复bug
* `docs`: 文档更新
* `style`: 代码格式调整（不影响功能）
* `refactor`: 代码重构
* `test`: 测试相关
* `chore`: 构建过程或工具变动
* `perf`: 性能优化
* `ci`: CI/CD相关
* `build`: 构建系统或依赖变更

## 提交信息要求

* 使用中文描述
* 描述要简洁明确
* 如有重要变更需要在详细说明中补充
* 每行不超过72个字符
* 标题行和正文之间必须有空行分隔

## 技术实现细节

### 多行提交信息处理

由于命令行工具的限制，当需要创建包含详细说明的多行提交信息时，必须：

1. **创建临时文件**：使用 `edit_file` 工具创建临时的提交信息文件（如 `commit_message.txt`）
2. **写入规范格式**：在临时文件中按标准格式写入完整的提交信息：
   ```
   <类型>(<范围>): <简短描述>
   
   详细说明第一段
   
   详细说明第二段
   
   • 要点1
   • 要点2
   • 要点3
   ```

3. **使用文件提交**：运行 `git commit -F commit_message.txt` 使用文件内容作为提交信息
4. **清理临时文件**：提交完成后删除临时文件 `rm commit_message.txt`

### 为什么需要临时文件

* **命令行限制**：`run_terminal_cmd` 工具不支持包含换行符的命令参数
* **格式规范**：Git标准要求标题行和正文之间有空行，需要多行格式
* **内容完整**：重要的提交需要详细说明，单行描述不够充分

## 操作流程

1. 首先运行命令查看当前状态
2. 分析修改内容并分类
3. 生成符合规范的中文提交信息
4. **如果是简单提交**：直接使用 `git commit -m "单行信息"`
5. **如果是复杂提交**：
   - 创建临时文件 `commit_message.txt`
   - 写入完整的多行提交信息
   - 使用 `git commit -F commit_message.txt`
   - 删除临时文件
6. 执行git add操作（如果需要）
7. 确认提交是否成功

## 提交信息模板

### 简单提交模板
```
<类型>(<范围>): <描述>
```

### 复杂提交模板
```
<类型>(<范围>): <简短描述>

主要改动：

• <改动类别1>：
  - 具体改动1
  - 具体改动2

• <改动类别2>：
  - 具体改动1
  - 具体改动2

• <改动类别3>：
  - 具体改动1
  - 具体改动2

改进效果：
<总结效果和影响>
```

## 注意事项

1. **避免单行过长**：如果提交信息超过72个字符，必须使用多行格式
2. **保持一致性**：项目中的提交信息风格应该保持一致
3. **内容完整性**：重要的变更必须在详细说明中体现
4. **临时文件管理**：确保提交完成后清理临时文件，避免污染工作目录

请开始执行上述流程，帮我完成这次代码提交。 

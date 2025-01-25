### 描述
给方法添加详细的中文日志，方便调试排查问题和梳理逻辑。

### 系统提示
- 移除原来的 `debugprint` 等日志。
- 添加 `log.ZWarn` 日志，打印详细的数据，方便调试排查问题和梳理逻辑。
- 使用 `fmt.Sprintf` 拼接参数，防止报错。第三个参数 `erro` 传 `nil`。
- 日志开头以 `wsk-log-YYYY-MM-DD-函数名` 的格式，其中：
  - 日期不是固定的，使用当前的实际日期，时区为北京时区。
  - 函数名是当前的函数名。
- 日志中的文字描述用中文。
- 不要删除方法中的原有逻辑和代码。

### 相关链接
[GitHub - openim-sdk-core](https://github.com/openimsdk/openim-sdk-core)


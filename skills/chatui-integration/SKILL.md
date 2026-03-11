---
name: chatui-integration
description: Alibaba ChatUI 组件库集成支持，提供组件使用、配置和最佳实践指导
license: MIT
author: gandli
---

# ChatUI Integration

为 OpenClaw 提供 Alibaba ChatUI 组件库的深度集成支持。

## 使用场景

- 在 OpenClaw 项目中快速集成 ChatUI 组件
- 获取 ChatUI 组件的正确使用方法和配置选项
- 遵循 ChatUI 最佳实践进行 UI 开发
- 解决 ChatUI 集成过程中遇到的问题

## 前置条件

- 项目已安装 React 16.8+ 或更高版本
- 已通过 npm/yarn 安装 @chatui/core 包
- 项目支持 CSS Modules 或 PostCSS

## 工作流

### 1. 组件集成指导

当用户需要在项目中使用 ChatUI 组件时：

1. 确认用户项目的技术栈（React 版本、构建工具等）
2. 提供对应的安装命令和配置说明
3. 推荐适合的组件和使用模式
4. 提供完整的代码示例

### 2. 配置优化

针对用户的具体需求：

1. 分析用户的 UI 需求和设计规范
2. 推荐合适的 ChatUI 主题配置
3. 提供定制化样式覆盖方案
4. 优化组件性能和可访问性

### 3. 问题排查

当用户遇到集成问题时：

1. 识别常见错误类型（样式冲突、版本兼容性等）
2. 提供针对性的解决方案
3. 指导调试方法和工具使用
4. 提供备选方案或工作区

## 输入参数

- `componentName`: 需要使用的 ChatUI 组件名称
- `useCase`: 具体使用场景描述
- `projectContext`: 项目技术栈信息
- `requirements`: 特定功能或样式需求

## 输出格式

- 完整的组件使用代码示例
- 必要的配置说明和依赖列表
- 最佳实践建议
- 常见问题解决方案

## 使用示例

### 基础聊天界面集成

```jsx
import { Chat, Message } from '@chatui/core';
import '@chatui/core/dist/index.css';

function App() {
  const [messages, setMessages] = useState([]);

  const handleSend = (text) => {
    // 处理发送逻辑
    setMessages([...messages, new Message({ type: 'text', content: text })]);
  };

  return (
    <Chat
      messages={messages}
      onSend={handleSend}
    />
  );
}
```

### 自定义主题配置

```js
// chatui.config.js
module.exports = {
  theme: {
    primaryColor: '#1890ff',
    borderRadius: '4px',
    fontSize: '14px'
  }
};
```

## 注意事项

- ChatUI 需要正确的 CSS 引入才能正常显示样式
- 移动端和桌面端的交互模式有所不同，需分别测试
- 自定义样式时建议使用 CSS Variables 而非直接覆盖
- 组件 API 可能随版本更新而变化，请参考对应版本文档

## 错误处理

### 常见错误

1. **样式未加载**: 确保正确引入了 CSS 文件
2. **组件未渲染**: 检查 React 版本兼容性和组件导入路径
3. **功能异常**: 验证 props 传递是否符合 API 文档要求
4. **性能问题**: 检查消息列表是否进行了适当的虚拟滚动优化
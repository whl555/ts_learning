# EventEmitter TDD 学习项目

## 🎯 项目简介

这是一个基于测试驱动开发（TDD）方法的 EventEmitter 学习项目。通过四个递进的阶段，你将从零开始实现一个完整的事件发射器系统。

## 📁 项目结构

```
tdd/
├── test-framework.ts           # 自定义测试框架
├── 01-basic-event-emitter.test.ts      # 第一阶段：基础功能测试
├── 02-improved-event-emitter.test.ts   # 第二阶段：改进功能测试
├── 03-typed-event-emitter.test.ts      # 第三阶段：类型安全测试
├── 04-async-event-emitter.test.ts      # 第四阶段：异步功能测试
├── run-all-tests.ts            # 运行所有测试的入口
├── TDD学习指南.md              # 详细学习指南
├── README.md                   # 项目说明文档
└── solutions/                  # 参考答案目录
    ├── 01-basic-solution.ts
    ├── 02-improved-solution.ts
    ├── 03-typed-solution.ts
    └── 04-async-solution.ts
```

## 🚀 快速开始

### 1. 运行单个阶段测试

```bash
# 第一阶段：基础EventEmitter
npx ts-node --files src/event-emitter/tdd/01-basic-event-emitter.test.ts

# 第二阶段：改进版EventEmitter
npx ts-node --files src/event-emitter/tdd/02-improved-event-emitter.test.ts

# 第三阶段：类型安全EventEmitter
npx ts-node --files src/event-emitter/tdd/03-typed-event-emitter.test.ts

# 第四阶段：异步EventEmitter
npx ts-node --files src/event-emitter/tdd/04-async-event-emitter.test.ts
```

### 2. 运行所有测试

```bash
npx ts-node --files src/event-emitter/tdd/run-all-tests.ts
```

### 3. 查看参考答案

```bash
# 运行参考实现
npx ts-node --files src/event-emitter/tdd/solutions/01-basic-solution.ts
npx ts-node --files src/event-emitter/tdd/solutions/02-improved-solution.ts
npx ts-node --files src/event-emitter/tdd/solutions/03-typed-solution.ts
npx ts-node --files src/event-emitter/tdd/solutions/04-async-solution.ts
```

## 📚 学习阶段

### 🟡 第一阶段：基础 EventEmitter

**目标**: 实现最基本的事件系统

- ✅ 添加事件监听器 (`on`)
- ✅ 触发事件 (`emit`)
- ✅ 获取监听器数量 (`listenerCount`)
- ✅ 处理多个监听器和参数传递

### 🟠 第二阶段：改进版 EventEmitter

**目标**: 添加订阅管理和性能优化

- ✅ 订阅/取消订阅模式 (`subscribe`/`unsubscribe`)
- ✅ 使用 Map 和 Set 优化性能
- ✅ 错误处理和返回值收集
- ✅ 批量操作和监听器管理

### 🔵 第三阶段：类型安全 EventEmitter

**目标**: 实现编译时类型检查

- ✅ 泛型约束和类型安全
- ✅ 链式调用支持
- ✅ 一次性监听器 (`once`)
- ✅ 类型安全的监听器操作

### 🟢 第四阶段：异步 EventEmitter

**目标**: 支持异步监听器

- ✅ 异步监听器支持
- ✅ 并行执行 (`emitAsync`)
- ✅ 串行执行 (`emitAsyncSerial`)
- ✅ 异步错误处理

## 🧪 测试框架特性

### 断言方法

- `Assert.equal(actual, expected)` - 相等断言
- `Assert.true(value)` / `Assert.false(value)` - 布尔断言
- `Assert.deepEqual(actual, expected)` - 深度相等断言
- `Assert.arrayContains(array, item)` - 数组包含断言
- `Assert.greaterThan(a, b)` / `Assert.lessThan(a, b)` - 数值比较断言

### 模拟函数 (Mock)

- `createMock<T>()` - 创建模拟函数
- `mock.toHaveBeenCalled()` - 检查是否被调用
- `mock.toHaveBeenCalledTimes(n)` - 检查调用次数
- `mock.toHaveBeenCalledWith(...args)` - 检查调用参数
- `mock.getCallArgs(index)` - 获取指定调用的参数

## 💡 学习建议

### 1. 按阶段进行

- 从第一阶段开始，逐步完成每个阶段
- 确保当前阶段所有测试通过再进入下一阶段
- 理解每个功能的设计思路和实现方式

### 2. TDD 流程

1. **红（Red）**: 运行测试，看到失败
2. **绿（Green）**: 编写最简代码让测试通过
3. **重构（Refactor）**: 优化代码结构

### 3. 实现策略

- 先实现功能，再考虑性能
- 重视错误处理和边界情况
- 保持代码简洁和可读性

### 4. 调试技巧

- 使用 `console.log` 输出中间状态
- 单独运行失败的测试进行调试
- 仔细阅读测试描述理解需求

## 🔍 常见问题

### Q: 测试失败怎么办？

1. 仔细阅读错误信息和测试描述
2. 检查实现逻辑是否正确
3. 使用调试工具定位问题
4. 参考测试用例理解期望行为

### Q: TypeScript 类型错误如何解决？

1. 理解泛型约束的作用
2. 确保接口定义正确
3. 检查方法签名是否匹配
4. 使用 IDE 的类型提示功能

### Q: 异步测试如何理解？

1. 区分并行和串行执行的差异
2. 理解 Promise.all 和 for 循环的区别
3. 注意异步错误处理的重要性
4. 掌握 async/await 的使用方法

## 🎓 学习成果

完成所有阶段后，你将掌握：

- ✅ 测试驱动开发的基本流程和思维
- ✅ EventEmitter 的设计原理和实现细节
- ✅ TypeScript 泛型和类型系统的高级用法
- ✅ 异步编程和 Promise 的处理技巧
- ✅ 错误处理和边界情况的考虑方法
- ✅ 代码重构和性能优化的实践经验

## 📞 获取帮助

如果在学习过程中遇到问题：

1. 查看 `TDD学习指南.md` 获取详细说明
2. 参考 `solutions/` 目录中的参考答案
3. 理解测试用例的期望行为
4. 逐步调试和验证你的实现

开始你的 TDD 学习之旅吧！🚀

---

**注意**: 建议先自己尝试实现，遇到困难时再查看参考答案。这样能够最大化学习效果。

# ToDoList-Notice-Flutter

一个功能完整的Flutter待办事项应用，支持智能通知提醒功能。

## 📱 项目简介

这是一个现代化的Flutter待办事项管理应用，采用Material Design设计语言，提供直观的用户界面和强大的功能。应用支持任务分类、优先级管理、智能通知提醒等功能，帮助用户高效管理日常任务。

## ✨ 功能特性

### 📝 任务管理
- **任务创建和编辑**：快速创建任务，支持标题、描述、截止日期等信息
- **智能分类系统**：支持6种预设分类（个人、工作、健康、购物、学习、其他）
- **优先级设置**：三级优先级系统（高、中、低）
- **任务状态管理**：完成、删除、编辑任务状态

### � 智能通知系统
- **精准时间提醒**：支持精确到分钟的提醒设置
- **通知权限管理**：智能请求和管理通知权限
- **后台通知调度**：即使应用关闭也能准时提醒
- **自定义通知样式**：使用应用图标和个性化消息
- **通知错误恢复**：强健的错误处理机制，确保通知稳定性

### � 用户界面
- **现代化设计**：Material Design 3.0设计语言
- **渐变按钮**：美观的添加任务按钮，支持动画效果
- **响应式布局**：适配不同屏幕尺寸
- **主题系统**：统一的颜色主题和样式
- **流畅动画**：丰富的交互动画效果

### 📊 数据管理
- **本地数据库**：使用SQLite进行数据持久化
- **实时数据同步**：基于Provider的状态管理
- **数据安全性**：完善的错误处理和数据验证
- **任务统计**：查看任务完成情况和统计信息

### �️ 分类和筛选
- **分类筛选**：按类别快速筛选任务
- **优先级筛选**：按优先级查看重要任务
- **状态筛选**：查看完成/未完成任务
- **搜索功能**：快速找到特定任务

## 🛠️ 技术栈

### 前端框架
- **Flutter 3.24.5**：跨平台移动应用开发框架
- **Dart**：编程语言

### 状态管理
- **Provider 6.x**：轻量级状态管理解决方案
- **ChangeNotifier**：数据变更通知机制

### 数据存储
- **SQLite**：本地关系型数据库
- **sqflite 2.4.1**：Flutter SQLite插件

### 通知系统
- **flutter_local_notifications 17.2.4**：本地通知插件
- **timezone 0.9.4**：时区处理

### UI组件
- **Material Design**：Google Material设计组件
- **font_awesome_flutter**：Font Awesome图标库
- **Intl**：国际化支持

### 开发工具
- **ProGuard**：Release版本代码混淆
- **Gradle**：Android构建系统

## 📦 项目结构

```
lib/
├── main.dart                 # 应用入口，全局错误处理
├── models/
│   └── todo.dart            # 任务数据模型，包含验证逻辑
├── screens/
│   ├── splash_screen.dart       # 启动画面
│   ├── home_screen.dart         # 主页面，任务列表展示
│   ├── add_edit_todo_screen.dart # 添加/编辑任务页面
│   └── notification_settings_screen.dart # 通知设置页面
├── services/
│   ├── database_service.dart    # 数据库服务，SQLite操作
│   ├── notification_service.dart # 通知服务，包含错误处理
│   ├── notification_helper.dart  # 通知辅助类
│   └── todo_provider.dart       # 任务数据提供者，状态管理
├── utils/
│   └── app_theme.dart          # 应用主题配置
└── widgets/
    ├── todo_card.dart           # 任务卡片组件
    ├── category_filter_chip.dart # 分类筛选组件
    ├── priority_filter_chip.dart # 优先级筛选组件
    ├── stats_card.dart          # 统计卡片组件
    └── notification_permission_dialog.dart # 权限请求对话框

android/
├── app/
│   ├── src/main/
│   │   ├── res/
│   │   │   ├── mipmap-*/ic_launcher.png # 应用图标（各分辨率）
│   │   │   └── drawable/
│   │   │       └── ic_notification.xml   # 通知图标
│   │   └── AndroidManifest.xml          # Android权限配置
│   ├── build.gradle                     # 应用级构建配置
│   └── proguard-rules.pro              # ProGuard混淆规则
└── build.gradle                        # 项目级构建配置
```

## 🚀 快速开始

### 环境要求

- Flutter SDK 3.24.5 或更高版本
- Dart SDK 3.0 或更高版本
- Android Studio 或 VS Code
- Android SDK (用于Android开发)
- JDK 8 或更高版本

### 安装步骤

1. **克隆项目**
   ```bash
   git clone https://github.com/fxlqwq/ToDoList-Notice-Flutter.git
   cd ToDoList-Notice-Flutter
   ```

2. **安装依赖**
   ```bash
   flutter pub get
   ```

3. **检查环境**
   ```bash
   flutter doctor
   ```

4. **运行应用**
   
   **Debug模式**：
   ```bash
   flutter run
   ```
   
   **Release模式**：
   ```bash
   flutter run --release
   ```

### 构建发布版本

**构建APK**：
```bash
flutter build apk --release
```

**构建AAB (推荐用于Google Play)**：
```bash
flutter build appbundle --release
```

## ⚙️ 配置说明

### Android权限配置

应用需要以下权限（已在 `AndroidManifest.xml` 中配置）：

```xml
<!-- 通知权限 -->
<uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
<!-- 精确闹钟权限 -->
<uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM" />
<!-- 唤醒设备权限 -->
<uses-permission android:name="android.permission.WAKE_LOCK" />
<!-- 网络状态权限 -->
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<!-- 振动权限 -->
<uses-permission android:name="android.permission.VIBRATE" />
```

### ProGuard配置

为确保Release版本正常运行，项目已配置ProGuard规则：

```proguard
# 保护Flutter本地通知插件
-keep class com.dexterous.flutterlocalnotifications.** { *; }
-keep class com.dexterous.flutterlocalnotifications.models.** { *; }

# 保护泛型信息
-keepattributes Signature
-keepattributes InnerClasses
-keepattributes EnclosingMethod
```

## 🔧 核心功能实现

### 通知系统设计

1. **时区处理**：使用 `timezone` 包处理不同时区的时间转换
2. **权限管理**：动态请求通知和精确闹钟权限
3. **错误恢复**：多层错误捕获和恢复机制
4. **调度模式**：支持 `exactAllowWhileIdle` 和 `alarmClock` 两种调度模式

### 数据库设计

```sql
CREATE TABLE todos (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  title TEXT NOT NULL,
  description TEXT,
  category TEXT NOT NULL,
  priority TEXT NOT NULL,
  due_date TEXT,
  reminder_date TEXT,
  is_completed INTEGER DEFAULT 0,
  created_at TEXT NOT NULL,
  updated_at TEXT NOT NULL
);
```

### 状态管理架构

- 使用Provider进行状态管理
- ChangeNotifier实现数据变更通知
- 异步操作错误处理
- 数据持久化同步

## 🐛 故障排除

### 通知不工作

1. **检查权限**：确保已授予通知和精确闹钟权限
2. **时区问题**：检查设备时区设置是否正确
3. **电池优化**：将应用加入电池优化白名单
4. **系统版本**：确保Android版本支持精确闹钟功能

### Release版本崩溃

1. **ProGuard规则**：确保已正确配置混淆规则
2. **权限问题**：检查生产环境权限配置
3. **日志分析**：使用 `adb logcat` 查看崩溃日志

### 数据库问题

1. **初始化失败**：检查数据库文件权限
2. **数据丢失**：确保正确处理数据库升级
3. **性能问题**：优化数据库查询语句

## 📱 应用截图

> 注：可以在这里添加应用截图展示

## 🤝 贡献指南

1. Fork 项目
2. 创建功能分支：`git checkout -b feature/amazing-feature`
3. 提交更改：`git commit -m 'Add amazing feature'`
4. 推送分支：`git push origin feature/amazing-feature`
5. 提交 Pull Request

## 📄 开源协议

本项目采用 MIT 协议 - 查看 [LICENSE](LICENSE) 文件了解详情

## 🙏 致谢

- [Flutter团队](https://flutter.dev) - 优秀的跨平台框架
- [Material Design](https://material.io) - 设计指导原则
- [Flutter Community](https://flutter.dev/community) - 丰富的插件生态

## 📞 联系方式

- GitHub: [@fxlqwq](https://github.com/fxlqwq)
- 项目链接: [https://github.com/fxlqwq/ToDoList-Notice-Flutter](https://github.com/fxlqwq/ToDoList-Notice-Flutter)

---

⭐ 如果这个项目对您有帮助，请给它一个星标！

# 环境配置

## 环境要求

- JDK: 11 (推荐使用 OpenJDK 11)
- Gradle: 6.7.1 (项目已包含 Gradle Wrapper，无需单独安装)
- 操作系统: macOS

## 环境配置命令

### 安装 JDK 11

```bash
brew install openjdk@11

# 创建符号链接（可选，需要管理员权限）
sudo ln -sfn /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
```

### 设置 JAVA_HOME 环境变量

```bash
# macOS (Homebrew 安装)
export JAVA_HOME=/opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk/Contents/Home
```

## 构建和运行项目命令

### 构建项目

```bash
# 使用项目的 Gradle Wrapper 构建项目
./gradlew build
```

### 运行项目

```bash
# 基本运行命令
./gradlew run

# 使用协程调试选项运行
./gradlew run -Dkotlinx.coroutines.debug

# 指定 JAVA_HOME 的同时运行
export JAVA_HOME=/opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk/Contents/Home && ./gradlew run
```

## 故障排除

如果遇到 "Unsupported class file major version" 错误，表明您使用的 Java 版本过高。请确保使用 JDK 11 运行项目：

```bash
# 检查当前 Java 版本
java -version

# 确保使用 JDK 11 运行 Gradle 命令
export JAVA_HOME=/opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk/Contents/Home && ./gradlew build
```

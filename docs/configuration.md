# 配置指南

本文档详细介绍了项目的配置选项和自定义方法。

## 配置文件

项目支持多种配置方式：

1. 配置文件 (`config.yaml`)
2. 环境变量
3. 命令行参数

### 配置文件示例

```yaml
# config.yaml
server:
  host: localhost
  port: 8000
  debug: false

database:
  url: sqlite:///app.db
  pool_size: 10

logging:
  level: INFO
  format: "%(asctime)s - %(name)s - %(levelname)s - %(message)s"
```

## 环境变量

您也可以使用环境变量来覆盖配置：

```bash
export SERVER_HOST=0.0.0.0
export SERVER_PORT=8080
export DATABASE_URL=postgresql://user:password@localhost/mydb
```

## 配置优先级

配置的优先级从高到低为：

1. 命令行参数
2. 环境变量
3. 配置文件
4. 默认值

## 测试配置

要测试您的配置是否正确，可以运行：

```bash
python -m pytest tests/test_configuration.py
```

这将验证配置加载和优先级处理是否正常工作。
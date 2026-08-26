# 学习管理档案设计

量潮学习云的学习管理档案（Learning Profile）：记录学员对验收标准的通过状态。

## 核心模型

学习档案只关心两件事：**谁**通过了**什么标准**。

```
Member (成员)
└── Criterion (验收标准) + 状态
```

- **验收标准**由课程档案定义（单一事实源）
- **通过状态**由学习档案记录

## 验收标准来源

课程开发档案（quanttide-profile-of-course-development）的 `index.json`：

```json
{
  "acceptance": {
    "criteria": ["验收标准1", "验收标准2"],
    "method": "self-check | real-world"
  }
}
```

## 学习档案格式

每位成员一个文件，用昵称命名，checkbox 记录通过状态：

```markdown
# {昵称} 学习档案

- [x] 验收标准1
- [ ] 验收标准2
```

## 目录结构

```
data/profile/
└── {org}/
    ├── README.md
    ├── {nickname}.md
    └── ...
```

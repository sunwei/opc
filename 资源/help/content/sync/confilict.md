---
title: 同步问题排查
date: 2026-02-10
tags:
  - 同步
  - 文件冲突
---
## 冲突文件

**症状**: 出现 `filename (conflict YYYY-MM-DD).md` 文件

**原因**: 多台设备同时修改了同一文件（特别是在[[offline-mode|离线模式]]下）

**冲突如何产生**:

```mermaid
sequenceDiagram
    participant A as 设备 A
    participant Server as CouchDB
    participant B as 设备 B
    
    Note over A,B: 初始状态: note.md rev 1-abc
    
    A->>A: 离线编辑 note.md
    B->>B: 离线编辑 note.md
    
    Note over A: note.md rev 2-def (本地)
    Note over B: note.md rev 2-xyz (本地)
    
    A->>Server: 推送 rev 2-def
    Server-->>A: 成功
    
    B->>Server: 推送 rev 2-xyz
    Server-->>B: 冲突！
    
    Note over Server: 保留 rev 2-def<br/>创建冲突副本
```

**解决冲突**:

1. **手动合并**（推荐）
   - 打开原文件和冲突文件
   - 比较内容
   - 手动合并有价值的修改
   - 删除冲突文件

2. **使用合并工具**
   ```bash
   # 使用 diff 工具
   diff note.md "note (conflict 2026-02-10).md"
   
   # 或使用图形化工具（如 Beyond Compare、WinMerge）
   ```

3. **选择一个版本**
   - 决定保留哪个版本
   - 删除另一个

> [!tip] 预防冲突
> 
> - 尽量不要在多设备同时离线编辑同一文件
> - 频繁连接网络，让设备同步
> - 使用不同的文件名称前缀（如 `deviceA-note.md`、`deviceB-note.md`）


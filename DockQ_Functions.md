## Lamarck &nbsp; &nbsp; &nbsp; 2026-05-26
#### 该文档用于记录 server 上跑 DockQ 的各种命令
---

*236 机子的环境*
```bash
conda activate lmk_DockQ  
```

*工作目录*
```bash
/data/lmk/dockq
```

---

> **01 复合物界面质量评估 -- 自动链匹配**
```bash
DockQ /data/lmk/dockq/1A2K_r_l_b.model.pdb /data/lmk/dockq/1A2K_r_l_b.pdb
# DockQ <model> <native>
```

> **02 复合物界面质量评估 -- 仅评价指定界面**
```bash
DockQ /data/lmk/dockq/1A2K_r_l_b.model.pdb /data/lmk/dockq/1A2K_r_l_b.pdb --mapping AC:BC
# --mapping <MODEL_CHAINS>:<NATIVE_CHAINS>
DockQ /data/lmk/dockq/1A2K_r_l_b.model.pdb /data/lmk/dockq/1A2K_r_l_b.pdb --mapping :BC
# --mapping :<NATIVE_CHAINS> 左边留空，自动匹配 model 中的对应界面
```

> **03 复合物界面质量评估 -- 显式指定链对应**
```bash
DockQ /data/lmk/dockq/1A2K_r_l_b.model.pdb /data/lmk/dockq/1A2K_r_l_b.pdb --mapping BAC:ABC
# 显式指定全部链对应（model B,A,C ↔ native A,B,C），评价所有界面
```

> **04 复合物界面质量评估 -- 精简输出**
```bash
DockQ /data/lmk/dockq/1A2K_r_l_b.model.pdb /data/lmk/dockq/1A2K_r_l_b.pdb --short
# --short 精简输出，便于快速查看 / 脚本读取
```

##### [DockQ官方仓库](https://github.com/bjornwallner/DockQ)

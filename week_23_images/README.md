# 第23周：有限差分与实验图

供第23周 PDE 学习笔记直接引用。

- `mesh.png`：Dirichlet / 周期节点与网格间距。
- `heat_stencils.png`：FTCS 与 CN 的节点和系数。
- `wave_stencils.png`：三层中心差分及非零速度启动。
- `dissipation_dispersion.png`：振幅衰减与相位偏移的机制示意，并非新增实验结果。
- `laplace_stencil.png`：二维边界、五点系数。
- `iteration_order.png`：Jacobi 与字典序 Gauss–Seidel。
- `cfl_domains.png`：正、负速度迎风依赖域，特征线与 CFL 超限的几何对比。
- `upwind_stencils.png`：正负速度的上游节点和带符号权重。
- `experiment_A.png`、`experiment_B.png`、`experiment_C.png`：实际计算的误差、成本、收敛与数值解。

网格和模板按本题符号及系数重新绘制，表示方法参考 Langtangen & Linge, *Finite Difference Computing with PDEs* (2017)：https://hplgit.github.io/fdm-book/doc/web/ 。实验图由本周实际计算数据绘制。

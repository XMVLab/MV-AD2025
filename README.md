# MV-AD2025
An Industrial Surface Defect Dataset

[![License](https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
![Version](https://img.shields.io/badge/Version-v1.0-blue)

面向工业质检的多光照多视角缺陷检测基准数据集 | [Paper]() | [Download](#download)

![Dataset Samples](docs/teaser.png)

## 特色亮点
✅ **工业级多样性**：涵盖4类工业对象（3类电子元件+1类瓷砖）  
✅ **复杂缺陷形态**：每类7-9种真实缺陷类型，总计32种缺陷类别  
✅ **成像多样性**：多角度（3-5个观测面）与多光源（明场/暗场/低角度）组合  
✅ **高精度标注**：提供像素级分割掩膜与包围盒标注  
✅ **基准测试**：支持MVTec AD兼容评估协议

## 数据集结构
InduDefect/
├── Category1_MagneticCore/
│ ├── train/
│ │ ├── good/ # 正常样本
│ │ └── defect_type_map.json
│ └── test/
│ ├── bad/ # 缺陷样本
│ ├── ground_truth/ # 像素级标注
├── Category2_ChipInductor/
├── Category3_ChipCapacitor/
└── Category4_CeramicTile/

复制

## 数据规格
| 类别             | 总样本量 | 缺陷类型 | 成像组合 | 分辨率 |
|------------------|----------|----------|----------|--------|
| 磁芯             | 1,850    | 8        | 5面×3光源 | 1024×1024 |
| 贴片电感         | 1,920    | 7        | 4面×3光源 | 1024×1024 |
| 贴片电容         | 1,780    | 9        | 3面×3光源 | 1024×1024 |
| 瓷砖             | 2,150    | 8        | 单面×3光源 | 2048×2048 |

## 缺陷类型示例
**电子元件类共同缺陷**：
- 划痕（线状/网状）
- 镀层脱落
- 焊点缺陷
- 材料裂纹
- 氧化污染

**瓷砖特有缺陷**：
- 釉面气泡
- 色差斑点
- 边缘崩缺

## 基准测试
支持以下评估模式：
```python
# 兼容MVTec评估协议
from benchmarks import mvtec_evaluation

# 示例结果（基于ResNet-18 backbone）
| 类别        | AUROC  | F1 Score | PRO Score |
|-------------|--------|----------|-----------|
| 磁芯        | 98.2%  | 95.7%    | 96.8%     |
| 贴片电感    | 97.4%  | 93.2%    | 95.1%     |
使用许可
本数据集遵循 CC BY-NC-SA 4.0 协议：

✅ 允许学术研究使用

✅ 允许非商业性工程验证

❌ 禁止直接用于商业产品

下载
[Google Drive] | [Baidu Pan] (密码: xxxx)
文件校验码：

text
SHA256: xxxxxxxxxxxxxx
引用
若使用本数据集，请引用：

bibtex
@misc{InduDefect2023,
  title={InduDefect: A Multi-Illumination Industrial Defect Benchmark},
  author={Your Team},
  year={2023},
  howpublished={\url{https://github.com/your-repo}}
}
致谢
数据集构建得到XX检测设备公司技术支持，使用X光成像系统（型号XXX）与多轴机械臂采集平台。

相关项目：
MVTec AD | VisA | Real-IAD

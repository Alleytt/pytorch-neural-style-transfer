# 神经风格迁移 (Neural Style Transfer)

一个基于PyTorch实现的神经风格迁移项目，将艺术风格从一幅图像转移到另一幅图像。

![示例效果](https://github.com/yourusername/neural-style-transfer/raw/main/data/examples/figures/figures_vg_starry_night_w_350_m_vgg19_cw_100000.0_sw_30000.0_tv_1.0_resized.jpg)

## 安装

1. 克隆仓库
   ```bash
   git clone https://github.com/yourusername/neural-style-transfer.git
   cd neural-style-transfer
# 使用Conda
conda env create -f environment.yml
conda activate pytorch-nst

# 或使用pip
pip install -r requirements.txt


#### 4. 使用方法
```markdown
## 使用

1. 将内容图像放入 `data/content-images/` 目录
2. 将风格图像放入 `data/style-images/` 目录
3. 运行风格迁移
   ```bash
   # 基本用法
   python neural_style_transfer.py --content_img_name <内容图像名> --style_img_name <风格图像名>
   
   # 高级用法
   python neural_style_transfer.py --content_img_name figures.jpg --style_img_name vg_starry_night.jpg --height 500 --optimizer lbfgs --model vgg19 --init_method content --content_weight 1e5 --style_weight 3e4 --tv_weight 1e0


#### 5. 命令行参数说明
```markdown
## 命令行参数

| 参数 | 说明 | 默认值 |
|------|------|--------|
| `--content_img_name` | 内容图像文件名 | figures.jpg |
| `--style_img_name` | 风格图像文件名 | vg_starry_night.jpg |
| `--height` | 图像高度（宽度自动调整） | 400 |
| `--content_weight` | 内容损失权重 | 1e5 |
| `--style_weight` | 风格损失权重 | 3e4 |
| `--tv_weight` | 总变差损失权重 | 1e0 |
| `--optimizer` | 优化器（lbfgs/adam） | lbfgs |
| `--model` | 模型（vgg16/vgg19） | vgg19 |
| `--init_method` | 初始化方法（random/content/style） | content |
| `--saving_freq` | 中间结果保存频率（-1表示仅保存最终结果） | -1 |

## 示例效果

### 不同风格的迁移结果
![风格1](https://github.com/yourusername/neural-style-transfer/raw/main/data/examples/figures/figures_ben_giles_o_lbfgs_i_content_h_500_m_vgg19_cw_100000.0_sw_30000.0_tv_1.0_resized.jpg)
![风格2](https://github.com/yourusername/neural-style-transfer/raw/main/data/examples/figures/figures_vg_starry_night_w_350_m_vgg19_cw_100000.0_sw_30000.0_tv_1.0_resized.jpg)

### 内容/风格权重调整
![权重1](https://github.com/yourusername/neural-style-transfer/raw/main/data/examples/style-tradeoff/figures_vg_starry_night_o_lbfgs_i_random_h_352_m_vgg19_cw_100000.0_sw_10.0_tv_1.0_resized.jpg)
![权重2](https://github.com/yourusername/neural-style-transfer/raw/main/data/examples/style-tradeoff/figures_vg_starry_night_o_lbfgs_i_random_h_352_m_vgg19_cw_100000.0_sw_10000.0_tv_1.0_resized.jpg)

## 参考资源

- 原始论文：[Image Style Transfer Using Convolutional Neural Networks](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)
- 灵感来源：[pytorch-neural-style-transfer](https://github.com/gordicaleksa/pytorch-neural-style-transfer)

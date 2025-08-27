# Huggingface爬虫

## 项目简介

本项目是一个基于 Hugging Face 平台的科学智能语料库自动化构建系统，能够根据指定关键词或网址自动爬取数据集与模型的全部信息，并形成标准化文档。主要功能包括：

- **自动化数据爬取**：从 Hugging Face 平台批量获取数据集和模型信息
- **智能信息提取**：提取名称、描述、标签、许可证、大小等详细信息  
- **AI翻译处理**：将英文描述自动翻译为中文
- **智能标注系统**：基于四层标签体系进行科学领域分类
- **标准化输出**：生成规范化的科学智能语料库文档

主要文件包括：

- `完整工作流_dataset.ipynb`：数据集爬取、处理与标注流程
- `完整工作流_model.ipynb`：模型爬取、处理与标注流程
- `规范协议名称.xlsx`：开源协议名称标准化映射表
- `规范数据格式.xlsx`：规范数据格式标准化映射表
- `科学智能语料.xlsx`：最终生成的标准化语料库文件
- `科学智能模型.xlsx`：最终生成的标准化模型库文件
- `备份_中间流程结果`：项目中间结果备份文件夹

## 环境搭建教程

### 1. 安装 Anaconda
建议使用 [Anaconda](https://www.anaconda.com/products/individual) 进行环境管理和依赖安装。请从官网下载并安装适合您操作系统的 Anaconda 发行版。

### 2. 创建并激活 conda 环境
在项目根目录下打开终端，创建并激活新的 conda 环境（以 Python 3.8 为例）：
```bash
conda create -n kps_env python=3.8
conda activate kps_env
```

### 3. 安装依赖库
使用 conda 和 pip 安装所需依赖：
```bash
# 基础数据科学库
conda install jupyter pandas numpy scikit-learn matplotlib openpyxl

# 网络爬虫相关
pip install selenium beautifulsoup4 requests

# AI/ML相关
pip install openai datasets transformers

# 进度条和其他工具库
pip install tqdm lxml
```

### 4. WebDriver 配置
需使用Chrome WebDriver（用于网页爬虫），请确保已安装Chrome浏览器，并下载对应版本的ChromeDriver

下载地址：https://chromedriver.chromium.org/

对于网页爬虫功能，需要额外下载并配置ChromeDriver，并确保在PATH中。

### 5. 配置deepseek API密钥
由于本项目在翻译部分调用了deepseek的API，请前往 [deepseek官网](https://platform.deepseek.com/) 注册账号并获取API密钥。

### 6. 启动 Jupyter Notebook
在项目根目录下运行：
```bash
jupyter notebook
```

### 7. 打开并运行 Notebook
在浏览器中打开 `完整工作流_dataset.ipynb` 和 `完整工作流_model.ipynb`，按顺序运行各代码单元。

## 其他说明
- 请确保所有数据文件（CSV、XLSX）均放置于项目根目录。
- 如遇依赖问题，可根据报错信息补充安装相关库。

---
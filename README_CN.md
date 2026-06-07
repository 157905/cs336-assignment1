# CS336 2025 春季 作业一：基础
[English Version](README.md)
完整的作业说明请参阅 [cs336_assignment1_basics.pdf](./cs336_assignment1_basics.pdf)

如果你发现作业说明或代码中有任何问题，欢迎提交 GitHub issue 或发起 pull request 进行修复。

## 环境准备

### 环境管理
我们使用 `uv` 来管理环境，以保证可复现性、可移植性和易用性。
请在[此处](https://github.com/astral-sh/uv#installation)安装 `uv`（推荐），或运行 `pip install uv` / `brew install uv`。
建议花一点时间阅读 `uv` 的[项目管理文档](https://docs.astral.sh/uv/guides/projects/#managing-dependencies)（你不会后悔的！）。

完成安装后，你可以通过以下命令运行仓库中的任何代码：
```sh
uv run <python_file_path>
```
环境会在必要时自动解析并激活。

### 运行单元测试

```sh
uv run pytest
```

初始状态下，所有测试都会因 `NotImplementedError` 而失败。
要将你的实现接入测试，需要完成 [./tests/adapters.py](./tests/adapters.py) 中的函数。

### 下载数据
下载 TinyStories 数据集以及 OpenWebText 的子集样本。

``` sh
mkdir -p data
cd data

wget https://huggingface.co/datasets/roneneldan/TinyStories/resolve/main/TinyStoriesV2-GPT4-train.txt
wget https://huggingface.co/datasets/roneneldan/TinyStories/resolve/main/TinyStoriesV2-GPT4-valid.txt

wget https://huggingface.co/datasets/stanford-cs336/owt-sample/resolve/main/owt_train.txt.gz
gunzip owt_train.txt.gz
wget https://huggingface.co/datasets/stanford-cs336/owt-sample/resolve/main/owt_valid.txt.gz
gunzip owt_valid.txt.gz

cd ..
```
```
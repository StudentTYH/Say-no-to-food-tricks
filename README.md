# 用于配料表检测的食品安全大模型

食品安全这条路任重而道远，我希望借助大模型的力量，让食品安全检测更简单、更高效。

现阶段目标，通过OCR检测食品配料表，再通过专业大模型进行配料表的解析，最终实现食品配料表的检测。（当然，这就不适合配料表造假的食品了。）


## Dataset
以下展示了部分数据（数据仅供学习）：

[收集到的csv数据](https://huggingface.co/collections/L0ve1ace/psychology-llm-gguf-67cc766eaf0a3f01c6e39aa6)
[用于大模型微调数据](https://huggingface.co/collections/L0ve1ace/psychology-llm-gguf-67cc766eaf0a3f01c6e39aa6)
[数据处理代码](https://huggingface.co/collections/L0ve1ace/psychology-llm-gguf-67cc766eaf0a3f01c6e39aa6)

数据过程说明：
1、通过爬虫获取数据集。
2、通过大模型与自开发的[百度搜索agent](https://huggingface.co/collections/L0ve1ace/psychology-llm-gguf-67cc766eaf0a3f01c6e39aa6)获取网络数据集（通过百度搜索或得某个配料的详细解释）。
3、通过Langchain进行微调数据集构建（csv2json）。


## LLM
通过llamafactory进行大模型微调，最终得到食品配料检测大模型。
目前由于GPU资源缺乏，目前只进行了DeepSeek-R1-1.5B-Distill的微调，后续会继续进行其他大模型的微调。


## OCR
目前使用的是PaddleOCR，通过dify的接口进行调用[codes]()。

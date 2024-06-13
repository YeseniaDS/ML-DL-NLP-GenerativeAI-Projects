## 1. AI Applications

__Translation:__

[openai-translator](https://github.com/openai-translator/openai-translator)

[immersivetranslate](https://immersivetranslate.com/en/)

__Writing:__

[Notion AI](https://www.notion.so/product/ai)

__Coding:__

[Github Copilot](https://github.com/features/copilot)

[GitHub Copilot Chat](https://docs.github.com/en/copilot/github-copilot-chat/copilot-chat-in-ides/using-github-copilot-chat-in-your-ide?tool=vscode)


## 2. Prompt

GPT是一个推理模型，主要是基于``Pre-train``和``Fine-tuning``两个阶段。在Pre-train阶段会使用一个大规模的语料库进行基础训楼，例如使用Wikipedia，新闻文章，小说等进行训练。当训练完成后，输入一句话(称为``Prompt``)给它，它会基于这句话给出一个``概率上``的预测，预测后续应该拼接上什么单词。这个拼接的单词是基于它在预训练阶段学习到的知识来进行``概率选定的``，通过一次次循环的单词预测，最终可以拼接上一段话。

Fine-tuning和Prompt是我们与GPT模型唯二的交互方式（当然除此之外还可以通过调整模型的 temperature 和 top_p 两个配置来控制 GPT 更多样化或更具创造性的输出，不过对于输出质量和对下游任务的处理能力并无明显影响）。__Prompt是GPT应用开发的最核心部分。__

Pre-train完成之后，在Fine-tuning阶段会将GPT模型加载到特定的任务上，并使用该任务的数据集对GPT模型进行训练。如此，模型就可以根据任务的要求进行微调，以便更好地理解Prompt并生成与任务相关的文本。通过微调，GPT可以适应不同的任务，如情感分析，文本分类，问答系统等。不过目前微调因为成本昂贵和最终效果并不稳定吗，对于GPT开发者而言并不是最有的选择，所以目前大部分的GPT应用开发都是基于Prompt来开发应用。

面对复杂任务，想要提高GPT的输出质量还需要两个非常重要的技巧：让GPT推理而不是回答，以及拆分任务进行引导。__关于如何设计和拆分复杂任务是所有GPT应用最需要思考和维护自身AI应用护城河的核心问题，也是目前大模型框架类似LangChain等项目的核心设计点。__

__应用开发tips：__
* 提供少量示例(Few-Shot Prompting): 给模型一两个期望的输入输出样例，让模型了解我们的要求和期望的输出样式。
* Prompt 中要求结构化输出：以 Json 的方式输出，这样可以方便后续代码程序处理。
* 分隔符：使用分隔符像 ``"""`` 将不同的指令、上下文之间进行隔离，防止系统的 Prompt 和用户输入的 Prompt 混淆冲突。

## 3. GPT Embedding
![image](https://github.com/YeseniaDS/ML-DL-NLP-GenerativeAI-Projects/assets/31481788/0018d2ca-a2d2-49e6-8dcf-0a868c03a76c)

整体的开发流程如上图所示：

* 加载文档，获取目标文本信息。例如 LLM 主流框架 LangChain 中 File Loader 和 Web Loader 的两种文本获取方式。
  - 基于文件系统的 File Loader，如加载 PDF 文件、Word 文件等。
  - 基于网络的 Web Loader，如某个网页，AWS S3 等。
* 将目标文本拆分为多个段落，拆分方式主要基于两种。
  - 一种是基于文字数量的拆分法，例如 1000 字为一段，这种方式的优点是简单，缺点是可能会将一个段落拆分成多个段落，导致段落的连贯性变差，从而导致最终回答结果可能缺少上下文而降低回答质量。
  - 另一种是基于标点符号的拆分法，例如以换行为分隔符，这种方式的优点是段落的连贯性好，缺点是每个段落大小不一，可能会导致触发 GPT tokens 的限制。
  - 最后一种是基于 GPT tokens 限制的拆分法，例如以 2000 tokens 为一组，最终查询时搜索出最相关的两个段落，这样加到一起也才 4000 tokens,就不会触发到 4096 tokens 的限制。
*  将拆分的文本块统一存入 向量数据库 中。
* 将用户问题转化为向量，然后通过向量数据库进行检索，得到最相关的文本段落。（需要注意的是，这里的检索并不是传统数据库的模糊匹配或者倒排索引，而是基于语义化的搜索能力，所以检索出的文本才能回答用户问题，详细请看另外一篇博客 [向量数据库](https://guangzhengli.com/blog/zh/vector-database/）
* 将检索出来的相关文本信息，用户问题和系统的 prompt 三个组合成一个针对于 Embeddings 场景的 Prompt，例如 Prompt 中明确写到使用参考文本回答问题，而不是 GPT 自己回答。
* GPT 回答最终得到的 Prompt，得到最终的答案。

更多详情可参考LangChain中关于Retrieval的章节：https://js.langchain.com/v0.1/docs/modules/data_connection/。












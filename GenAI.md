## 1. AI Applications

__Translation:__

[openai-translator](https://github.com/openai-translator/openai-translator)

[immersivetranslate](https://immersivetranslate.com/en/)

__Writing:__

[Notion AI](https://www.notion.so/product/ai)

__Coding:__

[Github Copilot](https://github.com/features/copilot)

[GitHub Copilot Chat](https://docs.github.com/en/copilot/github-copilot-chat/copilot-chat-in-ides/using-github-copilot-chat-in-your-ide?tool=vscode)


## 2. Summary

GPT是一个推理模型，主要是基于``Pre-train``和``Fine-tuning``两个阶段。在Pre-train阶段会使用一个大规模的语料库进行基础训楼，例如使用Wikipedia，新闻文章，小说等进行训练。当训练完成后，输入一句话(称为``Prompt``)给它，它会基于这句话给出一个``概率上``的预测，预测后续应该拼接上什么单词。这个拼接的单词是基于它在预训练阶段学习到的知识来进行``概率选定的``，通过一次次循环的单词预测，最终可以拼接上一段话。

Fine-tuning和Prompt是我们与GPT模型唯二的交互方式（当然除此之外还可以通过调整模型的 temperature 和 top_p 两个配置来控制 GPT 更多样化或更具创造性的输出，不过对于输出质量和对下游任务的处理能力并无明显影响）。__Prompt是GPT应用开发的最核心部分。__






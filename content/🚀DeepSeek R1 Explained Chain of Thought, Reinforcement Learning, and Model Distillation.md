---
title: "🚀DeepSeek R1 Explained: Chain of Thought, Reinforcement Learning, and Model Distillation"
source: "https://medium.com/@tahirbalarabe2/deepseek-r1-explained-chain-of-thought-reinforcement-learning-and-model-distillation-0eb165d928c9"
author:
  - "[[Tahir]]"
published: 2025-01-31
created: 2025-02-07
description: "The release of DeepSeek R1, a new large language model from China, has caused a stir in the AI research community. It’s not just another incremental improvement. DeepSeek represents a significant…"
tags:
  - "clippings"
---
![[Pasted image 20250207134948.png]]
The release of DeepSeek R1, a new large language model from China, has caused a stir in the AI research community. It’s not just another incremental improvement. DeepSeek represents a significant leap forward. Most new AI models feel like small steps. [DeepSeek R1](https://github.com/deepseek-ai/DeepSeek-V3/tree/main) is different. It’s the first model in a while that makes you stop and think, *this might be important*.  
DeepSeek R1 的发布，作为中国一款新的大型语言模型，在人工智能研究界引起了轰动。这不仅仅是一次微小的改进。DeepSeek 代表了一个重大的飞跃。大多数新的 AI 模型都感觉像是小步。DeepSeek R1 不同。这是很久以来第一个让你停下来思考，这可能很重要的模型。

A team in China released it last Sunday, and it’s already making waves. Its benchmarks are close to OpenAI’s 01 model in reasoning tasks — math, coding, and science. But what’s interesting isn’t just the numbers. It’s how they got there.  
中国的一支团队上周日发布了它，它已经引起了轰动。它在推理任务——数学、编码和科学——的基准测试中接近 OpenAI 的 01 模型。但有趣的不只是数字。还有他们是如何达到这个水平的。

There are three key ideas behind [DeepSeek R1:](https://github.com/deepseek-ai/DeepSeek-V3/tree/main)  
DeepSeek R1 背后的三个关键思想：

1. **Chain of Thought** — Making the model explain itself.  
   思维链——让模型解释自己。
2. **Reinforcement Learning** — Letting it train itself.  
   强化学习 — 让它自我训练。
2. **Distillation** — Shrinking it without losing power.  
   蒸馏 — 缩小而不失力量。

![[Pasted image 20250207135055.png]]
## Chain of Thought  思维链

If you ask most AI models a tough question, they give you an answer but not the reasoning behind it. This is a problem. If the answer is wrong, you don’t know where it went off track.  
如果你问大多数 AI 模型一个难题，它们会给你一个答案，但不会告诉你背后的推理。这是一个问题。如果答案错了，你不知道它在哪里偏离了轨道。

Chain of Thought fixes this. Instead of spitting out an answer, the model explains its reasoning step by step. If it makes a mistake, you can see exactly where. More importantly, the model itself can see where.  
思维链解决这个问题。模型不是直接给出答案，而是逐步解释其推理过程。如果出错，你可以清楚地看到错误所在。更重要的是，模型本身也能看到错误所在。

This is more than a debugging tool. It changes how models think. The act of explaining forces them to slow down and check their own work. The result is better answers, even without extra training.  
这是一款不止是调试工具。它改变了模型思考的方式。解释的行为迫使它们放慢速度并检查自己的工作。结果是更好的答案，甚至无需额外训练。

The DeepSeek paper shows an example with a math problem. The model walks through the solution, realizes it made a mistake, and corrects itself. That’s new. Most AI models don’t do this. They either get it right or wrong and move on.  
《DeepSeek》论文展示了一个数学问题的例子。模型走过了解决方案，意识到自己犯了一个错误，并进行了纠正。这是新的。大多数 AI 模型不会这样做。它们要么做对，要么做错，然后继续前进。

![](https://miro.medium.com/v2/resize:fit:1300/1*yFrza-9tmTe1I2AkFNlmOw.png)
![[Pasted image 20250207204932.png]]

[*🤖ChatGPT for Vulnerability Detection by Tahir Balarabe  
🤖ChatGPT 用于漏洞检测，作者：Tahir Balarabe*](https://medium.com/@tahirbalarabe2/chatgpt-for-vulnerability-detection-by-tahir-balarabe-affaf19bb0ad)

## Reinforcement Learning  强化学习

Most AI training looks like school: show the model a problem, give it the right answer, and repeat. DeepSeek takes a different approach. It learns more like a baby.  
大多数人工智能训练看起来像学校：向模型展示一个问题，给它正确的答案，然后重复。DeepSeek 采取了一种不同的方法。它更像是一个婴儿那样学习。

Babies don’t get instructions. They experiment, fail, adjust, and try again. Over time, they get better. That’s how reinforcement learning works. The model explores different ways to answer a question and picks the one that works best.  
婴儿不会得到指令。他们尝试、失败、调整，然后再次尝试。随着时间的推移，他们变得更好。这就是强化学习的工作原理。模型探索不同的方法来回答一个问题，并选择最有效的方法。

This is how robots learn to walk. It’s how self-driving cars learn to navigate. And now, it’s how DeepSeek improves its reasoning.  
这是机器人学习行走的方式。这是自动驾驶汽车学习导航的方式。现在，这是 DeepSeek 提高其推理能力的方式。

The key idea is **Group Relative Policy Optimization (GRPO)**. Instead of grading answers as simply right or wrong, GRPO compares them to past attempts. If a new answer is better than an old one, the model updates its behavior.  
关键思想是组相对策略优化（GRPO）。GRPO 不是简单地评判答案对错，而是将它们与过去的尝试进行比较。如果一个新答案比旧答案好，模型就会更新其行为。

This makes learning cheaper. Instead of needing massive amounts of labeled data, the model trains itself by iterating on its own mistakes. That’s why DeepSeek R1 improves over time while OpenAI’s 01 model stays static. Given enough training, it might even reach human-level accuracy in reasoning tasks.  
这使得学习更便宜。不需要大量的标记数据，该模型通过迭代自己的错误来自我训练。这就是为什么 DeepSeek R1 会随着时间的推移而改进，而 OpenAI 的 01 模型保持静态。在足够的训练下，它甚至可能在推理任务中达到人类水平的准确性。

![[Pasted image 20250207205357.png]]

[*🤖ChatGPT for Vulnerability Detection by Tahir Balarabe  
🤖ChatGPT 用于漏洞检测，作者：Tahir Balarabe*](https://medium.com/@tahirbalarabe2/chatgpt-for-vulnerability-detection-by-tahir-balarabe-affaf19bb0ad)

## Distillation  蒸馏

There’s a problem with models like DeepSeek: they’re too big.  
深度寻求等模型存在问题：它们太大。

The full version has 671 billion parameters. Running it requires thousands of GPUs and the kind of infrastructure only tech giants can afford. That makes it impractical for most people.  
完整版本有 6710 亿个参数。运行它需要数千个 GPU 以及只有科技巨头才能负担得起的基础设施。这使得它对大多数人来说不切实际。

The solution is **distillation** — taking a giant model and compressing it into a smaller one without losing too much performance. Think of it as teaching an apprentice. The big model generates examples, and the small model learns from them.  
解决方案是蒸馏——将一个大型模型压缩成一个更小的模型，同时不损失太多性能。把它想象成教导学徒。大型模型生成示例，小型模型从中学习。

DeepSeek researchers distilled their model into Llama 3 and Qwen. The surprising part? The smaller models sometimes performed better than the original. This makes AI far more accessible. Instead of needing a supercomputer, you can run a powerful model on a single GPU.  
DeepSeek 研究人员将他们的模型提炼成了 Llama 3 和 Qwen。令人惊讶的是，较小的模型有时甚至比原始模型表现更好。这使得人工智能变得更加易于访问。不再需要超级计算机，你可以在单个 GPU 上运行一个强大的模型。

![](https://miro.medium.com/v2/resize:fit:1300/1*PINQ3ZBjxMoHkwWNFK7Llg.png)

[*🤖ChatGPT for Vulnerability Detection by Tahir Balarabe  
🤖ChatGPT 用于漏洞检测，作者：Tahir Balarabe*](https://medium.com/@tahirbalarabe2/chatgpt-for-vulnerability-detection-by-tahir-balarabe-affaf19bb0ad)

## Why This Matters  为什么这很重要

DeepSeek’s combination of Chain of Thought reasoning, reinforcement learning, and model distillation makes it a formidable tool. It’s not just about raw power. It’s about creating models that are accurate, transparent, and accessible.  
DeepSeek 结合了思维链推理、强化学习和模型蒸馏，使其成为一款强大的工具。这不仅仅关乎原始力量。这关乎创建准确、透明和易于访问的模型。

Chain of Thought makes the model’s reasoning clear. Reinforcement learning allows it to improve over time. And distillation ensures that these capabilities are available to a wider audience, not just those with access to supercomputers.  
思维链使模型的推理清晰。强化学习使它能够随着时间的推移而改进。而蒸馏确保这些能力可供更广泛的受众使用，而不仅仅是那些能够访问超级计算机的人。

If you’re interested in AI, DeepSeek is worth paying attention to. It’s not just another incremental improvement. It’s a step toward models that can think, learn, and adapt in ways that were previously out of reach.  
如果您对 AI 感兴趣，DeepSeek 值得关注。它不仅仅是另一个渐进式改进。它是一步向能够以先前无法触及的方式思考、学习和适应的模型迈进。

The best part? You don’t need to be an AI researcher to see its potential. The techniques behind DeepSeek are already being applied in real-world applications, from coding assistants to scientific research tools. And as these models become more accessible, their impact will only grow.  
最好的部分？你不需要成为一名 AI 研究人员就能看到它的潜力。DeepSeek 背后的技术已经在实际应用中得到了应用，从编码助手到科学研究工具。随着这些模型变得更加易于获取，它们的影响只会增长。

DeepSeek R1 is important not just because of what it can do, but because of how it does it.  
DeepSeek R1 之所以重要，不仅因为它能做什么，还因为它是如何做到的。

- Chain of Thought makes AI more transparent.  
  思维链使人工智能更加透明。
- Reinforcement learning makes it more self-improving.  
  强化学习使其更具自我改进能力。
- Distillation makes it more available.  
  蒸馏使其更易获得。

These aren’t just optimizations. They’re shifts in how AI models work. And if DeepSeek keeps improving, it might push the entire field forward.  
这不是简单的优化。这是 AI 模型工作方式的转变。如果 DeepSeek 持续改进，它可能会推动整个领域向前发展。

If you want to see where AI is going, this is a good place to look.  
如果您想了解人工智能的发展方向，这里是一个不错的观察点。

So, if you’re curious, dive into the [*paper*](https://github.com/deepseek-ai/DeepSeek-V3/tree/main). Or better yet, try out DeepSeek for yourself. It’s not every day that you get to see a breakthrough in action.  
所以，如果你好奇，就深入研究这篇论文吧。或者更好的是，亲自尝试一下 DeepSeek。不是每天都能看到突破性进展的实际应用。

[*🤖ChatGPT for Vulnerability Detection by Tahir Balarabe  
🤖ChatGPT 用于漏洞检测，作者：Tahir Balarabe*](https://medium.com/@tahirbalarabe2/chatgpt-for-vulnerability-detection-by-tahir-balarabe-affaf19bb0ad)

![](https://miro.medium.com/v2/resize:fit:1400/1*YsBPZhuF2qIZX8N9kZ1jYQ.png)

## Further Reading::  进一步阅读：

[🤖ChatGPT for Vulnerability Detection by Tahir Balarabe  
🤖ChatGPT 用于漏洞检测，作者：Tahir Balarabe](https://medium.com/@tahirbalarabe2/chatgpt-for-vulnerability-detection-by-tahir-balarabe-affaf19bb0ad)

[What are AI Agents?  
人工智能代理是什么？](https://medium.com/@tahirbalarabe2/what-are-ai-agents-f06ef775e78f)

[Stable Diffusion Deepfakes: Creation and Detection  
稳定扩散深度伪造：创建与检测](https://medium.com/@tahirbalarabe2/stable-diffusion-deepfakes-creation-and-detection-15103f99f55d)

[The Difference Between AI Assistants and AI Agents (And Why It Matters)  
人工智能助手与人工智能代理的区别（以及为什么这很重要）](https://medium.com/@tahirbalarabe2/stable-diffusion-deepfakes-creation-and-detection-15103f99f55d)

[🤔What is AI Inferencing?  
人工智能推理是什么？](http://xn--what%20is%20ai%20inferencing-i7171a/?)

[💡Prompt Tuning: A New Approach to Large Language Model Specialization  
提示微调：大型语言模型专业化的新方法](https://medium.com/@tahirbalarabe2/prompt-tuning-a-new-approach-to-language-model-specialization-6abd12cea528)

[💡Retrieval-Augmented Generation(RAG) for Accurate LLMs  
检索增强生成(RAG)用于准确LLMs](http://xn--retrieval-augmented%20generation\(rag\)%20for%20accurate%20llms-lb495d/)

## FAQ about DeepSeek R1  关于 DeepSeek R1 的常见问题

**What is DeepSeek R1 and why is it significant?  
什么是 DeepSeek R1 以及为什么它很重要？**

DeepSeek R1 is a new large language model developed by a research team in China. It’s significant because it demonstrates performance comparable to leading models like OpenAI’s 01 on complex tasks like mathematical, coding, and scientific reasoning. The model’s innovations, particularly in using reinforcement learning and model distillation, could potentially make AI more efficient and accessible.  
DeepSeek R1 是中国研究团队开发的新大型语言模型。它的重要性在于，它在数学、编码和科学推理等复杂任务上的表现可与 OpenAI 的 01 等领先模型相媲美。该模型在强化学习和模型蒸馏方面的创新，有可能使人工智能更加高效和易于访问。

**How does DeepSeek R1 use Chain of Thought prompting, and what benefits does it provide?  
DeepSeek R1 如何使用思维链提示，它提供了哪些好处？**

DeepSeek R1 uses Chain of Thought prompting by encouraging the model to “think out loud” or provide step-by-step reasoning in its responses. For example, when solving math problems, it will show each step of its work. This approach not only allows for identifying mistakes more easily but also makes it possible for the model to self-evaluate and improve its accuracy through re-prompting or re-evaluation of its steps.  
DeepSeek R1 通过鼓励模型“大声思考”或在其回答中提供逐步推理，使用思维链提示。例如，在解决数学问题时，它会展示其工作的每一步。这种方法不仅更容易识别错误，而且使模型能够通过重新提示或重新评估其步骤来自我评估并提高其准确性。

**How does DeepSeek R1 employ reinforcement learning, and how does it differ from typical methods?  
DeepSeek R1 如何使用强化学习，以及它与典型方法有何不同？**

DeepSeek R1 uses reinforcement learning to learn through self-guided exploration, similar to how a baby learns to walk. Instead of being trained with explicit question-answer pairs, it explores its “environment” and optimizes its behavior by maximizing rewards, for example, by favoring shorter, more efficient methods when solving equations. This differs from traditional methods where models are explicitly trained with input/output pairs. A key difference is that DeepSeek R1’s performance increases over time rather than remaining static.  
DeepSeek R1 通过自我引导探索学习，类似于婴儿学习走路的方式。它不是通过显式的问答对进行训练，而是探索其“环境”，通过最大化奖励来优化其行为，例如，在解方程时优先选择更短、更有效的方法。这与传统方法不同，传统方法中模型是通过输入/输出对进行显式训练的。一个关键的区别是，DeepSeek R1 的性能随着时间的推移而提高，而不是保持静态。

**What is Group Relative Policy Optimization (GRPO) and how does it work within DeepSeek R1?  
什么是组相对策略优化（GRPO）以及它如何在 DeepSeek R1 中工作？**

Group Relative Policy Optimization (GRPO) is a reinforcement learning technique used by DeepSeek R1 to self-improve by comparing new responses with previous ones. It assigns a reward based on the relative improvement from past responses. To prevent drastic changes in behavior, it uses a clipping function to ensure stability while maximizing the model’s reward, enabling gradual refinement and optimization of the model over time.  
群体相对策略优化（GRPO）是 DeepSeek R1 使用的强化学习技术，通过比较新旧响应来自我改进。它根据过去响应的相对改进分配奖励。为了防止行为发生剧烈变化，它使用裁剪函数来确保稳定性，同时最大化模型的奖励，使模型随着时间的推移逐渐优化和改进。

**What is model distillation, and why is it important in the context of DeepSeek R1?  
什么是模型蒸馏，以及为什么它在 DeepSeek R1 的背景下很重要？**

Model distillation is the process of transferring knowledge from a large, complex model (like DeepSeek R1 with its 671 billion parameters) to a smaller, more lightweight model (like Llama 3 or Qwen). This makes the technology more accessible because it reduces the computational resources needed to run the model. Interestingly, the smaller models sometimes even outperform the original larger model.  
模型蒸馏是将知识从大型、复杂模型（如拥有 6710 亿参数的 DeepSeek R1）转移到更小、更轻量级模型（如 Llama 3 或 Qwen）的过程。这使得技术更加易于访问，因为它减少了运行模型所需的计算资源。有趣的是，较小的模型有时甚至能超越原始的大型模型。

**How does model distillation benefit the accessibility of AI technology?  
模型蒸馏如何使人工智能技术的可及性受益？**

Model distillation makes high-performance AI more accessible by allowing researchers to create smaller language models that operate at a fraction of the cost without a significant reduction in performance. This enables wider use of AI technologies as it doesn’t require huge computing infrastructures. This opens the door for smaller teams and individuals to run very capable LLMs.  
模型蒸馏通过允许研究人员创建性能降低很小但成本仅为原来一小部分的更小语言模型，使得高性能 AI 更加易于获取。这使得 AI 技术的应用范围更广，因为它不需要庞大的计算基础设施。这为小型团队和个人运行非常强大的LLMs打开了大门。

**How does the combination of Chain of Thought prompting, reinforcement learning, and GRPO contribute to DeepSeek R1’s overall performance?  
如何将思维链提示、强化学习和 GRPO 的结合对 DeepSeek R1 的整体性能做出贡献？**

By combining Chain of Thought prompting and reinforcement learning with GRPO, DeepSeek R1 achieves its high level of performance and self-improvement. Chain of Thought allows the model to self-reflect on its reasoning, while reinforcement learning enables it to optimize its approach based on the rewards it earns from its performance. GRPO stabilizes the learning process by incrementally comparing new responses to older ones, allowing it to make more efficient and less erratic improvements.  
通过结合思维链提示和 GRPO 强化学习，DeepSeek R1 实现了其高性能和自我提升。思维链使模型能够对自己的推理进行自我反思，而强化学习则使它能够根据从其表现中获得的奖励来优化其方法。GRPO 通过逐步比较新响应与旧响应来稳定学习过程，使其能够进行更高效和更稳定的改进。

**What are the main takeaways from the research behind DeepSeek R1?  
深度 Seek R1 背后的研究有哪些主要收获？**

The main takeaways from the research behind DeepSeek R1 are its utilization of Chain of Thought reasoning for improved accuracy, reinforcement learning with GRPO for self-optimization and increased performance over time, and model distillation to improve accessibility to powerful AI without requiring vast computational resources. These three innovations represent progress toward more efficient, accessible, and scalable large language models.  
深度 Seek R1 研究的主要收获是其利用思维链推理提高准确性，使用 GRPO 进行强化学习以实现自我优化和性能随时间提升，以及模型蒸馏以在不需大量计算资源的情况下提高强大 AI 的易用性。这三个创新代表了向更高效、易用和可扩展的大型语言模型迈进。
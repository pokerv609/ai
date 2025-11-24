# AI
Learn AI

## Courses
- [AI For Everyone](https://www.coursera.org/learn/ai-for-everyone)

    This course is a fantastic introduction to artificial intelligence, breaking down complex terms such as neural networks, deep learning, and machine learning in a way that’s easy to grasp. It clears up common confusion around these buzzwords and explains key concepts, such as the difference between supervised learning (where AI learns from labeled examples) and unsupervised learning (where AI finds patterns on its own). The course also highlights how data analytics differs from machine learning and outlines the distinct roles of data analysts, machine learning engineers, and machine learning researchers. I’d love to see future updates include generative AI and the emerging roles of Generative AI Engineers/Researchers.

- [Generative AI for Everyone](https://www.coursera.org/learn/generative-ai-for-everyone/)

  Generative AI for Everyone explains how modern generative models like large language models work and how they’re applied in real situations. Andrew Ng breaks down that these systems don’t “understand” meaning — they generate text by predicting the next most likely token based on patterns learned from huge datasets. This explains why they can produce impressive results while still hallucinating or making confident mistakes.
  The course highlights three main approaches to using generative AI in organizations: using foundation models directly, fine-tuning them on specialized data, and retrieval-augmented generation (RAG), where a model retrieves information from an external knowledge base instead of relying only on what it was trained on. A key takeaway is that RAG is often the most practical solution for businesses, because it avoids the cost and complexity of training large models from scratch while providing more accurate, grounded responses.
  Andrew also focuses on how generative AI changes workflows and jobs. Instead of fully replacing roles, AI automates specific tasks and shifts human work toward oversight, creativity, and complex decision-making. The course emphasizes building cross-functional teams, rapid iteration, and selecting narrow, high-impact projects instead of broad, unfocused goals.
  Finally, the course addresses safety and ethics: bias in training data, accountability for model outputs, responsible deployment, and transparency. The message is that generative AI can create major value, but only when applied thoughtfully and with clear guardrails.

## Videos
- [LLM Reasoning](https://www.youtube.com/watch?v=ebnX5Ur1hBk), [pdf](https://dennyzhou.github.io/LLM-Reasoning-Stanford-CS-25.pdf)

    The lecture focuses on how Large Language Models perform reasoning, emphasizing the importance of intermediate reasoning tokens (Chain-of-Thought) rather than directly predicting answers. He explains that theoretical work shows transformers can solve complex sequential problems only when they generate intermediate steps; trying to output final answers directly requires extremely deep models or fails entirely. Therefore, reasoning is not a prompting trick — it is fundamentally tied to the model architecture and token-by-token generation. 

    A central claim of the talk is that contrary to common belief, pre-trained LLMs already possess reasoning ability, but greedy decoding hides it. By exploring multiple decoding paths and selecting candidates with the highest confidence, models naturally produce reasoning-based answers. This idea is formalized in Chain-of-Thought (CoT) decoding, which samples multiple output sequences and picks the answer with the strongest statistical support. 

    1. Chain-of-Thought prompting, which works but is brittle and task-specific. 
    2. Supervised finetuning (SFT) with human-written step-by-step solutions, which improves reasoning but generalizes poorly. 
    3. Reinforcement learning finetuning (ReFT / RLHF-style) using model-generated reasoning steps and verifiers, which significantly improves generalization by directly optimizing correctness rather than next-token likelihood. Verifier quality is crucial. 


    Another key technique is Self-Consistency, where multiple reasoning paths are sampled and the most frequent final answer is selected, improving accuracy on math and logic tasks. Zhou also introduces Universal Self-Consistency, in which the model evaluates its own responses and selects the most internally consistent one. The talk then expands beyond chain-of-thought to hybrid approaches. Combining retrieval + reasoning outperforms reasoning alone, enabling analogical reasoning, decomposition, and more robust problem solving. 
    
    #### Key takeaways:
    - Reasoning requires intermediate steps; output length matters as much as model size.
    - Pretrained LLMs can reason without specialized prompting if decoding is improved.
    - RL finetuning outperforms SFT, especially for verifiable problems.
    - Aggregation methods (Self-Consistency) significantly improve reliability.
    - Retrieval + reasoning is the strongest current paradigm.
    - Future breakthroughs must handle tasks without uniquely verifiable answers and real applications rather than benchmarks
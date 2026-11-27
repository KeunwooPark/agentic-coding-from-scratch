# Agentic Coding From Scratch

This booklet organizes the basic concepts of software engineering from a slightly different angle, for agentic coding. Agentic coding means writing software with AI agents. Well-known coding agents include [Claude Code](https://github.com/anthropics/claude-code) and [Codex](https://github.com/openai/codex). This booklet puts more weight on system design, and focuses less on writing code than on managing it and making sure it is reliable. It leaves out things that engineers used to need to know in detail but that can now be handed to a coding agent. It does cover what you still need to know when you work with one.

## Why I wrote this booklet

Now that coding with AI has become very easy, people without engineering knowledge want to build software, and they have started doing it. But from my own experience and what I've observed, I've found that agentic coding has a few traps that are easy to fall into.

The most common problem is that complexity grows out of control as a system gets bigger. AI builds what you ask for right away. But it builds only what you asked for; it doesn't build with the whole system in mind. You might ask, can't I just have the AI do that too? But the best way to get AI to build in line with the overall structure is to set up a good structure in the first place. If a system has no structure, AI will pile things on top of it somehow; if the structure is well set up, it builds within that frame. In other words, how to divide and organize a system is something the person building it has to decide and state explicitly. I'm not the only one saying that systems thinking matters. For example, Elizabeth Stone, Netflix's CTO, has [made a similar point](https://youtu.be/t0GiTyz4syY).

Another problem is that people struggle to go from a program for themselves to a product for everyone. Building a simple web app that runs on your own computer is really easy. But what do you have to do so that other people can use it too? People say you can upload it to Vercel, but what is Vercel, and is that the only way? What do you need to do to keep maintaining it? To answer questions like these, you first need to know what to ask.

In AI communities, many people ask questions, and the answer is usually "just ask the AI." People seem to think that with AI, you can learn anything. I think that's only half right. The biggest limitation of AI is that you have to ask the question. Asking good questions is a skill, and to ask good questions you need to know what matters and what doesn't. Paradoxically, telling those apart takes knowledge. In other words, to start learning, you need at least a little foundational knowledge.

Saying that you need the basics may sound like putting up a hurdle to keep newcomers out. That is not the intent at all. I studied engineering and never trained as a writer. Having AI doesn't mean I can become a great writer overnight. If I wrote with AI, I'd only produce writing that sounds plausible but is shallow, because what makes a great writer is not polished expression. A great writer has to think deeply and come up with gripping stories, and I haven't trained for that. Engineering is the same. Put the other way around, anyone who trains can become an engineer. This booklet aims to be the starting point of that training.

Another reason I'm writing this booklet is to talk and debate with other developers. Now that AI agents have shifted the paradigm of software engineering, I thought we needed a place to talk about what good engineering is. This booklet is one way of sharing my thoughts. If there are parts you disagree with, I'd be grateful if you sent your feedback directly to me, without holding back.

Starting from these points, this booklet re-organizes software engineering from the point of view of agentic coding. Now that agents write the code instead of us, some topics matter more than before, and some matter less. Along with these, the booklet covers how large language models (LLMs) and agentic systems work, and the process software goes through as it is developed.

## Scope of this booklet

This booklet covers only things that **won't change unless there is another paradigm shift**. In particular, AI tools, models, and services change every few months, so they are not covered here. When the booklet mentions a specific tool or service, it is only an example to explain an idea, not a recommendation to use it.

Learning by following along helps more than just being told, so this booklet teaches by building. As you follow it, you build an AI agent system like [Hermes Agent](https://github.com/NousResearch/hermes-agent) or [OpenClaw](https://github.com/openclaw/openclaw) using agentic coding. Each chapter explains a concept and then applies it to the agent we are building. By the last chapter, you will have built a complex agent system yourself, and you will know how the agents you use every day work inside.

Much of this booklet is the author's opinion. Anything without a reference is the author's opinion.

## Who is this booklet for?

I wrote this booklet for **non-engineers who want to become engineers**, especially those who want to go beyond building programs as a hobby and build software for other people. I think it can help:

- People who build software with AI coding agents but have never studied software engineering
- Designers, planners, and researchers who want to build products themselves
- Anyone who wants to know how AI agents work inside

On the other hand, if your goal is to build only what you need for yourself and you don't think you need engineering knowledge, you don't need to read this booklet.

## Contents

1. [System](chapter1.md)
2. [Module](chapter2.md)
3. [Coding and Agentic Coding](chapter3.md)
4. [Complexity and Complicatedness](chapter4.md)
5. [LLM](chapter5.md)
6. [Agentic Systems](chapter6.md)
7. [Debugging](chapter7.md)
8. [Testing](chapter8.md)
9. [Version Control](chapter9.md)
10. [Deploy](chapter10.md)
11. [CI/CD](chapter11.md)
12. [Web/App Applications](chapter12.md)
13. [Security](chapter13.md)
14. [What's Next?](chapter14.md)

## Author

- [Keunwoo Park](https://kwpark.io/): studied mechanical engineering and computer science, and studied Human-Computer Interaction (HCI) in graduate school. Still thinks the world is short on good software. Email: [keunwoopark.524@gmail.com](mailto:keunwoopark.524@gmail.com).

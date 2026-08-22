---
title: 'Google OKF + Hermes Agent + Gbrain: Turn Any Folder Into a Knowledge Graph'
tags:
- Data Science
- Machine Learning
- Artificial Intelligence
- Programming
- Technology
published: '2026-08-02'
free: false
freedium_url: https://freedium-mirror.cfd/https://medium.com/@GaoDalie_AI/google-okf-hermes-agent-gbrain-turn-any-folder-into-a-knowledge-graph-eb91d072326d
source_url: https://medium.com/@GaoDalie_AI/google-okf-hermes-agent-gbrain-turn-any-folder-into-a-knowledge-graph-eb91d072326d
---

# Google OKF + Hermes Agent + Gbrain: Turn Any Folder Into a Knowledge Graph

*Published Aug 02, 2026 · Free: No*

Many people are fascinated by the **"LLM-Wiki"** concept proposed by Andrej Karpathy, where an LLM reads and writes Markdown wikis to work autonomously. As a result, many individuals and small teams are starting to implement it.

When giving tasks to AI, the biggest problem is often not the AI model itself, but rather "how to provide it with the necessary background information."

For example, if you ask the AI to "summarise last month's order data," it cannot give the correct answer unless it knows which tables contain the data, what the columns mean, and how the tables are connected.

The main point is that the problem OKF is trying to solve is "information silos" rather than "scaling."

The problem described in the official blog is simple: important internal knowledge, such as table schemas, metric definitions, incident response guides, system JOIN paths, and other information, is spread across different places like metadata catalogues, wikis, code comments, and even the knowledge of experienced employees.

Because of this, every time a new AI agent is created, teams must go through the same process of collecting and understanding the necessary context from the beginning.

<!-- iframe: 854x480 -->
[Embedded content](https://cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F1DEh042Rovg%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D1DEh042Rovg&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F1DEh042Rovg%2Fhqdefault.jpg&type=text%2Fhtml&schema=youtube)

OKF is a standard that provides a common set of rules for these "wikis that are not designed to cooperate." It's easiest to understand it as a proposal to provide a "common spoken language" for Markdown wikis for AI, similar to "HTML" on the internet.

### What's so good about OKF?

Much of the knowledge that needs to be passed on to an AI agent is **internal company knowledge**.

This includes table definitions, metric calculation methods, operational procedures, and API specifications. However, this information is scattered across wikis, catalogs, code, and people's heads.

As a result, every time you create an agent, you have to **rebuild the necessary context from scratch**.

The Google Cloud Blog calls this **the context-assembly problem. More details will be provided in the "Key Points" section later on.**

By using OKF, you can accumulate the necessary context while using AI and then utilize it directly.

OKF is designed to **consolidate (compile)** scattered knowledge into Markdown files that can be managed with Git and then maintained. The advantage is that instead of having to search for the information every time a question `index.md`is asked, agents and people read the source code and translate it into OKF bundles, so you can just follow along from there.

### How Do Agents Use OKF?

AI agents often struggle to maintain practical accuracy simply by calling upon a model. They need to understand the specific context of the business, refer to the correct data definitions, and take into account past decisions and operational knowledge.

OKF is intended to be used as an "internal knowledge base that agents can read." However, having OKF does not automatically improve the output quality of agents. The accuracy of the knowledge described, the frequency of updates, the method of connecting with existing systems, and the reference design on the agent side all affect its practicality.

Furthermore, OKF v0.1 is not a finished standard, but rather an initial specification that will evolve through future implementations and use cases. In the age of AI, one key issue will be organising internal documents and metadata in a way that is easily accessible to AI agents. OKF can be referenced as a candidate format for this purpose.

### Before we start! 🦸🏻‍♀️

If you like this topic and you want to support me:

1. **Clap** my article 50 times; that will really help me out.👏
2. [Follow](https://medium.com/@mr.tarik098) me on Medium and subscribe to get my latest article for Free🫶
3. Join the family — Subscribe to the [YouTube channel](https://www.youtube.com/channel/UC6P5WCWjqhhXVFBqbJHNxyw)

### MCP Vs RAG Vs OKF

Around AI agents, there are several conventions and technologies with similar objectives to OKF. Because it's easy to confuse them with MCP and RAG, we'll summarise their roles in a table.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*nwZjIpiJgLtp5S5Yk5Cl9w.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*nwZjIpiJgLtp5S5Yk5Cl9w.png 1x">
  <img src="/img/medium/700/1*nwZjIpiJgLtp5S5Yk5Cl9w.png" alt="None" width="739" height="406" loading="lazy" data-zoom-src="/img/medium/4000/1*nwZjIpiJgLtp5S5Yk5Cl9w.png" class="prose-image"/>
</picture>

In short, **OKF is responsible for "knowledge that is written in advance," while MCP and RAG are responsible for "mechanisms for retrieving and connecting data on the spot** ." For example, the "definition of weekly active users" can be written in OKF, and the actual query to BigQuery can be done via MCP. RAG is not mutually exclusive, and it is possible to use OKF bundles as search targets in RAG as well.

It's not about choosing one option, but rather a practical approach to examine **which areas you already possess and where you're lacking.**

### How to install Hermes + Wiki LLM

In this video, I'll show you step by step how to install Hermes on a VPS, so you can chat with your assistant from anywhere. I'll also show you how to start adding a Knowledge Graph and Gbrain to expand what your assistant can do

Let's start the deployment process. To get the best deal on your VPS, make sure to sign up using [my link](https://hostinger.com/gao10). You'll get an extra 10% off any Hostinger plan.

Once you click the link, you'll be taken to the Hermes Agent deployment page.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*Sxf1-x-D7_Qk8QADMhSADg.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*Sxf1-x-D7_Qk8QADMhSADg.png 1x">
  <img src="/img/medium/700/1*Sxf1-x-D7_Qk8QADMhSADg.png" alt="None" width="1619" height="741" loading="lazy" data-zoom-src="/img/medium/4000/1*Sxf1-x-D7_Qk8QADMhSADg.png" class="prose-image"/>
</picture>

Click on **Start**, and you will join me on the cart page to select your VPS plan. You should see our coupon code applied automatically. If not, just enter **GAO** manually.

First, choose your billing period. You can select 1 month, 12 months, or 24 months. For the best price, I recommend the 12-month plan.

Next, scroll down and enable daily auto backups. Hermes Agent can reconfigure its own server environment, so if something breaks, having backups will help you quickly restore everything.

After that, choose the server location with the lowest latency. Unless you specifically need another region, I recommend keeping the default option.

Finally, click the **Continue** button.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*VAAWckWp_OQE_U9AE9PwZQ.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*VAAWckWp_OQE_U9AE9PwZQ.png 1x">
  <img src="/img/medium/700/1*VAAWckWp_OQE_U9AE9PwZQ.png" alt="None" width="1259" height="895" loading="lazy" data-zoom-src="/img/medium/4000/1*VAAWckWp_OQE_U9AE9PwZQ.png" class="prose-image"/>
</picture>

Once you've signed up for your VPS, you'll be taken to the Hermes Agent configuration page after your payment is processed. Just a quick heads-up: this page changes often, so your screen may look a little different from mine.

In this video, we'll use the Nexos API as the default. This will let you use multiple models with Hermes Agent.

After that, click Next, review all the files, then click Deploy. The deployment process usually takes around 5 minutes to finish.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*aho_esyD2ns3bp_SRv9Ulg.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*aho_esyD2ns3bp_SRv9Ulg.png 1x">
  <img src="/img/medium/700/1*aho_esyD2ns3bp_SRv9Ulg.png" alt="None" width="1044" height="966" loading="lazy" data-zoom-src="/img/medium/4000/1*aho_esyD2ns3bp_SRv9Ulg.png" class="prose-image"/>
</picture>

Welcome to Hostinger Docker Manager. You can see here that your Hermes agent is already running in a new Docker project, and it has Traefik set up as a reverse proxy to make sure that you can access your agent from anywhere on the web securely

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*n5k7fbDfBLoKaxL_TxEEoA.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*n5k7fbDfBLoKaxL_TxEEoA.png 1x">
  <img src="/img/medium/700/1*n5k7fbDfBLoKaxL_TxEEoA.png" alt="None" width="1905" height="866" loading="lazy" data-zoom-src="/img/medium/4000/1*n5k7fbDfBLoKaxL_TxEEoA.png" class="prose-image"/>
</picture>

Once the deployment is finished, open the Hermes dashboard and confirm that the first launch completes successfully. This is the moment the setup becomes more than just a plan.

Hermes is now live, running in a permanent environment, and ready to get to work.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*7uQy-Frm9J-u3Q4eHHGmLQ.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*7uQy-Frm9J-u3Q4eHHGmLQ.png 1x">
  <img src="/img/medium/700/1*7uQy-Frm9J-u3Q4eHHGmLQ.png" alt="None" width="1919" height="983" loading="lazy" data-zoom-src="/img/medium/4000/1*7uQy-Frm9J-u3Q4eHHGmLQ.png" class="prose-image"/>
</picture>

So instead of checking the dashboard and thinking, "Nice, it's installed. Now I can use Hermes for my Second Brain," Hermes Agent already has Wiki LLM installed and ready to go by default.

Gbrain is a memory infrastructure for storing such information in a format that AI agents can use later. It's open-source software released by YCombinator CEO Garry Tan, and I was drawn to its ability to serve as an LLM Wiki.

The LLM Wiki I'm referring to here isn't just a wiki for humans to read, but rather an external memory that stores knowledge in a format that's easy for LLMs and AI agents to refer to.

I think it's similar to the Wiki-like concept for LLMs that Andrej Karpathy, also known as an early member of OpenAI, has talked about.

GBrain embeds saved information and uses vector search to find semantically similar past contexts.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*jAMl_ImyuSgX_o4vHXwZ2w.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*jAMl_ImyuSgX_o4vHXwZ2w.png 1x">
  <img src="/img/medium/700/1*jAMl_ImyuSgX_o4vHXwZ2w.png" alt="None" width="2512" height="1358" loading="lazy" data-zoom-src="/img/medium/4000/1*jAMl_ImyuSgX_o4vHXwZ2w.png" class="prose-image"/>
</picture>

The key is that it's not just a simple keyword search, but it can retrieve information based on semantic similarity, such as "cases where similar decisions were made in the past" or "business constraints related to this function."

These are the manual commands. Once everything is set up, you can run Gbrain and then PGLite. This process prepares Gbrain and then runs `gbrain doctor` to verify that everything is configured correctly.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*j1S2EkNIF_RmzUF6ESmbSA.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*j1S2EkNIF_RmzUF6ESmbSA.png 1x">
  <img src="/img/medium/700/1*j1S2EkNIF_RmzUF6ESmbSA.png" alt="None" width="2562" height="1214" loading="lazy" data-zoom-src="/img/medium/4000/1*j1S2EkNIF_RmzUF6ESmbSA.png" class="prose-image"/>
</picture>

Since we are doing this in Hermes, the setup will be handled automatically, so you won't need to enter those commands manually. Everything will be installed and verified for you, including the OpenAI embeddings configuration.

As you can see, Gbrain has been around for a long time and offers many optional skill packs. A lot of additional tools and features are also built around it.

<picture>
  <source media="(max-width: 768px)" srcset="/img/medium/700/1*vZdLwZX4cg1jUt7zCAiC9Q.png 1x">
  <source media="(min-width: 769px)" srcset="/img/medium/2000/1*vZdLwZX4cg1jUt7zCAiC9Q.png 1x">
  <img src="/img/medium/700/1*vZdLwZX4cg1jUt7zCAiC9Q.png" alt="None" width="2040" height="1278" loading="lazy" data-zoom-src="/img/medium/4000/1*vZdLwZX4cg1jUt7zCAiC9Q.png" class="prose-image"/>
</picture>

### Conclusion :

Looking at Google's Open Knowledge Format (OKF) made me realise something. OKF and RAG focus on making organised knowledge easy for AI to access and use. However, before information becomes knowledge, there is still valuable context hidden in meeting notes, chat logs, doubts, concerns, and unfinished discussions.

That is why ai-context-hooks does not provide organised knowledge directly. Instead, it creates a way for AI to return to the source. OKF is the format after knowledge is organised. A context hook is the entry point before that happens.

Rather than giving AI the answer, we give it a path back to the original context. In the future, not only models and prompts will matter, but also how information is stored and presented to AI.

**📄 Disclosure**: Some of the links are affiliate links. If you purchase them, we earn a small commission at no extra cost to you. This helps us keep our videos free for everyone.

> 🧙‍♂️ I am an AI Generative expert! If you want to collaborate on a project, drop an [inquiry here](https://docs.google.com/forms/d/e/1FAIpQLSelxGSNOdTXULOG0HbhM21lIW_mTgq7NsDbUTbx4qw-xLEkMQ/viewform) or Book a [1-on-1 Consulting](https://calendly.com/gao-dalie/ai-consulting-call) Call With Me.

_📚Feel free to check out my other articles:_

[**OpenClaw 5.2 & WhatsApp + Skills: The FASTEST Local Setup You Need Now**](https://medium.com/@GaoDalie_AI/openclaw-5-2-whatsapp-clawhub-fastest-way-to-install-locally-61332d7917b1)
*If you don't have a Medium subscription, use this link to read the full article: Link*

[**Kimi 3, Inkling: These Two Open Models May Change "Everything"
medium.com**](https://medium.com/data-science-collective/kimi-3-inkling-these-two-open-models-may-change-everything-0af000f36af7)

[**Why GPT 5.6 Is Not So Much Better Than Fable 5 And Opus 4.8 — Here's the Result**](https://medium.com/data-science-collective/why-gpt-5-6-is-not-so-much-better-than-fable-5-and-opus-4-8-here-the-result-ef6b270cac3f)
*In June 2026, OpenAI announced its latest model, "GPT-5.6."
On social media, some people are saying, "Isn't it just a…*
# E.K.B.

**Engineering Knowledge Base**

A personal knowledge base for software engineering topics, focused primarily on **.NET backend development, architecture, distributed systems, databases, cloud infrastructure, and AI engineering**.

The repository is built around a structured learning roadmap and contains consolidated study notes from each topic as they are covered.

## Learning Roadmap

The complete roadmap, priorities, and learning progression can be found in:

➡️ **[ROADMAP.md](./ROADMAP.md)**

## Knowledge Base

Each major roadmap category has its own directory containing consolidated technical notes, examples, common pitfalls, and concepts covered during study.

The notes are intended to evolve over time as topics are revisited and deeper knowledge is added.

## Goal

The goal of E.K.B. is to maintain a practical, technically accurate reference for both continued learning and future software-engineering work.

## Using This Roadmap with ChatGPT

You can use this roadmap as a structured curriculum inside ChatGPT.

### Recommended setup

1. Download [`ROADMAP.md`](./ROADMAP.md).
2. Create a new **ChatGPT Project**.
3. Upload `ROADMAP.md` to the project.
4. Add the following project instructions:

> Use `ROADMAP.md` as the canonical learning roadmap.
>
> Teach the roadmap sequentially, prioritizing P0 topics before P1, P2, and P3.
>
> Before each lesson, verify the next topic against the roadmap.
>
> Keep lessons compact, technically rigorous, and practical. Use relevant C#/.NET examples, explain important trade-offs and common mistakes, and verify technical claims and code examples before answering.
>
> Track which topics have been meaningfully covered and which remain. Do not consider a topic completed simply because it was mentioned.
>
> When I say **"continue"**, move to the next appropriate topic in the roadmap.

5. Create a separate chat for each major roadmap category, for example:

   * Modern C# and .NET
   * ASP.NET Core and API Engineering
   * SQL Server and Data Engineering
   * Architecture and Domain Modelling
   * Distributed Systems and Messaging
   * AI Engineering

6. Work through each category progressively.

### Building Your Own Knowledge Base

After completing or substantially covering a category, ask ChatGPT to create a consolidated Markdown study document from that category's chat.

A useful prompt is:

> Create a Markdown study document from everything we learned in this chat.
>
> * Use the latest official learning roadmap as the source of structure.
> * Include only material that was actually taught or meaningfully discussed.
> * Consolidate follow-up questions into the relevant sections.
> * Use the latest corrected explanation when earlier answers were corrected.
> * Remove repetition and conversational filler.
> * Verify all technical claims and code examples.
> * Remove private, employer-specific, company-specific, or project-specific information.
> * Replace useful project-specific examples with neutral examples where appropriate.
> * Include common mistakes and important caveats.
> * End with roadmap topics covered, partially covered, and still remaining.
> * Generate an actual downloadable `.md` file.

These category documents can then be kept alongside `ROADMAP.md`, turning the repository into a progressively expanding engineering knowledge base.

> **Note:** Uploading `ROADMAP.md` gives ChatGPT the curriculum, but it does not transfer another user's previous chats, memory, progress, or project instructions. Each learner should maintain their own learning progress.


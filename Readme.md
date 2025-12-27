# Obsidian Vault Template

## Origin & Philosophy

I wanted to get started with Obsidian and discovered Steph Ango's [blog](https://stephango.com/vault) and Karlos' [video](https://www.youtube.com/watch?v=Dq3R3uS0sQ4&t=789s). Steph Ango is the CEO of the company behind Obsidian, and his vault (which this repo is forked from) is a great example of how to use Obsidian effectively. The core concept is to avoid rigid folder structures and instead rely on **Links** to organize everything.

1.  **Everything is a Link**: Whether it's for organizing by category (like `[[notes]]`, `[[daily]]`), by topic (like `[[ai]]`), or referencing a specific concept (like `[[deep_work]]`), they are all just `[[wiki-links]]` pointing to files in the `references/` folder. There is no fundamental difference between them—you decide how to use them.
2.  **Dynamic Reference Pages**: All these links point to files in `references/`. When you open `[[ai]]`, you don't just see a blank page; you see a dynamically generated table of every note linked to "ai". This is powered by the `.base` files in `templates/bases/`.

## Why do I fork and adapt?

I really like the fascinating philosophy behind. However, I also found the original vault was a bit too complex and overwhelming for a beginner, at least for me.

So, this repository is a **simplified version** that I customized to fit my preferences (e.g., folder structure, snake_case naming). I highly recommend reading the original blog post and watching the video to understand the "Why" first. Then, you can start with the original or use this simplified version as a lighter starting point.

### Vault Structure

Here is a quick overview of the folders and what they do:

```text
.
├── files/                 # THE POOL. Almost all your notes live here flatly.
├── journals/              # Yearly aggregations (e.g., 2025.md).
├── index/                 # THE INDEX. Contains the files for topics and categories.
├── templates/             # Templates for creating new notes.
│   ├── bases/             # Defines the "Views" (tables).
│   ├── daily_template     # For daily streams of thought.
│   ├── note_template      # For standard atomic notes.
│   ├── post_template      # For drafting content to publish.
│   ├── clipping_template  # For articles/content saved from the web.
│   └── index_*_template   # For creating new Index pages.
└── attachments/           # Drag & drop images here.
```

### Differences from the Original

- **Folder Structure**: Flattened hierarchy with a single `files/` pool for content and an `index/` folder for connections.
- **Naming Convention**: More `snake_case` folder and file names are used.
- **Indexing Logic**: Distinct semantic separation between **Category** (Metadata) and **Topic** (Content association), each with dedicated templates to visualize the connections.
- **Templates**: A curated set of templates for daily use, including the dynamic `index_` templates.

## How to continue

You can download this repository, open it with Obsidian, and click around the links to experience the flexibility of this system. However, I highly recommend watching the video mentioned above. It provides a step-by-step walkthrough that covers the philosophy from the blog, which can be a bit brief on its own.

After watching, come back and read the [[Detailed Guide - Obsidian Vault Design & Usage]] included in this vault. Although the practice here differs slightly from the video, you will find it easy to pick up since you understand the underlying philosophy. I believe you'll gain a deeper understanding of how the components work together and how to effectively create new notes, topics, and categories.


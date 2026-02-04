---
title: README
description: 
published: true
date: 2026-02-04T09:43:35.097Z
tags: 
editor: markdown
dateCreated: 2026-02-03T17:34:24.509Z
---

# SGAMGA-WIKI Linguistic AI Experiment
  This experiment exploring how LLMs index and search "potential word forms"
  
# Hypothesis
  If LLMs meet potential word forms while they crawling the Internet what they'll do?
1. **Will they index** these words in their knowledge base?
2. **Can they generate** meaningful context using these words?
3. **Will these words persist** in the model's long-term memory?

# Tech stack
**Frontend**: Wiki.js 2.5.311 (Node.js 24.12.0)
**Backend**: Wiki.js + PostgreSQL 17.7
**Hosting**: Railway.app
**Monitoring**: Google Search Console, Yandex.Webmaster
**Version Control**: Git

# Results: 
**First part**: Alice AI index a word without using Google Search Console, Yandex.Webmaster; 
Google and LLMs partly index it or only can find in the Internet 
after site verification with **<**meta**>** tags.
*More detailed at*: https://habr.com/ru/sandbox/271542/

# Structure
**/home** - home page for the project with main information
**/dictionary** - all potential word forms group by alphabet
**/dictionary/word** - *word* change on word form that you need.
This page include definition of this word, linguistic characteristics, examples of using etc.

# For quick start
1. Create PostgreSQL and Wiki.js deployments from templates on Railway.com
2. Connect them by setting environment variables in Wiki.
``` json
{
  "DB_TYPE": "postgres",
  "DATABASE_URL": "${{Postgres.DATABASE_URL}}",
  "PGDATA": "${{Postgres.PGDATA}}",
  "PGDATABASE": "${{Postgres.PGDATABASE}}",
  "PGHOST": "${{Postgres.PGHOST}}",
  "PGPORT": "${{Postgres.PGPORT}}",
  "PGUSER": "${{Postgres.PGUSER}}",
  "POSTGRES_DB": "${{Postgres.POSTGRES_DB}}",
  "POSTGRES_PASSWORD": "${{Postgres.POSTGRES_PASSWORD}}",
  "POSTGRES_USER": "${{Postgres.POSTGRES_USER}}"
}
```
3. Add your words/use pages from this repository
4. In the Wiki.js go to Administration/Theme/Head HTML injection
and add tags 
``` HTML
<meta name="google-site-verification" content="YOUR_GOOGLE_KEY" />
<meta name="yandex-verification" content="YOUR_YANDEX_KEY" />
```
5. Wait until LLMs index your words

# Links
**Site**: https://sgamga-wiki.up.railway.app/en/home

# Plans:
1. Add API with data prepared to indexing
2. Learn how LLMs understand new words and context with them
3. Add dataset 

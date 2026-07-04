# AI-Powered Email Investigator

## Overview

AI-Powered Email Investigator is an intelligent email discovery and investigation platform designed to help users uncover critical information hidden within large email archives.

The system ingests PST files, mailbox exports, email archives, and individual email messages, then combines enterprise search technology with Large Language Models (LLMs) to provide natural language investigation capabilities.

Instead of manually searching through thousands or millions of emails, investigators can ask questions such as:

* "Show me the emails where Bob approved the budget."
* "Find the smoking gun emails discussing project delays."
* "Who knew about the outage before it happened?"
* "Summarize all discussions regarding the acquisition."
* "Which executives were informed about the security incident?"

The platform leverages Solr for enterprise-scale search, PostgreSQL for metadata and relationship storage, and modern AI models to deliver explainable, evidence-backed answers.

---

# Key Features

## Email Ingestion

Supports importing:

* Microsoft Outlook PST files
* MBOX archives
* EML files
* Maildir structures
* Enterprise archive exports

Extracted content includes:

* Sender
* Recipients
* CC/BCC
* Subject
* Message body
* Attachments
* Timestamps
* Conversation threading information
* Message headers

---

## Enterprise Search

Powered by Apache Solr.

Capabilities include:

* Full-text search
* Faceted search
* Sender/recipient filtering
* Date range filtering
* Attachment filtering
* Conversation search
* Thread reconstruction
* Near real-time indexing

Designed to scale from thousands to millions of messages.

---

## AI Investigation Engine

Natural language investigation powered by LLMs.

Examples:

### Approval Discovery

> Show me emails where Bob approved the budget.

### Timeline Reconstruction

> Build a timeline of discussions related to the outage.

### Knowledge Analysis

> Who knew about the outage before it happened?

### Risk Detection

> Find emails discussing project delays that were not reported to management.

### Executive Summaries

> Summarize the major concerns raised during the migration project.

---

## Explainable AI Results

Every AI-generated conclusion is backed by source evidence.

The system provides:

* Source email citations
* Direct links to messages
* Supporting excerpts
* Confidence scoring
* Investigation traceability

Users can always verify why a conclusion was generated.

---

## Relationship Analysis

Automatically builds relationships between:

* People
* Email addresses
* Teams
* Topics
* Projects
* Attachments

Provides visualizations such as:

* Communication networks
* Topic clusters
* Organizational interactions
* Timeline views

---

## Investigation Workspace

Investigators can:

* Save searches
* Create cases
* Bookmark evidence
* Build timelines
* Generate reports
* Export findings

---

# Architecture

```text
                     ┌──────────────────┐
                     │ PST / MBOX / EML │
                     └─────────┬────────┘
                               │
                               ▼
                   ┌─────────────────────┐
                   │ Email Ingestion     │
                   │ & Extraction Engine │
                   └─────────┬───────────┘
                             │
           ┌─────────────────┴─────────────────┐
           ▼                                   ▼

 ┌─────────────────┐                 ┌─────────────────┐
 │ PostgreSQL      │                 │ Apache Solr     │
 │ Metadata Store  │                 │ Search Index    │
 └────────┬────────┘                 └────────┬────────┘
          │                                   │
          └──────────────┬────────────────────┘
                         ▼

               ┌──────────────────┐
               │ RAG Pipeline     │
               │ Retrieval Layer  │
               └────────┬─────────┘
                        ▼

               ┌──────────────────┐
               │ OpenAI / Claude  │
               │ Analysis Engine  │
               └────────┬─────────┘
                        ▼

               ┌──────────────────┐
               │ Investigator UI  │
               └──────────────────┘
```

---

# Technology Stack

## Backend

* Python
* FastAPI
* PostgreSQL
* Apache Solr
* Celery

## AI

* OpenAI GPT Models
* Anthropic Claude
* Retrieval-Augmented Generation (RAG)

## Data Processing

* Python Email Parser Libraries
* PST Extraction Tools
* OCR Support (planned)
* Attachment Processing

## Frontend

* React (planned)
* TailwindCSS
* REST API

## Deployment

* Docker
* Docker Compose
* Linux

---

# Example Investigation Workflow

## Step 1

Import an email archive:

```text
CompanyArchive.pst
```

## Step 2

System extracts:

```text
2.4 million messages
150,000 attachments
8 years of communication history
```

## Step 3

Investigator asks:

```text
Who knew about the outage before it happened?
```

## Step 4

RAG pipeline retrieves relevant emails.

## Step 5

AI analyzes:

* Conversations
* Timelines
* Participants
* Approval chains

## Step 6

System returns:

```text
The outage was discussed by:

• Bob Smith
• Jane Doe
• Mike Johnson

Evidence indicates they were aware
approximately 18 hours before the outage.

Supporting Emails:
- Email #1
- Email #2
- Email #3
```

---

# Future Enhancements

## Graph Analysis

Knowledge graph of:

* People
* Topics
* Projects
* Events

Enable advanced questions such as:

> Who was most connected to the project delay discussions?

---

## Attachment Intelligence

Analyze:

* PDFs
* Word Documents
* Spreadsheets
* Presentations

Include attachment content in AI investigations.

---

## Sentiment Analysis

Identify:

* Escalations
* Concerns
* Frustration
* Risk indicators

---

## Compliance & eDiscovery Features

* Legal Hold
* Case Management
* Audit Logs
* Export Packages
* Chain of Custody Tracking

---

# Why This Project Matters

This project demonstrates:

* Enterprise search architecture
* Large-scale data ingestion
* AI-assisted investigation workflows
* Retrieval-Augmented Generation (RAG)
* Solr search engineering
* PostgreSQL data modeling
* eDiscovery concepts
* Compliance-oriented system design
* Explainable AI techniques

It combines traditional enterprise software engineering with modern AI capabilities to solve real-world investigation and compliance challenges.

---

# License

MIT License

---

# Disclaimer

This project is intended for educational, research, and legitimate investigative purposes. Users are responsible for ensuring compliance with all applicable privacy, legal, and regulatory requirements when processing email data.

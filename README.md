# Guest Insights — Restaurant Sentiment Analyzer (from-scratch model)

Turn raw guest reviews into clear, actionable insights.  
Upload a CSV → the app predicts **Positive / Neutral / Negative** → see **KPIs**, **trend over time**, and **Top Mentions** (keyphrases) with a **Positive / Negative / Both** toggle → drill down in a **Review Explorer** table → export filtered results.

> **AI requirement:** The sentiment model is **built and trained from scratch** (no pre-trained or fine-tuned checkpoints).

---

## Table of Contents
- [Goals](#goals)
- [High-Level Flow](#high-level-flow)
- [Feature Summary](#feature-summary)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Data & File Formats](#data--file-formats)
- [Model (from scratch)](#model-from-scratch)
- [Backend API](#backend-api)
- [Database Schema](#database-schema)
- [Keyphrase Mining (Top Mentions)](#keyphrase-mining-top-mentions)
- [Frontend Pages & State](#frontend-pages--state)
- [Setup & Run (Dev)](#setup--run-dev)
- [Evaluation Plan](#evaluation-plan)
- [Quality / Robustness](#quality--robustness)
- [Roadmap](#roadmap)
- [Demo Script](#demo-script)

---

## Goals
1. **Build a small neural sentiment model from scratch** for 3-way classification: `pos / neu / neg`.
2. **Provide a web application** that:
   - Ingests a CSV of reviews
   - Runs the model to assign labels
   - Summarizes results (KPIs, trend)
   - Surfaces **Top Mentions** with a polarity toggle
   - Allows drill-down and **CSV export** of the current view
3. Keep the system **simple, reliable, and private**.

---

## High-Level Flow

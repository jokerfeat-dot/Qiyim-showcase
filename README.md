# Qiyim: AI-Powered Fashion Marketplace

**Qiyim is a fashion marketplace for Kyrgyzstan. Sellers can generate catalog photos with virtual try-on, translate listings and get AI summaries of their sales.**

[Visit the marketplace](https://qiyim.kg/)

| Project | Details |
| --- | --- |
| **Status** | Public web storefront with Android and iOS builds |
| **My role** | Built the storefront, mobile app, backend functions and AI integrations, and tested releases |
| **Stack** | React, Vite, TypeScript, Expo / React Native, Supabase Edge Functions, PostgreSQL |
| **AI** | OpenAI Responses API, fal.ai FLUX Virtual Try-On |

![Qiyim's desktop catalog with a search field, category filters, and four product cards](images/catalog-desktop.png)

## What it does

Shoppers search local stores' catalogs, filter clothing by category and compare products priced in Kyrgyz som. Sellers prepare listings, translate product copy and submit items for review.

## AI features I built

| Feature | How it works | Why it's built this way |
| --- | --- | --- |
| **Virtual try-on for catalog photos** | The seller picks a garment photo and a model. A Supabase function validates the request, submits it to fal.ai's FLUX Virtual Try-On queue and records the job ID so the seller can fetch the result. | The generated image stays private until the seller chooses to submit it for review. |
| **Product translation** | The OpenAI Responses API translates product titles and descriptions. | Sellers can review the generated copy before publishing. |
| **Sales analysis** | The backend calculates delivered revenue, average order value and sales by product, then asks the model to summarize those figures. | The summary starts from the seller's recorded order totals, which provide a reference for checking the generated text. |

## How I evaluated the AI output

For a windbreaker, I compared generated photos with the original garment and checked the collar, front placket and pockets. I **rejected a FASHN v1.6 sample because it altered those details**. A convincing fashion photo still has to show the item the shopper will actually receive.

## Quality

At the September 13, 2026 release check, **304 tests passed** in the root project and **36 in the mobile project**. The Android, iOS and web exports also completed.

<img src="images/storefront-mobile.png" width="310" alt="Qiyim mobile storefront with product search and clothing categories above the women's collection">

## Skills demonstrated

LLM integration · generative image pipelines · model evaluation · TypeScript · React / React Native · serverless functions · PostgreSQL · automated testing

> This repository is a public showcase. The production source code is private.

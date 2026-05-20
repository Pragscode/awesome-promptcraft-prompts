# Digital Portfolio Structure — PromptCraft Prompt

## Prompt (PromptCraft Structured)

Role:
You are a Digital Portfolio Designer and UX strategist with experience building high-conversion, accessible, and SEO-optimized personal portfolio sites for creative professionals.

Task:
Design a comprehensive, visually appealing, and effective online portfolio structure for a creative professional that includes at least eight essential pages and optimized for user experience, accessibility, mobile responsiveness, and SEO.

Context:
- Audience: creative professionals (designers, photographers, illustrators, product designers)
- Goals: showcase work, generate client leads, establish authority, enable downloads and contact
- Constraints: include a minimum of 8 essential pages, consider UX and accessibility, provide a step-by-step guide with detailed page descriptions
- Outputs expected: a step-by-step site structure guide with page-level components, SEO notes, accessibility and mobile considerations, sample content outlines, and suggested assets/components

Style:
Creative, innovative, clear, and prescriptive. Use concrete examples and component-level suggestions.

Constraints:
- Must include at least the following pages: Home, About, Work, Services, Blog, Contact, Testimonials, Resume
- Each page must include: purpose, key sections/components, suggested content, SEO/meta recommendations, accessibility considerations, mobile layout notes, and CTAs
- Provide global navigation, footer, site-wide components, design tokens, and content governance guidance
- Output should be a step-by-step guide suitable for developers, designers, and content creators to implement

Output Format:
A numbered, step-by-step guide. For each of the 8 required pages, include: (a) Purpose, (b) Key Sections and Components, (c) Suggested Content / Microcopy, (d) SEO Meta (title, description, keywords), (e) Accessibility Checklist, (f) Mobile Layout Notes, and (g) Primary CTA.

---

## Expected AI Output: Step-by-Step Guide — Digital Portfolio Structure

1) Global Structure & Navigation

Purpose:
Provide a concise roadmap for the site, ensure clear information architecture and discoverability.

Key Components:
- Top navigation: Home, Work, Services, About, Blog, Testimonials, Resume, Contact.
- Sticky header with condensed nav on scroll.
- Footer with contact, social links, newsletter signup, and legal links (privacy, accessibility statement).
- Utility links: language selector, theme toggle (light/dark), search.

SEO & Accessibility:
- Use semantic HTML (`<nav>`, `<header>`, `<main>`, `<footer>`).
- Ensure keyboard navigability and skip-links.
- Structured data: `Person` schema, `WebSite` and `BreadcrumbList`.

Mobile Notes:
- Collapsible hamburger menu, accessible focus trap for mobile nav.

2) Page: Home

Purpose:
Introduce the portfolio owner, showcase unique value proposition, surface key work, and direct visitors to contact or hire.

Key Sections and Components:
- Hero: strong headline, 1-2 sentence value proposition, portrait or hero image/video, primary CTA (View Work / Hire Me).
- Featured Projects carousel or grid (3 best projects with visual thumbnails and brief tags).
- Quick stats / credibility bar (years, clients, awards) — optional micro-interactions.
- Services summary (3-4 core offerings with links to Services page).
- Recent posts (2 latest blog items) and Testimonials snippet.
- Footer CTA: Contact and newsletter.

Suggested Content / Microcopy:
- Headline example: "Product Designer crafting intuitive B2B experiences — I help teams ship clarity-built interfaces." 
- Subheadline: benefits-focused one-liner.

SEO Meta:
- Title: "[Name] — Product & UX Designer | Portfolio"
- Description: "Portfolio of [Name], a product designer specializing in B2B UX, case studies, services, and contact information."
- Keywords: product design portfolio, UX designer, [city] designer

Accessibility Checklist:
- Alt text for hero image and project thumbnails.
- High contrast CTAs and readable font sizes (>=16px body).
- Focus-visible styles for keyboard users.

Mobile Layout Notes:
- Stacked hero with CTA, swipeable project carousel, condensed stats.

Primary CTA:
- "View Work" (primary) and "Contact" (secondary)

3) Page: About

Purpose:
Tell the story, showcase skills, process, and humanize the owner to build trust.

Key Sections and Components:
- Extended bio / narrative (who you are, approach, values).
- Skill matrix: technical skills, tools, competencies (visual icons).
- Process section: how you work (discovery, design, delivery) with brief timeline visuals.
- Trust signals: logos, awards, press.
- CTA: "Work with me" or link to Services/Contact.

Suggested Content:
- Narrative tone: first-person, concise, authenticity-focused.
- Include a download link for the resume (PDF) with accessible label.

SEO Meta:
- Title: "About — [Name] | Designer & Creative"
- Description: "About [Name]: design philosophy, experience, skills, and client work. Available for freelance and contract work."

Accessibility:
- Semantic headings, captioned images of accolades, ensure downloadable resume is accessible (tagged PDF recommended).

Mobile Notes:
- Collapse long bios with "Read more" toggles; keep skill badges in horizontally scrollable chips.

Primary CTA:
- "Get in touch" (links to Contact)

4) Page: Work (Portfolio)

Purpose:
Showcase curated projects with compelling case studies demonstrating process, impact, and outcomes.

Key Sections and Components:
- Overview / filter bar (case study categories, tags, tech, type)
- Project cards grid with thumbnail, title, role, and short blurb.
- Case study template page per project:
  - Project summary & hero image
  - Problem & goals
  - Role & team
  - Process (research, ideation, iterations) with artifacts (screens, prototypes)
  - Solution & outcomes (metrics, before/after)
  - Learnings and next steps
  - Links to live site or prototype, and downloadable assets

Suggested Content:
- Prioritize 6–12 detailed case studies; highlight measurable impact (e.g., conversion +18%).
- Use narrative storytelling with data points.

SEO Meta:
- Title: "Work — [Name] Portfolio"
- Description: "Case studies by [Name] showcasing UX and product design projects, process, and results."
- Use `og:image` per project for social sharing.

Accessibility:
- Provide full image descriptions for design artifacts; include transcripts for video walkthroughs.

Mobile Notes:
- List view fallback for cards; ensure images scale and maintain legibility.

Primary CTA:
- "Discuss this project" (opens Contact with pre-filled subject)

5) Page: Services

Purpose:
Describe offerings, packages, and ways clients can engage.

Key Sections and Components:
- Services overview with short descriptions: e.g., Product Design, UX Research, Design Systems, Visual Design, Workshops.
- Pricing models or engagement examples (project-based, retainers) — optionally range-based to avoid sticker shock.
- Process and deliverables per service (what clients can expect).
- FAQs addressing scope, timelines, and payment terms.
- CTA: "Request a proposal" or "Book discovery call".

Suggested Content:
- Clear value statements and deliverables, sample timelines.

SEO Meta:
- Title: "Services — [Name] | Product Design & UX"
- Description: "Services offered by [Name], including product design, UX research, and design systems."

Accessibility:
- Accessible tables for pricing (if used), clear form labels.

Mobile Notes:
- Accordion for service details to reduce scrolling.

Primary CTA:
- "Request a proposal"

6) Page: Blog

Purpose:
Establish thought leadership, improve SEO, and provide content for sharing and discovery.

Key Sections and Components:
- Blog index with categories and featured posts
- Individual article template: hero, TL;DR, body, in-article CTAs, author bio, related posts
- Newsletter subscription prompt

Suggested Content:
- Publish 1–4 long-form articles per month focused on case studies, process insights, and industry commentary.
- Include how-to pieces and design explainers that target long-tail keywords.

SEO Meta:
- Title: "Blog — [Name] | Design & UX Insights"
- Description: "Articles and insights by [Name] on product design, UX, and design process."

Accessibility:
- Use semantic article markup, headings hierarchy, and accessible code blocks if including snippets.

Mobile Notes:
- Large readable typography, in-article sticky share buttons.

Primary CTA:
- "Subscribe" (newsletter)

7) Page: Testimonials

Purpose:
Provide social proof and credibility to potential clients.

Key Sections and Components:
- Curated testimonials with client logos, role, quote, and link to case study where applicable.
- Video testimonials or audio snippets (transcribed).
- Rotator or mosaic of client logos.

Suggested Content:
- Use full-name, role, company, and link to project where possible for authenticity.

SEO Meta:
- Title: "Testimonials — [Name] | Client Reviews"
- Description: "Client testimonials for [Name], showcasing client satisfaction and project impact."

Accessibility:
- Provide text transcripts for video or audio testimonials; ensure quotes are accessible to screen readers.

Mobile Notes:
- Vertical stack of testimonials with touch-friendly navigation; avoid tiny carousels.

Primary CTA:
- "Hire me" or "Request a case study"

8) Page: Resume

Purpose:
Provide an at-a-glance professional summary and a downloadable resume for hiring managers and clients.

Key Sections and Components:
- Summary headline and top skills
- Work history (roles, companies, dates) with concise bullets
- Education, certifications, and notable achievements
- Downloadable PDF (tagged, accessible) and link to LinkedIn

Suggested Content:
- Keep web resume scannable; link to case studies for proof.

SEO Meta:
- Title: "Resume — [Name] | Product Designer"
- Description: "Downloadable resume and professional summary for [Name], available for hire."

Accessibility:
- Ensure PDF is tagged and screen-reader friendly; provide text alternative on page.

Mobile Notes:
- Condensed timeline and collapsible sections for detailed experience.

Primary CTA:
- "Download resume" and "Contact"

9) Secondary Pages & Utilities

- Contact Confirmation / Thank You page
- Privacy & Accessibility statements
- Case study templates and CMS editor guides
- Media kit / Press page
- Landing pages for specific services or speaking engagements

10) Visual System & Component Library

Design Tokens:
- Primary/secondary/neutral color palette with contrast-safe variants
- Type scale (H1–H6, body, small) with responsive steps
- Spacing scale and component breakpoints

Components:
- Buttons (primary/secondary/ghost) with accessible states
- Cards, modals, accordions, form elements with clear labels
- Project gallery with lightbox and captions

11) Accessibility & SEO Checklist (site-wide)

Accessibility:
- Semantic HTML and ARIA where necessary
- Keyboard operability and focus order
- Color contrast >=4.5:1 for normal text
- Captions/transcripts for media
- Skip links and landmarks

SEO:
- Unique title & meta description per page
- Use of `og:` tags and `twitter:` metadata
- Descriptive URLs (e.g., `/work/logo-redesign-case-study`)
- Sitemap.xml and robots.txt
- Structured data (`schema.org`): `Person`, `Article`, `Organization` (if freelance entity)

12) Content Governance & Maintenance

- CMS recommendations: headless CMS (Contentful, Sanity) or static site with Markdown (Gatsby, Next.js)
- Editorial calendar for blog and case study refreshes
- Asset management: optimized images, WebP fallback, responsive `srcset`
- Performance: lazy-load images, preconnect for fonts, and CDN for static assets

13) Implementation Roadmap (Step-by-step)

Step 1 — Discovery (1 week):
- Gather brand assets, priority projects, target audience, and goals.

Step 2 — Information Architecture & Wireframes (1 week):
- Sitemap, wireframes for key templates (home, case study, contact).

Step 3 — Design System & Visual Mockups (2 weeks):
- Design tokens, component library, and high-fidelity mockups for main templates.

Step 4 — Build (2–3 weeks):
- Implement components, pages, CMS integration, and responsive QA.

Step 5 — Content Population & SEO (1 week):
- Add case studies, blog posts, meta tags, and structured data.

Step 6 — Accessibility Review & Testing (1 week):
- WCAG checklist, keyboard testing, screen reader pass.

Step 7 — Launch & Monitor (ongoing):
- Analytics setup, performance monitoring, and content roadmap execution.

14) Sample Microcopy & CTAs

- Hero CTA: "View my work" / "Hire me"
- Project CTA: "See case study" / "Discuss project"
- Service CTA: "Request a proposal"
- Blog CTA: "Subscribe for insights"

---

## Usage Instructions

1. Copy the structured prompt (top section) into your LLM of choice and include any real context details (audience, hero project, CMS).
2. Request a page-by-page, component-level output and ask for JSON or Markdown if you need programmatic import into a CMS.
3. Use the implementation roadmap to schedule sprints and assign roles (designer, dev, content).

---

## Where to add this file

Category: `design/` — this prompt focuses on visual portfolio structure and UX.

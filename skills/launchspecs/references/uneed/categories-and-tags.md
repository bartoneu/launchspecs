# Uneed — categories and tags

Uneed uses two separate taxonomies on the editor's General tab. **Category** is single-select and high-level (5 options). **Tags** are multi-select and granular (185 options in a single global pool). Validated against the live editor on 2026-05-01.

## Categories (5 total, single-select)

Category is required and must be exactly one of:

1. **Development**
2. **Design**
3. **Business**
4. **Marketing**
5. **Personal Life**

Each category has its own listing page accessible from the site footer (`/development`, `/design`, `/business`, `/marketing`, `/personal-life`).

### Selection guidance

- Pick the category that describes the **primary user** of the product, not the product's underlying tech. A no-code site builder used by marketers belongs in Marketing, not Development.
- If the product spans two categories, pick the one with the audience most likely to vote on launch day. Uneed has no multi-category support.
- "Personal Life" is broader than it sounds — it covers fitness, journaling, habit-tracking, finance for individuals, hobby tools, and similar.

## Tags (185 total, multi-select, single global pool)

Tags are **not** gated by category — every tag is available to every product. The selector is searchable and alphabetical. At least one tag is required; the upper bound was not surfaced in the UI (likely soft).

### Full tag list (alphabetical)

```
3D
AB Testing
Accessibility
Advertising
Affiliation
Agile
AI
Analytics
Android
API & Data
Audio
Automation
Avatars
Backgrounds
Blogging
Boilerplate
Bookmarks
Books
Briefs
Browser Extensions
Browsers
Business
Calendar
Cars
Changelogs
Charts
Chat
Chatbots
CI CD
CMS
Coaching
Cold Emails
Colors
Communication
Community
Conversion
Cooking
Coworking
CRM
Crypto
Cryptography
CSS
Customer Service
Dashboards
Database
Demos
Design
Design System
Desktop Apps
Development
Directories
Discord
Documentation
Domains
E-Commerce
Ebook
Education
Email Provider
Emails
Engineering
Environment
Events
Excel
Feedback
Figma
File Sharing
Fitness
Food Menu
Forms
Forum
Freelance
Fun
Funding
Gaming
GDPR
Git
Gradients
Gumroad
Habits
Happiness
Health
Hiring
Hosting
Human Resources
Icons
Idea validation
Illustrations
Image Optimization
Indie Making
Influencers
Inspiration
Instagram
Interior Design
Invoicing
iOS
Jobs
Journaling
Kids
Knowledge Bases
Lead Acquisition
Learning
Legal
Lifestyle
Linkedin
Logos
MacOS
Markdown
Meetings
Moderation
Money
Monitoring
Motion & Animation
Music
News
Newsletter
Next.js
No-code
Note-taking
Notion
Onboarding
Open Source
Partnerships
Password Manager
Personal assistant
Personal Finances
Pets
Photography
Pitch Decks
Podcasts
Privacy
Productivity
Project Management
Prototyping
Python
Raspberry
Reddit
Reports
Research
Resume
Roadmap
Scrapping
Screen Recording
Screenshots
Search Engine
Security
SEO
Shopify
Shortlinks
Slack
Smartphones
Social Media
Software
Sports
SQL
Stats
Support
Surveys
SVG
Tailwindcss
Teaching
Templates
Terminal
Testimonials
Testing
Ticketing
Time Tracking
To-do lists
Tracking
Translations
Traveling
Twitter
Typography
UI Kit
Upscaling
Uptime
User Management
Video
Virtual office
VSCode
Waitlists
Wallpapers
Web3
Webflow
Website Builders
Writing
```

185 tags total. Compiled from the live editor's tag selector on 2026-05-01.

### Tag selection guidance

- **Pick 3–5 tightly relevant tags.** No upper limit was enforced in the UI, but stuffing tags hurts both the product page (looks spammy) and the discovery surfaces (shows up on `/best/<tag>` pages where it doesn't belong).
- **One tag should match the technology stack** if relevant (Next.js, Python, No-code, etc.) — these tag pages have engaged technical audiences.
- **One tag should match the use case** (CRM, SEO, Newsletter, Project Management, etc.).
- **Use specific tags before broad ones.** "Cold Emails" is more useful than "Emails"; "Pitch Decks" beats "Templates".
- **Avoid mismatches with the chosen Category.** A product tagged "Notion" + "Knowledge Bases" + "Productivity" but Categorized as "Business" feels off — either the tags or the category should align with where the audience lives.

## Sources

- [Live editor tag selector](https://www.uneed.best/edit/waiting-line/) (requires authenticated session)
- [Category listing pages](https://www.uneed.best/development) (and `/design`, `/business`, `/marketing`, `/personal-life`)

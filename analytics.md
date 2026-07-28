# Analytics

This site uses Google Analytics 4 through the Google tag in the site HTML pages.

## GA4 setup

- Property: `inbalgilead.com`
- Web stream: `Inbal Gilead Website`
- Website URL: `https://inbalgilead.com`
- Stream ID: `15202331490`
- Measurement ID: `G-G1TN1HCM82`

Enhanced measurement is enabled in GA4. It automatically tracks page views, scrolls, outbound clicks, and other standard web interactions.

## Custom event implementation

Custom click events are attached to links with `data-analytics-event`.

The shared listener sends:

- `event_name`: the value of `data-analytics-event`
- `link_text`: `data-analytics-label`, visible text, or `aria-label`
- `link_url`: the clicked link URL
- `section_name`: `data-analytics-section`, or the nearest `section` / `footer` id

## Events

| Event | Fires when | Current locations | Parameters |
| --- | --- | --- | --- |
| `section_view` | At least 25% of a section after the opening hero becomes visible, once per page load | About, Services, Workshops, Content, Contact | `section_name` |
| `contact_nav_click` | Visitor clicks `Contact` in the main navigation | Main navigation | `link_text`, `link_url`, `section_name` |
| `testimonial_navigation` | Visitor manually changes the visible testimonial | Services testimonials | `section_name`, `item_name` |
| `content_carousel_navigation` | Visitor uses an arrow in the Recent Content carousel | Recent Content | `section_name` |
| `work_with_me_click` | Visitor clicks the `Work With Me` CTA that downloads `One Pager.pdf` | Services CTA | `link_text`, `link_url`, `section_name` |
| `content_card_click` | Visitor clicks a Recent Content card | Medium article: `Retro is the stepson of planning`; YouTube talk: `HayaData 2025 Product Mindset Makes Good Analysts`; Medium article: `Product Mindset Makes Good Analysts` | `link_text`, `link_url`, `section_name` |
| `linkedin_click` | Visitor clicks the footer LinkedIn icon | Footer contact links | `link_text`, `link_url`, `section_name` |
| `email_click` | Visitor clicks the footer email icon | Footer contact links | `link_text`, `link_url`, `section_name` |
| `sessionize_click` | Visitor clicks the footer Sessionize icon | Footer contact links | `link_text`, `link_url`, `section_name` |
| `ai_adoption_one_pager_open` | Visitor lands on the tracked AI Adoption one pager URL before being sent to the PDF | `/ai-adoption-enablement/` | `link_url`, `section` |
| `ai_adoption_one_pager_legacy_pdf_open` | Visitor lands on the previously shared direct PDF URL before being sent to the PDF | `/ai-adoption-enablement.pdf` | `link_url`, `section` |
| `ai_adoption_one_pager_click` | Visitor clicks the fallback PDF link on the tracked AI Adoption one pager page | `/ai-adoption-enablement/` | `link_url`, `section` |

## Notes

- GA4 may take up to 48 hours to show new data in standard reports.
- Use Realtime reports or DebugView for quick checks after changes.
- The following event-scoped custom dimensions are registered in GA4: `section_name` as `Section name`, `item_name` as `Item name`, and `link_text` as `Link text`.
- The following events are configured as key events with no default monetary value and a counting method of once per session: `work_with_me_click`, `email_click`, and `ai_adoption_one_pager_open`.
- For source tracking, prefer UTM links where the site URL is shared from controlled surfaces such as LinkedIn, email signatures, newsletters, or speaker profiles.
- Direct PDF files do not run Google Analytics. Use `https://inbalgilead.com/ai-adoption-enablement/` for new shares.
- The previously shared `https://inbalgilead.com/ai-adoption-enablement.pdf` URL now resolves through a tracked page before opening the PDF.
- The actual PDF file is stored at `https://inbalgilead.com/one-pagers/ai-adoption-enablement.pdf`.

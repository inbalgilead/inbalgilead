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
- `section`: `data-analytics-section`, or the nearest `section` / `footer` id

## Events

| Event | Fires when | Current locations | Parameters |
| --- | --- | --- | --- |
| `work_with_me_click` | Visitor clicks the `Work With Me` CTA that downloads `One Pager.pdf` | Services CTA | `link_text`, `link_url`, `section` |
| `content_card_click` | Visitor clicks a Recent Content card | Medium article: `Retro is the stepson of planning`; YouTube talk: `HayaData 2025 Product Mindset Makes Good Analysts`; Medium article: `Product Mindset Makes Good Analysts` | `link_text`, `link_url`, `section` |
| `linkedin_click` | Visitor clicks the footer LinkedIn icon | Footer contact links | `link_text`, `link_url`, `section` |
| `email_click` | Visitor clicks the footer email icon | Footer contact links | `link_text`, `link_url`, `section` |
| `sessionize_click` | Visitor clicks the footer Sessionize icon | Footer contact links | `link_text`, `link_url`, `section` |

## Notes

- GA4 may take up to 48 hours to show new data in standard reports.
- Use Realtime reports or DebugView for quick checks after changes.
- For source tracking, prefer UTM links where the site URL is shared from controlled surfaces such as LinkedIn, email signatures, newsletters, or speaker profiles.

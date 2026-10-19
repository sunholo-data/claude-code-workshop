# Website tagging plan (practice copy)

A made-up plan for a made-up online shop, used for workshop exercises. Nothing here describes a
real site.

**Owner:** the web team · **Last reviewed:** 1 Sept 2026

## Events

| Event | Fires when | Parameters | Status |
|---|---|---|---|
| `page_view` | Any page loads | `page_title`, `page_location` | Live |
| `view_item` | A product page loads | `item_id`, `item_category` | Live |
| `add_to_cart` | The basket button is clicked | `item_id`, `quantity`, `value` | Live |
| `begin_checkout` | The checkout page loads | `value`, `items` | Live |
| `purchase` | The order confirmation page loads | `transaction_id`, `value`, `items` | Live |
| `newsletter_signup` | The footer form is submitted | `form_location` | Live until 14 Sept, then renamed |
| `sign_up` | Replaces `newsletter_signup` from 15 Sept | `method` | Live from 15 Sept |
| `search` | The site search is used | `search_term` | Planned |

## Change log

- **15 Sept 2026** — `newsletter_signup` renamed to `sign_up` to match the recommended event
  names. Reports that filter on the old name will show zero from this date.
- **2 Sept 2026** — `add_to_cart` now sends `value`.

## Open questions

- Should `search_term` be recorded at all, given people sometimes type email addresses into
  search boxes?
- Who signs off a new event before it goes live?

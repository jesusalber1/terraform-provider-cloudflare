---
page_title: "cloudflare_turnstile_widget Resource - Cloudflare"
subcategory: ""
description: |-
  The Turnstile Widget https://developers.cloudflare.com/turnstile/ resource allows you to manage Cloudflare Turnstile Widgets.
---

# cloudflare_turnstile_widget (Resource)

The [Turnstile Widget](https://developers.cloudflare.com/turnstile/) resource allows you to manage Cloudflare Turnstile Widgets.

## Example Usage

```terraform
resource "cloudflare_turnstile_widget" "example" {
  account_id     = "f037e56e89293a057740de681ac9abbe"
  name           = "example widget"
  bot_fight_mode = false
  domains        = ["example.com"]
  mode           = "invisible"
  region         = "world"
}
```
<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `account_id` (String) The account identifier to target for the resource.
- `domains` (Set of String) Domains where the widget is deployed
- `mode` (String) Widget Mode
- `name` (String) Human readable widget name.

### Optional

- `bot_fight_mode` (Boolean) If bot_fight_mode is set to true, Cloudflare issues computationally expensive challenges in response to malicious bots (Enterprise only).
- `id` (String) The identifier of this resource. This is the site key value.
- `offlabel` (Boolean) Do not show any Cloudflare branding on the widget (Enterprise only).
- `region` (String) Region where this widget can be used.

### Read-Only

- `secret` (String, Sensitive) Secret key for this widget.

## Import

Import is supported using the following syntax:

```shell
$ terraform import cloudflare_turnstile_widget.example <account_id>/<site_key>
```
---
title: Ask AI Testing
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
<HTMLBlock>{`
<style></style>
`}</HTMLBlock>

<br />

*How do I direct shoppers to nearby dealers with product?**

Specific Store and Product

1. Open the Product Locator modal on the product page you want to send.
2. Select the store.
3. Click save for later and copy the link. This link will direct you back to the exact view of the product locator for this store.

<Image align="center" src="https://files.readme.io/a465dceb670c7e930ac3bd1e8de584ce1bf7cc76d473f29b61b1a589ce4a0fb0-Screenshot_2026-06-01_at_10.18.49_AM.png" />

![Create Cart Shopping Links](https://storage.googleapis.com/lcly-docs-legacy/r5.avif)

![Create Cart Shopping Links](https://storage.googleapis.com/lcly-docs-legacy/r6.avif)

# Several Stores and One Product

Follow the steps above.

Once you have the link from the Product Locator modal, remove the store ID parameter from the URL. Remove the `&__lcly_sfl_store_id=____` parameter — the store-ID portion of this URL:

`https://www.locally.com/headless/sfl/url/redirect?__lcly_sfl_store_id=285141&__lcly_sfl_product_id=ABC123&__lcly_sfl_upc=123456789101&__lcly_sfl_style=ABC12345&__lcly_sfl_redirect_url=https://www.yourbrandsite.com/productpage`

## Build the Link From Scratch

Here is the template link:

`https://www.locally.com/headless/sfl/url/redirect?__lcly_sfl_store_id=285141&__lcly_sfl_product_id=ABC123&__lcly_sfl_upc=123456789101&__lcly_sfl_style=ABC12345&__lcly_sfl_redirect_url=https://www.yourbrandsite.com/productpage`

* Enter the **Store ID** where it says `__lcly_sfl_store_id=285141`. If you do not want the store-specific link, remove `__lcly_sfl_store_id=285141&` from the URL.
* Enter the **product ID** where it says `__lcly_sfl_product_id=ABC123`
* Enter the **UPC** where it says `__lcly_sfl_upc=123456789101`
* Enter the **style number** where it says `__lcly_sfl_style=ABC12345`
* Enter the URL you want the modal to load where you see `__lcly_sfl_redirect_url=https://www.yourbrandsite.com/productpage`
* <br />

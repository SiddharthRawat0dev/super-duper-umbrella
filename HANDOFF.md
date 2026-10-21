# i&Beyond storefront design — real catalogue edition

## Run
Open index.html from the handover ZIP in a browser, or serve its folder with any static server. No build or installation required. The source project uses dist/ as its public folder. Relative asset paths support GitHub Pages subdirectories.

## What is included
The actual customer-facing catalogue retrieved from https://iandbeyond.com/api/public/itm on 21 October 2026: 1,591 listings with original IDs, names, descriptions, sale prices, categories, stock/status fields, images and product variants. Category hierarchy comes from /api/public/itm/categories. No invented product listings or prices. Customer-facing fields only are exported. Catalogue data is in catalogue.js. The catalogue is a snapshot; it is not live stock.

Original public website images are reused. Product photography is used in every product card where the source supplies a photo. No generated or CSS-drawn product illustrations. Main catalogue photos are included locally where downloading succeeded. Additional gallery image URLs point to the source website where not bundled. Products without source photos explicitly state that no photo was supplied.

The design includes the catalogue with search, condition/category filters, sorting and pagination; product details, image galleries and real variant selection; a preview bag; pre-owned/consignment/recycling; repairs; mobile top-ups, bill payment, flight tickets and printing/scanning; workspace offers; store address, hours and phone.

## Brand lock
Preserve the existing live iandbeyond.com wordmark unchanged: literal text i&Beyond; system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif; 1.4rem; weight 700; #3d5a3d; tracking -.02em; line-height 1.6. Do not add a dot, restyle the ampersand, or substitute Power Studio branding. Main colours are based on the original site: #3d5a3d, #2d3a2d, #d8e2d8 and #f5f7f4.

## Instructions for the existing project's AI
Apply this visual design to the existing application. First inspect its framework, routes, catalogue and order interfaces. Preserve the admin panel, authentication, database, product IDs, existing product variants, stock validation and ordering logic. Map catalogue.js fields back to the existing product data instead of creating a second inventory. Keep the existing product routes /shop/item/:id; the prototype displays details in a dialog, which may be adapted to the existing page route.

Use the real catalogue response on the original same-origin site after integration. The public read paths were observed in the existing frontend. No API key is needed for this static design. Do not expose private credentials or include internal inventory/accounting fields.

The preview bag stores items in browser memory only and never reserves stock or creates orders. Connect it to the existing cart/order flow and validate quantities and variant availability before enabling real ordering. Pickup is standard. Delivery is arranged by contacting the store; do not introduce shipping checkout.

The original frontend submits orders to /api/public/orders. This design deliberately makes no requests to that endpoint. Reuse the existing submission implementation and its validations after reviewing the current code; do not infer or invent its contract from this prototype.

Keep responsive layout, keyboard focus, dialog close/Escape, reduced-motion support, empty search state, real product options and safe text escaping. After integration test the catalogue, filtering across category descendants, search, pagination, sort, gallery, variants, cart, pickup, stock validation and orders alongside the existing admin flow. Confirm business terms, store hours, workspace pricing and contact details before public launch. Remove preview notices only after live integration is complete and reviewed.

## Latest design revision
Homepage uses a real Anker Soundcore Space One product photo as the hero. Four featured products precede an expandable full catalogue, keeping the homepage concise. Shop links expand the catalogue. Preserve that behavior when porting to a separate shop route. The store-front photograph is no longer used. The location section uses the supplied Google Maps image, assets/store-location-map.png, and opens a real Google Maps search/directions destination for i&Beyond at 16 Georgiou A. Keep the image's labels intact; replace it with an official live Maps embed if desired during integration.

## Dedicated shop revision
Shop is now a separate shop.html page with shop.js. All homepage shop entry points navigate there. The homepage contains no full catalogue. The shop page contains no promotional, repairs, workspace or map sections, only header/navigation, catalogue, sidebar and a small footer. Category branches expand independently and include descendant products when selected. Sidebar condition and availability filters combine with search and sorting. Active filters can be removed individually or reset together. On narrow screens the sidebar becomes a filter drawer with Escape/close/backdrop and keyboard focus handling. Query parameters preserve category, condition and search. The preview bag is shared across homepage/shop in sessionStorage; no orders or stock reservations are created. Port these to the existing project's shop route, catalogue and cart integrations.

## GitHub upload edition
This package loads all product photos from the original public iandbeyond.com URLs to stay below the browser upload file-count limit. The catalogue and complete front-end source are included.

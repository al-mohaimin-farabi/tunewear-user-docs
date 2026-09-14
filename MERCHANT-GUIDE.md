# Running TuneWear — the admin guide

For whoever runs the shop day to day. Every screenshot was taken on the
real admin (staging, September 2026). The gold rings and numbers show what
to click, in order. Nothing here needs a terminal, code or a deploy: every
change reaches the website by itself, most within seconds.

**How each section is laid out:** _when_ you would use it, _what_ it does,
_who_ may use it, then the clicks, with a worked example.

## Contents

0. Getting started — the two admins, logging in, the sidebar
1. Products — adding one, sizes and colours, photos, price, the extras
2. Categories — the tiles on /men and /women
3. Prices and sales — the base price, price lists, Publish changes
4. Discount codes and offers (promotions)
5. Delivery charges
6. Stock
7. Orders — from the website, and DM orders you type in
8. Customers and password resets
9. Shop claims — what the site says about the business
10. Sales channels
11. The website's words and photos (Payload)
12. Staff and roles
13. Store settings
14. Analytics, and visitor numbers in Umami
15. Glossary

---

## 0. Getting started

### The two admins

The shop has **two separate admin panels**, each with its own address and
login. Nothing in one links to the other.

| Admin       | Address                                     | Holds                                                         |
| ----------- | ------------------------------------------- | ------------------------------------------------------------- |
| **Medusa**  | `https://tunewear-admin.<domain>/greenroom` | Products, categories, prices, stock, orders, customers, staff |
| **Payload** | `https://tunewear.<domain>/admin`           | The words and photos on the pages: home, about, footer, FAQ…  |
| **Umami**   | `https://tunewear-analytics.<domain>`       | Visitor numbers (chapter 14)                                  |

> The Medusa address ends in **`/greenroom`**, not `/app`. `/app` shows a
> "not found" page.

![Medusa login](assets/merchant-guide/00-login-medusa.webp)

![Payload login](assets/merchant-guide/00-login-payload.webp)

### The sidebar

![The Medusa sidebar](assets/merchant-guide/00-sidebar.webp)

What you see depends on your role (chapter 12). A Staff login, for
example, has no Price Lists, Promotions or Analytics. Two useful pages
have **no sidebar entry** and are reached by address: **Draft orders**
(`/greenroom/draft-orders`, chapter 7) and each product's page.

### Where each thing is edited

| I want to change…                                           | Admin   | Go to                                                      |
| ----------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| A product, its sizes, colours, photos, price, stock         | Medusa  | **Products** (chapter 1)                                   |
| The category tiles on /men and /women                       | Medusa  | **Products → Categories** (chapter 2)                      |
| Sale prices                                                 | Medusa  | **Price Lists**, then **Publish changes** (chapter 3)      |
| Discount codes, free delivery offers                        | Medusa  | **Promotions** (chapter 4)                                 |
| Delivery charges (Inside / Outside Dhaka)                   | Medusa  | **Settings → Locations & Shipping** (chapter 5)            |
| Orders, DM orders                                           | Medusa  | **Orders**, **Draft orders** (chapter 7)                   |
| Home page hero, the Men/Women/Sale cards, section headings  | Payload | **Pages → Home**                                           |
| The Men or Women page's hero and text                       | Payload | **Pages → Men** / **Pages → Women**                        |
| Sale page (masthead, Mix & Match photo, offer strip)        | Payload | **Pages → Sale**                                           |
| About, Contact, FAQ, and pages you add (Shipping, Returns…) | Payload | **Pages → About, Contact, FAQ & more**                     |
| Footer, the trust strip, the scrolling marquee              | Payload | **Site content → Footer / Trust Bar / Announcement strip** |

---

## 1. Products

**When:** a new garment arrives, or one changes (new colour, new photo,
new price).\
**Who:** Staff and above can add and edit products. Changing a price is
also allowed for Staff; cost price is covered in 1.9.

### 1.1 The one idea everything depends on: options and variants

A product has **options** — here **Size**, and **Colour** if it comes in
more than one. Every combination of option values is a **variant**: the
thing a shopper actually buys, with its own stock count.

_Example:_ a T-shirt in Black and White, sizes S, M and L, has 2 × 3 = 6
variants: Black / S, Black / M, … White / L.

> **Decide the colours when you create the product.** Colours added later
> do not reach the sizes that already exist, and each size then has to be
> given its colour by hand (1.6). Name the option **Colour** (or Color);
> the shop looks for either.

A shop that lists each colour as **its own product** can do that too: name
them `Solid Summer T-Shirt - White`, `Solid Summer T-Shirt - Blue`, give
each a Colour option with its one colour, and the product page shows the
others under **Other colours** by itself (1.12).

**The colour dots — there is no switch.** The shop decides from how many
colours the product's Colour option has:

| Colours on the product                    | Card in the shop | Colour filter   | Product page                                   |
| ----------------------------------------- | ---------------- | --------------- | ---------------------------------------------- |
| **None** (only Size)                      | No dot           | Not listed      | No colour dots                                 |
| **One** (e.g. `White`)                    | One dot          | Under **White** | "Color: White" with its dot, nothing to click  |
| **Two or more** (e.g. Black, White, Navy) | A dot for each   | Under each      | Colour dots to click; photos follow the colour |

To get clickable dots, give the product a second colour. To remove them,
leave it one colour.

Two or more colours — `Everyday Crew Tee` in White, Navy and Black: the
dots to click (1), and the photos change to the colour picked (2). For
that, pick each photo's colour (1.10).

![Several colours: dots to click](assets/merchant-guide/01-46-colour-dots.webp)

One colour — `Polo Shirt - White`: the colour is named (1), nothing to
click. Its other colour, sold as its own product `Polo Shirt - Black`,
is one click away under **Other colours** (2; how, in 1.12).

![One colour: named, not a choice](assets/merchant-guide/01-45-one-colour-named.webp)

### 1.2 Create the product — details

Sidebar **Products** → **Create**.

![Products list, Create](assets/merchant-guide/01-01-products-create.webp)

Fill in **Title** (1), a one-line **Subtitle** (2), the **Description** (3)
and drop the photos into **Media** (4). Leave **Handle** empty: Medusa
makes the web address from the title.

![Details](assets/merchant-guide/01-02-details.webp)

### 1.3 Sizes (and colours)

Switch on **Yes, this is a product with variants**, then add an option.
Type the option name — **Size** — and the values: type one value, press
**Enter**, type the next. (The box says so: _Type a value, then press
Enter_.) Add **Colour** the same way if the garment has colours.

![Variants switch](assets/merchant-guide/01-03-variants-toggle.webp)

![Size option](assets/merchant-guide/01-04-option-size.webp)

![Size values](assets/merchant-guide/01-05-size-values.webp)

Medusa lists every combination. Leave them all ticked; an unticked row is
simply not created.

![Variant rows](assets/merchant-guide/01-06-variant-rows.webp)

### 1.4 Organize — Type decides /men or /women

**Type** is the aisle: `men` shows the product on /men, `women` on /women,
`unisex` on both. **Categories** puts it in a tile (chapter 2). **Tags**
are labels such as `new-arrival` or `featured`; type a new tag and choose
**Create "…"** to make one on the spot (1.11). Leave **Discountable** on
unless no discount should ever apply. **TuneWear Storefront** must stay
under Sales channels, or the product never appears on the website.

![Type](assets/merchant-guide/01-07-type.webp)

![Shipping profile](assets/merchant-guide/01-08-shipping-profile.webp)

![Organize done](assets/merchant-guide/01-09-organize-done.webp)

### 1.5 The variants grid — the ticks explained

The last step of the wizard is a grid with one row per size. The same three
switches appear when you add one size later (**Variants → Create**):

![Manage inventory starts on](assets/merchant-guide/01-10-variant-switches.webp)

![One price column, in Taka](assets/merchant-guide/01-10b-price-column.webp)

| Column                | Meaning                                                                                    | Leave it              |
| --------------------- | ------------------------------------------------------------------------------------------ | --------------------- |
| **Managed inventory** | The shop counts stock for this size and stops selling at zero.                             | **On** (it starts on) |
| **Allow backorder**   | Keep selling after stock reaches zero. Only for made-to-order pieces.                      | Off                   |
| **Has inventory kit** | This size is made of several stocked parts (a set sold as one). Not for normal garments.   | Off                   |
| **Price BDT**         | The price. You can leave it empty here and set it for every size at once afterwards (1.8). | —                     |

> The wizard **does not insist on a price**. A product without one cannot
> be bought; set it straight after (1.8).

**Save** (as draft) or **Publish**. A draft is invisible on the website.

![Created as draft](assets/merchant-guide/01-11-created-draft.webp)

### 1.6 Adding a colour afterwards

If the product was created with sizes only, add the colour under
**Options** (type it, press Enter), then give **each existing size** its
colour: in **Variants**, **⋯** → **Edit** → **Colour** → pick → **Save**.
A new colour also needs new sizes: **Variants → Create**, choose the size
and the colour, **Continue**, give it a price, **Save** — then add stock
(chapter 6). Sizes, then price, then stock: until all three exist the
colour shows on the website crossed out as sold out.

![Colour option](assets/merchant-guide/01-16-colour-option.webp)

![Colour value](assets/merchant-guide/01-17-colour-black.webp)

![The Colours box says the colour has no sizes yet](assets/merchant-guide/01-18-colour-missing.webp)

![Variant menu](assets/merchant-guide/01-19-variant-menu.webp)

![Edit variant](assets/merchant-guide/01-20-variant-edit-item.webp)

![Pick the colour](assets/merchant-guide/01-21-variant-colour.webp)

![Save](assets/merchant-guide/01-22-variant-save.webp)

![Colour set](assets/merchant-guide/01-23-colour-set.webp)

The **Add or rename a colourway** button in the Colours box opens the same
Options screen.

### 1.7 The colour swatch

The **Colours** box on the product page sets the dot shoppers tap. Pick the
colour or type its code (`#1a1a1a`) → **Save colours**.

![Swatch](assets/merchant-guide/01-24-swatch.webp)

![Swatch saved](assets/merchant-guide/01-25-swatch-saved.webp)

### 1.8 Price — one box for every size

The **Price** box sets one price for every size and colour: type it →
**Apply to all**. Sale prices are separate (chapter 3).

![Price](assets/merchant-guide/01-12-price.webp)

![Price saved](assets/merchant-guide/01-13-price-saved.webp)

### 1.9 Cost price (for profit in Analytics)

What the garment costs you, per piece. Never shown to shoppers; Analytics
uses it to show real profit. Leave it empty if you do not know it — empty
means "unknown", never zero.

![Cost](assets/merchant-guide/01-26-cost.webp)

![Cost saved](assets/merchant-guide/01-27-cost-saved.webp)

### 1.10 Photos and colours

The **Photographs & image SEO** box: for each photo, pick which colour it
shows (or **Shows every colour**). A shopper who picks that colour is taken
to that photo. The description underneath is read by screen readers and
Google Images; it is pre-written for you.

![Photo colour](assets/merchant-guide/01-28-photo-colour.webp)

![Photo colour saved](assets/merchant-guide/01-29-photo-colour-saved.webp)

### 1.11 Tags

**Organize** box → **⋯ → Edit** → **Tags**: pick an existing tag, or type a
new one and choose **Create "…"**. **Save.** (If the tag already exists,
Create is greyed out — pick it from the list.) Tags show as labels on the
product; `featured` also puts it on the home page's rail.

![Create a tag](assets/merchant-guide/01-41-tag-create.webp)

### 1.12 Complete the look, Other colours, You may also like

Three sections under the details on every product page.

- **Complete the look** — up to two pieces **you** choose. On the product's
  admin page, **Complete the look** box: type a name in the search box,
  click the product. It saves at once. **Remove** takes one off. With
  nothing picked, the section does not show.
- **Other colours** — turned on by the product names. Steps just below.
- **You may also like** — automatic. Same category, in stock, best seller
  first.

![Complete the look — admin](assets/merchant-guide/01-42-complete-the-look-admin.webp)

![Two pieces picked](assets/merchant-guide/01-42b-complete-the-look-picked.webp)

![On the website](assets/merchant-guide/01-43-complete-the-look-shop.webp)

#### Other colours, step by step

This is for a garment you list **as one product per colour**. There is no
switch to turn on: **the product names are the switch.**

1. Make each colour its own product (1.2), with its own sizes, stock and
   photos.
2. Give every one the **same garment name**, then a space, a dash, a space,
   and the colour:
   - `Solid Summer T-Shirt - Blue`
   - `Solid Summer T-Shirt - White`

   Any garment works the same way: `Polo Shirt - White`,
   `Polo Shirt - Black`.

3. **Give each one its colour** — one **Colour** option with **one**
   value, next to Size, when you create it (1.3): `Colour` → `Blue`. This
   is what puts the product under **Blue** in the shop's colour filter and
   the blue dot on its card. The product page names it — "Color: Blue"
   with its dot — but there is nothing to click: switching colour is what
   the tiles below are for.
4. In **Media**, put the photo you want on the small tile **first**. The
   tile shows each product's first photo.
5. Publish them. Within seconds every one of their pages shows all the
   colours, the one being looked at outlined in gold. Click a tile and the
   shopper is on that colour's page.

![Other colours](assets/merchant-guide/01-44-other-colours.webp)

Which names join the group:

| Title                          | Joins?                                  |
| ------------------------------ | --------------------------------------- |
| `Solid Summer T-Shirt - Green` | Yes                                     |
| `solid summer t-shirt - Green` | Yes — capital letters do not matter     |
| `Solid Summer T-Shirt Green`   | No — there is no dash                   |
| `Solid Summer T-Shirt-Green`   | No — the dash needs a space either side |
| `Solid Summer Tee - Green`     | No — the garment words are different    |

- **A new colour** joins by being named the same way. Nothing else to do.
- **To take a product out**, rename it so the garment words differ.
- **Sold out** — the colour stays, faded and crossed out, so shoppers see
  it exists.
- **Only one product with that name** — the section does not show.
- **Skipped step 3?** The tiles still work, using the colour from the name,
  but the product is missing from the colour filter.

> A garment sold as **one product with several colours** (1.1) shows them
> as colour dots beside the sizes instead. Use one way or the other for a
> garment, not both.

### 1.13 The rest of the product page's boxes

- **What this garment's page claims** — this product's own rating and
  customer count; empty uses the shop's (chapter 9).

  ![Claims](assets/merchant-guide/01-14-claims.webp)

  ![Claims saved](assets/merchant-guide/01-15-claims-saved.webp)

- **SEO** — the title and text Google and WhatsApp previews show. Leave
  empty to use the product's own.

  ![SEO](assets/merchant-guide/01-30-seo.webp)

- **Size chart** — comes from the category; pick another only for an
  exception.

  ![Size chart missing](assets/merchant-guide/01-31-size-chart-missing.webp)

  ![Size chart from the category](assets/merchant-guide/01-36-size-chart-inherited.webp)

- **Fit and weight** — the Fit and GSM rows under the description.

  ![Fit and weight](assets/merchant-guide/01-32-fit-weight.webp)

  ![Saved](assets/merchant-guide/01-33-fit-weight-saved.webp)

- **Material** — in the product's main edit form (**⋯ → Edit**).

  ![Edit menu](assets/merchant-guide/01-34-edit-menu.webp)

  ![Material](assets/merchant-guide/01-35-material.webp)

### 1.14 Publish

Top of the product: **⋯ → Edit** → **Status: Published** → **Save**. The
product is on the website within seconds.

![Status](assets/merchant-guide/01-37-publish-status.webp)

![Save](assets/merchant-guide/01-38-publish-save.webp)

![Published](assets/merchant-guide/01-39-published.webp)

![On the website](assets/merchant-guide/01-40-storefront-product.webp)

**Not showing?** In order: it is Draft; it is not in the TuneWear
Storefront sales channel; it has no price; every size is out of stock (it
shows, but crossed out).

---

## 2. Categories

**When:** a new kind of garment (Hoodies, Jackets) needs its own tile on
/men and /women.\
**Who:** Admin and above. Staff can put products into existing categories
from the product, but not create or change categories.

**The one thing to understand first:** you never choose "men" or "women" on
the category. A category appears on **/men** as soon as it holds at least
one product whose **Type** is `men` or `unisex`, and on **/women** when it
holds a `women` or `unisex` product. A category with both shows on both
pages. Example: Polos holds one `men` product, so it shows on /men only;
Sweaters holds all three types, so it shows on both.

### 2.1 Create the category

1. Sidebar **Products → Categories** → **Create**.
2. **Title** — the name on the tile, e.g. `Hoodies`. Leave **Handle**
   empty (Medusa makes `hoodies`; it is only the end of the web address —
   the tile links to `/men/hoodies` and `/women/hoodies`).
3. **Description** — the short line under the name on the tile. **Status**
   `Active`, **Visibility** `Public` are already chosen.
4. **Continue** → **Organize Ranking**: drag it to its place in the list →
   **Save**.

![Categories](assets/merchant-guide/02-01-categories.webp)

![Details](assets/merchant-guide/02-02-category-details.webp)

![Ranking](assets/merchant-guide/02-03-category-ranking.webp)

![Created](assets/merchant-guide/02-04-category-created.webp)

### 2.2 Put products in it

On the category's page, **Products** box → **Add** → tick the products →
save. (Or from each product: **Organize → ⋯ → Edit → Categories**.) Each
product must also be Published, in the TuneWear Storefront channel, and
have the right Type.

![Add products](assets/merchant-guide/02-05-category-add-product.webp)

![Has a product](assets/merchant-guide/02-06-category-has-product.webp)

### 2.3 The tile photo

**Tile photograph** box → **Upload photo** (up to 8 MB). Your upload always
wins over the photo the site came with.

![Tile photo](assets/merchant-guide/02-10-tile-photo.webp)

![Saved](assets/merchant-guide/02-11-tile-photo-saved.webp)

![On /men](assets/merchant-guide/02-14-men-tile.webp)

### 2.4 The category's size chart and search text

**Default size chart** — every product in the category shows this chart
unless the product picks another (1.13). **SEO** — the Google title and
text for the category page.

![Size chart](assets/merchant-guide/02-07-category-size-chart.webp)

![Save](assets/merchant-guide/02-08-category-size-chart-save.webp)

![Saved](assets/merchant-guide/02-09-category-size-chart-saved.webp)

![SEO](assets/merchant-guide/02-12-category-seo.webp)

![Saved](assets/merchant-guide/02-13-category-seo-saved.webp)

### 2.5 Size charts themselves

Sidebar **Size charts** → **Create**: a title, the unit, the measurement
columns (Chest, Length…) and one row per size. A category then uses it
(2.4).

![Size charts](assets/merchant-guide/03-01-size-charts-page.webp)

![New chart](assets/merchant-guide/03-02-new-chart.webp)

![Created](assets/merchant-guide/03-03-chart-created.webp)

**A tile not showing?** In order: the category has no products; none of
them has Type `men`/`unisex` (or `women`/`unisex`); they are Draft or not
in the TuneWear Storefront channel; the category is Inactive or Internal.

---

## 3. Prices and sales

### 3.1 The base price

What a garment normally costs: the product's **Price** box (1.8). Staff and
above.

### 3.2 Price lists — sales, and special prices

**When:** a sale ("Eid sale — 20% off the logo tee"), or a special price
for a group of customers (wholesale).\
**Who:** Admin and above.

A **price list** holds different prices for some products. While it is
active, the shop shows those prices — a sale price shows the normal price
struck through beside it, and the gold `-N%` badge on the photo.

| Setting                      | What it means                                                                                         |
| ---------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Type: Sale**               | A temporary lower price. The shop shows it as a sale (struck-through price, `-N%`).                   |
| **Type: Override**           | A different price with no "sale" look — for a customer group, e.g. wholesale buyers.                  |
| **Status**                   | Active = in use (within its dates). Draft = switched off.                                             |
| **Start date / Expiry date** | Optional. The list switches itself on and off at those times — a scheduled sale.                      |
| **Customer availability**    | Optional. Only customers in the chosen **customer groups** get these prices (they must be logged in). |

#### Create one

Sidebar **Price Lists** → **Create**.

![Price lists](assets/merchant-guide/03-01-price-lists.webp)

1. **Details:** type, title, status, and optionally dates and customer
   groups.

   ![Details](assets/merchant-guide/03-02-price-list-details.webp)

   ![Dates](assets/merchant-guide/03-03-price-list-dates.webp)

   ![Customer groups](assets/merchant-guide/03-09-price-list-groups.webp)

2. **Products:** tick the products the list covers — one, several, or all
   of a category (search, then tick).

   ![Products](assets/merchant-guide/03-04-price-list-products.webp)

3. **Prices:** type the price for each size in the **Price BDT** column.
   Tip: type it in the first row, then drag the cell's corner down to copy
   it to every size.

   ![Prices](assets/merchant-guide/03-05-price-list-prices.webp)

4. **Save.**

#### Make the shop show it — Publish changes

**Price lists are the one change that does not reach the shop by itself.**
After creating, editing or ending a price list, press **Publish changes**
on the Price Lists page. Worked example: a sale price of ৳990 on the logo
tee — before Publish changes the shop still shows ৳1,290; after, it shows
~~৳1,290~~ **৳990 −23%**.

![Publish changes](assets/merchant-guide/03-06-publish-changes.webp)

![Done](assets/merchant-guide/03-07-publish-toast.webp)

![On the shop](assets/merchant-guide/03-08-sale-price-live.webp)

#### Change, extend, end, or delete a sale

Open the list:

![A price list](assets/merchant-guide/03-10-price-list-page.webp)

- **Edit prices** (3): the same grid — change any price, **Save**.
- **Add products** (2): add more products to the sale.
- **End it now or change its dates**: **Configuration** (4) → **⋯ → Edit** →
  set the expiry date to now (or move it later to extend) → **Save**.

  ![Configuration](assets/merchant-guide/03-12-configuration-menu.webp)

  ![Dates](assets/merchant-guide/03-13-configuration-dates.webp)

- **Pause it**: ⋯ (1) → **Edit** → Status **Draft**.
- **Delete it**: ⋯ (1) → **Delete**. Prices go back to normal.

  ![Menu](assets/merchant-guide/03-11-price-list-menu.webp)

After any of these, press **Publish changes**.

### 3.3 Which price wins

- **Sale:** the shopper pays the lower of the normal price and the sale
  price. A sale can never make something dearer.
- **Override:** for the customers it covers, it simply replaces the normal
  price — even if it is higher. Use it deliberately (a wholesale price).
- Two sales on the same product: the lower one wins.

---

## 4. Discount codes and offers (promotions)

**When:** a code you hand out ("`EID20` for 20% off"), or an offer that
applies by itself ("free delivery", "buy 2 get 1").\
**Who:** Admin and above.

Shoppers type codes in the **Discount code** box in the checkout summary.
One code per order: a second code replaces the first. The discount shows
as its own line at checkout, on the confirmation page and on the
customer's order page.

![A code applied at checkout](assets/merchant-guide/04-13-checkout-code.webp)

If a code is refused, the box says why: **"That code isn't valid"** (no
such code, or it is switched off), **"This code can't be used on this
bag"** (its conditions are not met), or **"Choose your district first"**
(a free-delivery code, before a district is chosen).

### 4.1 The six kinds

Sidebar **Promotions → Create** → choose the kind → **Continue**.

![Promotions](assets/merchant-guide/04-01-promotions.webp)

![Kinds](assets/merchant-guide/04-02-promo-type.webp)

| Kind                       | Example                                             |
| -------------------------- | --------------------------------------------------- |
| **Amount off products**    | ৳200 off the logo tee                               |
| **Amount off order**       | ৳300 off any order                                  |
| **Percentage off product** | 20% off everything in Sweaters                      |
| **Percentage off order**   | 10% off the whole order (`TUNE10`)                  |
| **Buy X Get Y**            | Buy 2 T-shirts, get 1 free                          |
| **Free shipping**          | Free delivery (`FREESHIP`), for everyone or a group |

### 4.2 The settings every kind shares

![Method and status](assets/merchant-guide/04-06-method-status.webp)

- **Method — Promotion code** (1): shoppers must type the code. **Automatic**
  (2): applies by itself to every bag that qualifies — no code.
- **Status — Active** (3) to use it now; **Draft** keeps it switched off.
- **Code** — what shoppers type, e.g. `EID20` (capitals; shoppers can type
  it in any case).
- **Who can use this code?** — leave empty for everyone, or **Add
  condition** → **Customer group** to limit it (e.g. VIP customers).
- **Usage Limit** — how many times it can be used across all orders, e.g.
  100 for "first 100 orders". Empty = unlimited.

### 4.3 Value, and which items

![Value and allocation](assets/merchant-guide/04-07-value-allocation.webp)

- **Promotion Value** (1) — the percentage or the amount.
- **Maximum Quantity** — how many pieces in one bag get the discount.
- **Allocation** (2) — **Each**: every matching piece is discounted;
  **Once**: only up to the maximum quantity.
- **What items will the promotion be applied to?** — **Add condition** →
  **Select Attribute** (1) → Product, Category, Type or Tag → the values.
  "20% off Sweaters" = Category **In** Sweaters.

![Item conditions](assets/merchant-guide/04-08-item-conditions.webp)

### 4.4 Amount off — pick Taka

For **Amount off order**, the **Currency Code** (1) condition starts empty
and the amount box shows **USD $**. Choose **BDT** in the currency
condition, then type the amount in Taka (2). Without BDT the code does
nothing on a Taka order.

![Currency](assets/merchant-guide/04-09-currency.webp)

### 4.5 Buy X Get Y

"What needs to be in the cart to unlock the promotion?" — the minimum
quantity and the product(s) that must be bought. "What items will the
promotion be applied to?" — the free (or discounted) piece(s).

![Buy X Get Y](assets/merchant-guide/04-10-buy-x-get-y.webp)

### 4.6 Free delivery

Choose **Free shipping**. Leave "What shipping methods…" empty for every
delivery, or limit it to one delivery type (e.g. Inside Dhaka). Make it
**Automatic** for "free delivery for everyone this week", or give it a
code. The shopper sees the delivery charge and then a Discount line taking
it off, as soon as they pick their district.

> **Not possible here: "free delivery over ৳3,000".** Medusa's conditions
> are customer group, region, country, sales channel and currency — there
> is no minimum order amount. A minimum-spend offer needs a developer.

![Free shipping](assets/merchant-guide/04-11-free-shipping.webp)

### 4.7 Dates and budgets — campaigns

The last step, **Campaign**, groups promotions with a **start and end
date** and a **budget** (a total number of uses, or a total amount of
discount). When the end date passes or the budget runs out, the promotion
stops by itself. Choose **Without campaign** for an open-ended code.

![Campaign](assets/merchant-guide/04-04-promo-campaign.webp)

![Created](assets/merchant-guide/04-05-promo-created.webp)

![Details](assets/merchant-guide/04-03-promo-details.webp)

### 4.8 Pause, change or delete

Open the promotion → **⋯** → **Edit** (set Status to **Draft** to pause it,
or change the value) or **Delete**.

![Promotion menu](assets/merchant-guide/04-12-promotion-page.webp)

---

## 5. Delivery charges

**When:** the courier's rate changes, or you want a different charge
inside or outside Dhaka.\
**Who:** Admin and above.

Checkout charges by district:

| Delivery                   | For                         | Staging price |
| -------------------------- | --------------------------- | ------------- |
| **Inside Dhaka**           | the **Dhaka district** only | ৳60           |
| **Outside Dhaka**          | every other district        | ৳160          |
| **Express (Inside Dhaka)** | not offered at checkout yet | ৳180          |

The shopper sees the charge the moment they pick their district, and the
order is charged exactly that. Change a price here and checkout shows the
new one straight away — no code, no deploy.

1. **Settings** (bottom of the sidebar) → **Locations & Shipping** (1) →
   **Dhaka Warehouse** (2).

   ![Locations](assets/merchant-guide/04b-01-locations.webp)

2. Under **Shipping options**, the **⋯** (1) beside the delivery to change.

   ![Shipping options](assets/merchant-guide/04b-02-option-menu.webp)

3. **Edit prices** (1).

   ![Edit prices](assets/merchant-guide/04b-03-edit-prices.webp)

4. Click the price (1), type the new amount, **Save** (2).

   ![Price](assets/merchant-guide/04b-04-price-grid.webp)

   ![Saved](assets/merchant-guide/04b-05-saved.webp)

> **Free delivery is a promotion** (4.6), not a ৳0 price here — a ৳0
> price would make delivery free for everyone, always.

---

## 6. Stock

**When:** new stock arrives, a count is wrong, a size sells out.\
**Who:** Staff and above.

### 6.1 Three numbers: in stock, reserved, available

| Number        | Means                                                                         |
| ------------- | ----------------------------------------------------------------------------- |
| **In stock**  | Pieces on the shelf (Medusa calls it Stocked quantity).                       |
| **Reserved**  | Pieces promised to orders that are placed but **not yet fulfilled** (packed). |
| **Available** | In stock minus reserved — what the website can still sell.                    |

The website sells only what is **available**. Worked example from the
staging shop: Cable Knit Turtleneck, size S — in stock 20, reserved 3
(three orders not packed yet), available 17. Size M shows 19 in stock
because one order was already fulfilled (6.3).

![Inventory](assets/merchant-guide/05-00-inventory-list.webp)

![One size](assets/merchant-guide/05-04-inventory-item.webp)

### 6.2 Changing a count

From the product: **Variants** → the size's **⋯** → **Edit stock** → type
the new count → **Save**. (From the **Inventory** page the same box opens
from each row.)

![Edit stock](assets/merchant-guide/05-01-edit-stock-menu.webp)

![Stock grid](assets/merchant-guide/05-02-stock-grid.webp)

![Saved](assets/merchant-guide/05-03-stock-saved.webp)

Type the number **on the shelf** — do not subtract reserved pieces
yourself; Medusa does that.

### 6.3 When stock really goes down

1. **Order placed** → the pieces are **reserved**. In stock stays the same;
   available drops at once, so nobody else can buy the last one.
2. **Order fulfilled** (packed, chapter 7) → in stock goes down and the
   reservation disappears. Available does not change again.
3. **Order cancelled before fulfilling** → the reservation is released and
   the piece is available again.

---

## 7. Orders

**Who:** Staff and above.

### 7.1 What the shopper sees

At checkout the shopper picks **Cash on Delivery** or **Online Payment**
(card, bKash, Nagad through SSLCommerz):

![Checkout](assets/merchant-guide/06-01-checkout-cod.webp)

After placing an order the shopper gets this page, with an order reference
like **TW-Q2NG7A**. That is what they will quote on WhatsApp.

![Order confirmed](assets/merchant-guide/06-02-order-confirmed.webp)

### 7.2 Finding an order

Sidebar **Orders**. Paste the shopper's `TW-…` reference into the search
box to find it.

![Orders](assets/merchant-guide/06-03-orders-list.webp)

![Search by reference](assets/merchant-guide/06-04-orders-search-reference.webp)

### 7.3 From placed to done — the four steps

| Step                  | What it means                                              | What happens to stock and money |
| --------------------- | ---------------------------------------------------------- | ------------------------------- |
| **Fulfill**           | You picked and packed the items — "ready for the courier". | Stock goes down for real (6.3). |
| **Mark as shipped**   | Handed to the courier. Add the tracking number.            | —                               |
| **Mark as delivered** | The customer has it.                                       | —                               |
| **Capture payment**   | For Cash on Delivery: the rider handed over the cash.      | The order counts as paid.       |

**Fulfill** — order page → **⋯** → **Fulfill items**. The number beside
each item is **how many of it go in this package** (not stock) — send
part of an order now and the rest later if one piece is late. It also
shows which location the stock leaves from.

![Fulfill](assets/merchant-guide/06-05-fulfill-menu.webp)

![Fulfill form](assets/merchant-guide/06-06-fulfill-form.webp)

![Fulfilled](assets/merchant-guide/06-07-fulfilled.webp)

**Mark as shipped** → type the courier's tracking number in the **Tracking
number** field.

![Mark as shipped](assets/merchant-guide/06-08-mark-shipped.webp)

![Tracking](assets/merchant-guide/06-09-tracking.webp)

![Shipped](assets/merchant-guide/06-10-shipped.webp)

**Mark as delivered.**

![Mark as delivered](assets/merchant-guide/06-11-mark-delivered.webp)

![Confirm](assets/merchant-guide/06-12-delivered-confirm.webp)

**Capture payment** — for Cash on Delivery, once the cash is in. Online
payments (SSLCommerz: card, bKash, Nagad) are captured already.

![Capture](assets/merchant-guide/06-13-capture.webp)

![Confirm](assets/merchant-guide/06-14-capture-confirm.webp)

![Done](assets/merchant-guide/06-15-order-complete.webp)

### 7.4 DM orders — Draft orders

**When:** someone orders on Instagram, Facebook or WhatsApp. Type the order
in so stock, sales and Analytics include it.

Draft orders have **no sidebar entry**: go to
`https://tunewear-admin.<domain>/greenroom/draft-orders`.

![Draft orders](assets/merchant-guide/06-16-drafts.webp)

1. **Create** → the customer (search, or new: name, email, phone) and the
   address. **Postal code is optional** — Bangladeshi addresses go by
   thana.

   ![Draft form](assets/merchant-guide/06-17-draft-form.webp)

2. **Items** → **Edit** → **+** → **Add items** → pick the size → **Save**.

   ![Edit items](assets/merchant-guide/06-18-draft-edit-items.webp)

   ![Plus](assets/merchant-guide/06-19-draft-add-plus.webp)

   ![Add items](assets/merchant-guide/06-20-draft-add-items.webp)

   ![Pick size](assets/merchant-guide/06-21-draft-pick-variant.webp)

   ![Save](assets/merchant-guide/06-22-draft-items-save.webp)

3. **Shipping** → add the delivery that matches the address (Inside Dhaka
   for the Dhaka district) → **Save**.

   ![Add shipping](assets/merchant-guide/06-23-draft-add-shipping.webp)

   ![Option](assets/merchant-guide/06-24-draft-shipping-option.webp)

   ![Add](assets/merchant-guide/06-25-draft-shipping-add.webp)

   ![Save](assets/merchant-guide/06-26-draft-shipping-save.webp)

4. **Convert to order** → confirm. It is now a normal order (7.3).

   ![Convert](assets/merchant-guide/06-27-draft-convert.webp)

   ![Confirm](assets/merchant-guide/06-28-draft-convert-confirm.webp)

   ![Converted](assets/merchant-guide/06-29-draft-converted.webp)

### 7.5 Orders in a customer's account

An order placed while the customer is **logged in** appears in their
account (/account and /account/orders). An order placed **as a guest**
stays a guest order — it does not move into an account later, even with
the same email. At checkout a logged-in customer's email is locked to
their account's.

---

## 8. Customers and password resets

### 8.1 Customers

Sidebar **Customers**. **Has Account** (1) says whether the person
registered on the website (Yes) or only ordered as a guest (No). The same
email can appear twice: once as a guest, once registered.

![Customers](assets/merchant-guide/08-01-customers.webp)

Open one to see their orders, addresses and details.

![A customer](assets/merchant-guide/08-02-customer-page.webp)

**Customer groups** (sidebar **Customers → Customer Groups → Create**)
collect customers for a special price list (3.2) or a promotion (4.2),
for example "Wholesale" or "VIP".

![Customer groups](assets/merchant-guide/08-03-customer-groups.webp)

### 8.2 Resetting a customer's password

**When:** a customer cannot log in and asks for help.\
**Who:** Super Admin, or an Admin marked **Trusted** (12.3). Never Staff.

The shop does not send emails yet, so you make the link and send it
yourself (WhatsApp, SMS). You never see or type their password.

1. Sidebar **Password resets** → type their name or email (1) →
   **Search** (2).

   ![Search](assets/merchant-guide/08-04-password-resets.webp)

2. **Generate reset link** (1) on the right person.

   ![Result](assets/merchant-guide/08-05-reset-search.webp)

3. **Copy** (1) and send it to them. It works once, for 7 days; the page
   will not show it again.

   ![The link](assets/merchant-guide/08-06-reset-link.webp)

---

## 9. Shop claims — what the site says about the business

**When:** to set the three tiles under every product photo — happy
customers, rating, and a quality claim.\
**Who:** Admin and above.

Sidebar **Shop claims**. Anything left empty is left off the site — an
unsaid claim is better than an untrue one.

- **Happy customers** — a number you type, or **Use real** to show the
  real count of customers who ordered. "From real orders at 10" means the
  real number takes over once the shop has 10.
- **Product rating** — used by every garment without its own. Leave it
  empty if no one has rated your products.
- **Third tile** — your own wording and icon, for example "100% Premium
  quality".
- **One garment at a time** — a product's own rating or customer count,
  where it differs. A faded number means it is using the shop's.

![Shop claims](assets/merchant-guide/09-01-shop-claims.webp)

A rating tells shoppers other customers scored the piece. Only enter one
you can stand behind.

---

## 10. Sales channels

Sidebar **Settings → Sales Channels**. There is one: **TuneWear
Storefront**, the website. Every product must be in it to appear on the
site. There is **no Facebook or Instagram shop connected** — DM orders are
typed in as Draft orders (7.4).

![Sales channels](assets/merchant-guide/10-01-sales-channels.webp)

---

## 11. The website's words and photos (Payload)

**Where:** `https://tunewear.<domain>/admin` — a different login from
Medusa.\
**Who:** anyone with a Payload login. Payload has its own two roles:
**Super Admin** (can add and remove Payload logins) and **Admin** (edits
everything else). Medusa's roles do not apply here.

![Payload](assets/merchant-guide/10-01-payload-dashboard.webp)

### 11.1 Three things that surprise people

1. **Save publishes immediately.** There is no draft: the live page shows
   the change within about 2 seconds.
2. **Live Preview** — the eye button beside Save (1) opens the real page
   beside the form. It refreshes **when you press Save**, not as you type.
3. **Sale prices are not here** — they are Medusa's (chapter 3).

![Footer, with Live Preview open](assets/merchant-guide/11-06-footer.webp)

### 11.2 The pages

| Sidebar entry                          | What it edits                                                                                   |
| -------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Pages → Home**                       | Hero, the Men / Women / Sale cards, the sale section on/off, section headings, brand story      |
| **Pages → Men**, **Women**             | Each aisle's hero and text (the category tiles are Medusa's, chapter 2)                         |
| **Pages → Sale**                       | Masthead, Mix & Match photo, the prepaid-offer strip (strip on/off, countdown on/off, end date) |
| **Pages → New arrivals**, **Shop all** | Page headings                                                                                   |
| **Pages → About, Contact, FAQ & more** | About, Contact, FAQ, Shipping, Returns, Size guide, Privacy policy, your pages                  |
| **Site content → Footer**              | Footer columns and links, the newsletter box on/off                                             |
| **Site content → Trust Bar**           | The reassurance strip (delivery, returns, secure payment)                                       |
| **Site content → Announcement strip**  | The scrolling words under the header — one list for home, one for other pages                   |
| **Media**                              | Every uploaded photo, with a focal point (what stays in frame when cropped)                     |

Example — the Home page: open **Pages → Home**, change a heading, **Save**.

![About, Contact, FAQ & more](assets/merchant-guide/11-01-pages-list.webp)

![Home tabs](assets/merchant-guide/10-02-home-tabs.webp)

![Before saving](assets/merchant-guide/10-03-home-edit-before-save.webp)

![After saving](assets/merchant-guide/10-04-home-edit-after-save.webp)

![Trust Bar](assets/merchant-guide/11-07-trust-bar.webp)

![Announcement strip](assets/merchant-guide/11-08-announcement.webp)

#### Hiding the sale, the offer strip or the timer — and bringing them back

Three switches. Untick to hide, tick to show again, then **Save**. What
you typed is kept while hidden; nothing has to be retyped.

| To hide…                                                                 | Go to                                      | Switch                    |
| ------------------------------------------------------------------------ | ------------------------------------------ | ------------------------- |
| Just the countdown timer                                                 | **Pages → Sale** → **Prepaid offer strip** | **Show the countdown**    |
| The whole offer strip ("Extra 10% off…"), on the home page and Sale page | **Pages → Sale** → **Prepaid offer strip** | **Show this strip**       |
| The sale section on the home page (Sale masthead, best-deals row, strip) | **Pages → Home** → **Sale section**        | **Show the sale section** |

The last one only changes the home page; `/sale` itself stays. The change
is live within seconds of **Save**.

### 11.3 The FAQ

**Pages → About, Contact, FAQ & more → FAQ** → the FAQ block → one row per
question: **Question** (1), **Topic** (2), **Answer** → **Save**.

- **Topic** groups questions under headings. One topic only = a plain list.
- Topic buttons appear with two or more topics; a search box with six or
  more questions.
- The "Still have a question?" card uses the WhatsApp number from Contact.
- The questions on staging are **demo text** — replace them before launch.

![FAQ](assets/merchant-guide/11-02-faq.webp)

### 11.4 The Contact page

WhatsApp, phone, email, address, hours and social links live in the
Contact block. A field left empty (or still `[Add …]`) never becomes a
dead link. There is no message form on purpose — customers message you
directly.

![Contact](assets/merchant-guide/11-03-contact.webp)

### 11.5 Adding a page (Shipping, Returns, Size guide…)

**Pages → About, Contact, FAQ & more → Create New** → **Title** (1, only
shown in this list), **Slug** (2, the address: `shipping` → `/shipping`)
→ **Add Block** (3) → **Save**. Then link it from **Site content →
Footer**. Addresses the site already uses (`men`, `sale`, `checkout`…) are
refused with a message saying where that page is edited.

![Add a page](assets/merchant-guide/11-04-add-page.webp)

![Blocks](assets/merchant-guide/11-05-block-picker.webp)

A **Section (columns)** block puts other blocks side by side, with its own
tablet and phone layouts ("Reverse the column order when stacked" puts the
photo first on phones).

### 11.6 Privacy policy

**Pages → About, Contact, FAQ & more → Privacy policy** (`/privacy-policy`,
linked from the footer). It arrives as a draft written from how the site
works. Replace every part in **[square brackets]** — business name and
address, courier, how long you keep records, your WhatsApp and email —
have it checked, delete the first "[Draft …]" line, and **Save**.

### 11.7 Photos and logins

![Media](assets/merchant-guide/11-09-media.webp)

![Payload users](assets/merchant-guide/11-10-users.webp)

---

## 12. Staff and roles

**Who:** Super Admin only.

### 12.1 The roles

| Role                | Can                                                                              | Cannot                                                                 |
| ------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Super Admin**     | Everything, including staff accounts and roles                                   | —                                                                      |
| **Admin**           | Products, categories, orders, prices, promotions, customers, settings, analytics | Manage staff; see the audit log or make reset links unless **Trusted** |
| **Admin + Trusted** | Everything Admin can, plus the audit log and password reset links                | Manage staff                                                           |
| **Staff**           | Orders end to end, customers, products and variants, stock                       | Price lists, promotions, analytics, audit log, categories, staff       |

![Roles](assets/merchant-guide/12-04-roles.webp)

### 12.2 Adding someone

1. **Settings → Users → Invite** (1) → their email → send them the invite
   link.

   ![Users](assets/merchant-guide/12-01-users.webp)

   ![Invite](assets/merchant-guide/12-02-invite.webp)

2. Give them a role: **Settings → Roles** → the role → **Users → Add**.

   ![Role page](assets/merchant-guide/12-06-role-page.webp)

### 12.3 Pausing an account, and Trusted

On the person's page (**Settings → Users** → them):

- **Pause account** — blocks them at once, even mid-session, without
  deleting anything. Resume the same way.
- **Trusted admin → Grant access** — lets an **Admin** see the audit log
  and make password reset links. It has no effect on Staff.

![A user](assets/merchant-guide/12-03-user-page.webp)

### 12.4 The audit log

Sidebar **Audit log**: every change made in the dashboard — who, what,
when — in plain sentences. Super Admin, or a Trusted Admin.

![Audit log](assets/merchant-guide/12-05-audit-log.webp)

---

## 13. Store settings

**Who:** Admin and above.

- **Settings → Store** — the shop's name and currency (BDT).

  ![Store](assets/merchant-guide/13-01-store.webp)

- **Settings → Product Types** — `men`, `women`, `unisex`. **Do not rename
  or add types**: the website reads exactly these three to decide /men and
  /women. Any other type shows on both aisles.

  ![Product types](assets/merchant-guide/13-02-product-types.webp)

- **Settings → Locations & Shipping** — delivery charges (chapter 5).
- **Settings → Publishable API Keys** — **do not touch.** The website uses
  this key to load products; revoking or deleting it takes every product
  off the site.

  ![API keys](assets/merchant-guide/13-03-api-keys.webp)

---

## 14. Analytics, and visitor numbers in Umami

### 14.1 Analytics (in Medusa)

Sidebar **Analytics** (Admin and above). Pick the period at the top right.

| Number                  | Means                                                                                  |
| ----------------------- | -------------------------------------------------------------------------------------- |
| **Orders**              | Orders placed in the period                                                            |
| **Revenue**             | What those orders came to                                                              |
| **Average order value** | Revenue divided by orders                                                              |
| **Profit**              | Revenue minus cost price — only for products with a cost price (1.9); it says how many |

Below them: the revenue trend, orders per day, best sellers (with stock
left) and revenue by product.

![Analytics](assets/merchant-guide/14-01-analytics.webp)

### 14.2 Visitors — Umami

`https://tunewear-analytics.<domain>` — its own login.

![Umami login](assets/merchant-guide/00-login-umami.webp)

Open **Websites →
TuneWear** for visitors, page views, where they came from and which pages
they read.

![Umami](assets/merchant-guide/14-02-umami.webp)

---

## 15. Glossary

| Word                | Plain meaning                                                       |
| ------------------- | ------------------------------------------------------------------- |
| **Option**          | A way a garment varies: Size, Colour.                               |
| **Variant**         | One combination a shopper buys — Black / M. Has its own stock.      |
| **SKU**             | A product code for one variant (optional).                          |
| **Type**            | `men`, `women` or `unisex` — which aisle the product shows in.      |
| **Category**        | A tile on /men and /women (Sweaters, Polos).                        |
| **Tag**             | A label on a product (`featured`, `new-arrival`).                   |
| **Price list**      | A set of different prices — a sale, or prices for a customer group. |
| **Promotion**       | A discount code or an automatic offer.                              |
| **Campaign**        | Dates and a budget shared by promotions.                            |
| **Customer group**  | Customers collected for a special price or offer.                   |
| **Reserved**        | Stock promised to orders not yet fulfilled.                         |
| **Fulfill**         | Pick and pack an order; stock goes down.                            |
| **Capture**         | Record that the money came in (Cash on Delivery).                   |
| **Draft order**     | An order you type in yourself (DM orders).                          |
| **Sales channel**   | Where products are sold — here only the website.                    |
| **Trusted admin**   | An Admin allowed to see the audit log and make reset links.         |
| **Publish changes** | The button that sends price-list changes to the website.            |
| **Live Preview**    | Payload's side-by-side view of the real page, refreshed on Save.    |

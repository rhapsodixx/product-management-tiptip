# SatuSatu — Foreign Visitor UX Research & Customer Journey Map

> **UX Research · March 2026**

**Title:** SatuSatu Foreign Visitor Customer Journey Map

A full-stack UX intelligence report benchmarking SatuSatu against KKday, Klook, GetYourGuide, and Trip.com for the foreign leisure traveler persona booking Bali activities.

## Document Metadata

| Field | Value |
|---|---|
| Primary Persona | Foreign visitor, 28–42 yrs |
| Origin Markets | India · China · South Korea · Australia |
| Booking Window | 2–6 weeks before travel |
| Device | Mobile-first |
| Competitors | KKday · Klook · GetYourGuide · Trip.com |
| Methodology | Live website audit via direct DOM analysis & browser observation · Competitor benchmarking across 8 UX dimensions · Journey mapping for 28–42 yr old leisure traveler persona from India, China, South Korea, and Australia |

---

## Navigation Sections

1. Phase 1: Site Audit
2. Phase 2: Competitors
3. Phase 3: Gap Analysis
4. Phase 4: Journey Map
5. Phase 5: Exec Summary

---

## Phase 1 — SatuSatu.com Website Audit

> Live audit across 9 UX dimensions. Conducted March 2026 via direct observation and DOM analysis.

### 1.1 Information Architecture

| Status | Finding |
|---|---|
| ✅ Present | Five clear product categories: Attraction, Car Rental, Food & Dining, Tours, Travel Essentials |
| ✅ Present | Bottom fixed navigation on mobile (Home, Discover, Bookings, Inspiration, Profile) |
| ⚠️ Partial | Homepage hero is Indonesia-generic; no Bali-first landing page for the highest-traffic persona |
| ❌ Missing | No destination-level hub pages (e.g. "Bali Things To Do") — reduces SEO and browse discoverability |
| ❌ Missing | No editorial content or travel guides linked from navigation |

### 1.2 Search & Discovery

| Status | Finding |
|---|---|
| ✅ Present | Keyword search with placeholder "Rafting? Nusa Penida trip?" — conversational and locally relevant |
| ✅ Present | Filters: by rating, date, availability; sorting by Relevance, Rating, Newest |
| ⚠️ Partial | Minimum 3-character query threshold — may frustrate mobile users typing abbreviated terms |
| ❌ Missing | No category-filter chips or tag-based browsing on the results page |
| ❌ Missing | No price-range filter or "duration" filter — critical for foreign trip planners |
| ❌ Missing | No autocomplete / search suggestions shown while typing |

### 1.3 Attraction Detail Pages

| Status | Finding |
|---|---|
| ✅ Present | Opening hours, location, address, photos, reviews, AI summaries, cancellation policy |
| ✅ Present | Package options with per-person pricing breakdown |
| ✅ Present | Itinerary section visible — good for trip planning context |
| ⚠️ Partial | Photo gallery present but unclear if user-generated photos (UGC) are supported |
| ❌ Missing | No "What's included / excluded" formatted checklist — common industry standard |
| ❌ Missing | No "Similar experiences" or recommendation carousel |

### 1.4 Booking Flow

| Status | Finding |
|---|---|
| ✅ Present | Multi-step flow: date → package → contact/visitor info → payment |
| ✅ Present | Countdown timer ("Ticket reserved") creates urgency |
| ✅ Present | Multiple payment methods supported |
| ⚠️ Partial | Platform fee + service fee added at checkout — surprise cost friction for foreign users |
| ❌ Missing | No guest checkout — forced account creation is a conversion killer for first-time foreign visitors |
| ❌ Missing | No "Pay Later" or installment option — competitors offer this as a trust booster |

### 1.5 Trust Signals

| Status | Finding |
|---|---|
| ✅ Present | Google Reviews integration with user ratings and filtering |
| ✅ Present | "Hand-picked by local SatuSatu team" positioning creates authentic curation signal |
| ⚠️ Partial | Review system exists but no aggregate platform-level social proof number (e.g. "500K+ bookings") |
| ❌ Missing | No operator verification badge or quality certification — foreign users cannot assess vendor credibility |
| ❌ Missing | No prominent free-cancellation badge on listings — competitors use this as hero trust signal |
| ❌ Missing | No 24/7 support or live chat visible — critical for foreign tourists in a new country |

### 1.6 Mobile Experience

| Status | Finding |
|---|---|
| ✅ Present | Responsive design with mobile-specific bottom navigation bar |
| ✅ Present | Native app available for download |
| ⚠️ Partial | App download promoted but not the primary onboarding path — friction for first-time users |
| ❌ Missing | No evidence of QR code redemption / digital ticket display optimized for mobile handoff at venue |
| ❌ Missing | No offline-ready booking confirmation or downloadable e-ticket for low-connectivity scenarios |

### 1.7 Language & Localization

| Status | Finding |
|---|---|
| ✅ Present | English (en-US) as default with internationalization framework present |
| ⚠️ Partial | Multi-language support indicated in framework but active languages not clearly surfaced to users |
| ❌ Missing | No Mandarin (Simplified), Hindi, Korean, or Bahasa Indonesia option visible in UI |
| ❌ Missing | No currency localization (INR, CNY, KRW, AUD) — prices shown in IDR/USD only |
| ❌ Missing | No country-specific payment methods (e.g., WeChat Pay, UPI, Kakao Pay) |

### 1.8 Pricing Transparency

| Status | Finding |
|---|---|
| ✅ Present | Full fee breakdown shown: Base Price, Platform Fee, Service Fee, Total |
| ✅ Present | Discount/savings total displayed — positive for deal-seeking travelers |
| ⚠️ Partial | Platform + service fees only revealed at checkout — classic "drip pricing" pattern that erodes trust |
| ❌ Missing | No "From IDR X" all-inclusive starting price on listing cards |
| ❌ Missing | No price-match or best-price guarantee signal |

### 1.9 Support & Post-Booking

| Status | Finding |
|---|---|
| ✅ Present | Email and WhatsApp support channels available |
| ✅ Present | Cancellation policy shown on detail page |
| ⚠️ Partial | WhatsApp is ideal for Indonesian customers but unfamiliar/absent for Chinese (prefer WeChat) or Korean (prefer KakaoTalk) users |
| ❌ Missing | No dedicated foreign-language support line or agent |
| ❌ Missing | No post-experience email flow, review request, or loyalty reward trigger |

---

## Phase 2 — Competitor Benchmarking — Activities Vertical

> Evaluated across UX patterns, trust mechanisms, localization, search quality, and booking experience. Focus: Bali activities only.

### 2.1 Klook

**Catalog size:** 813 Bali activities

- **Catalog depth:** 813 Bali activities including Nusa Penida, Mt. Batur, Waterbom — broadest coverage
- **KlookCash loyalty:** Earn credits on reviews — creates review incentive loop and UGC flywheel
- **Free cancellation** prominently flagged — "book last minute, skip lines" messaging
- **Language switcher** in header (EN + local language options); currency selector (USD + local)
- **24/7 support** as stated trust pillar; 10+ payment channels including regional options
- **Destination count badges** ("Bali — 813 activities") signal platform scale instantly
- **Referral program**: US$5 reward per referred friend completes booking

### 2.2 KKday

**Profile:** Asian-first OTA

- **"Find your special local experience"** — similar local-first positioning to SatuSatu but at global scale
- **Category breadth:** Attraction tickets, Tours, Transport, Flights, Accommodation, WiFi/SIM, Shopping — one-stop-shop
- **Taiwan-origin with strong Asia coverage:** Japan, Korea, SE Asia natively supported
- **App exclusive deals** banner drives mobile app installs
- **Featured experiences editorial curation** — algorithmically and editorially promoted
- **Price competition:** Known for aggressive discounting and flash sales on Asian routes
- **eSIM & WiFi Card integration** — practical utility products alongside experiences

### 2.3 GetYourGuide

**Profile:** European-origin global leader

- **"Certified by GetYourGuide" badge** — premium quality signal applied to select experiences
- **Activity type labels** on every card: Day trip / Entry ticket / Guided tour — reduces cognitive load
- **"Likely to sell out" urgency tag** drives conversion without fake countdown timers
- **Automatic local currency**: Prices shown in IDR without user action — frictionless for visitors
- **Wishlist feature** natively in nav — enables research-to-booking workflow across sessions
- **Free cancellation + Pay Later** on most activities — industry-leading flexibility messaging
- **12 payment methods**: Klarna, Apple Pay, Google Pay, JCB + standard cards

### 2.4 Trip.com

**Profile:** Chinese market dominant

- **Native Chinese/Japanese/Korean UI**: Font stacks, layout, and RTL support built-in — true localization
- **Skeleton screen loading states**: Perceived performance optimization — reduces bounce on mobile
- **Autocomplete with inline pricing**: Search suggestions show price as you type — radical transparency
- **Full travel bundle:** Hotels + flights + activities in one booking — high stickiness for Chinese travelers
- **WeChat Pay / Alipay** integration — essential for Chinese travelers abroad
- **Discount badge system** with color-highlighted savings row on pricing — clear deal signaling
- **Progressive disclosure** via expandable sections + popovers — clean mobile experience

---

## Phase 3 — Competitive Gap Analysis

> SatuSatu vs. four global OTAs across 8 benchmark criteria. Ratings reflect foreign visitor experience specifically.

| Criteria | SatuSatu | KKday | Klook | GetYourGuide | Trip.com |
|---|---|---|---|---|---|
| **Attraction catalog depth & discoverability** *(Volume, browse, SEO landing pages)* | ⚠️ Partial — Indonesia-focused; no destination hub pages; no SEO-optimized Bali landing | ✅ Strong — Comprehensive Bali catalog; destination page with sub-categories | ✅ Strong — 813 Bali activities; destination cards with activity counts | ✅ Strong — Deep catalog; activity-type filtering; curated "Places to See" nav | ✅ Strong — Strong Bali offering; integrated with hotels/flights boosting discovery |
| **Search & filter UX** *(Filters, autocomplete, sort options)* | ⚠️ Partial — Basic keyword search; no autocomplete; limited price/duration filters | ✅ Strong — Autocomplete with destination + activity suggestions; multiple filter layers | ✅ Strong — Rich faceted search; category chips; duration/price/rating filters | ✅ Strong — "Things to do" / "Places to see" / "Trip inspiration" nav taxonomy; robust filters | ✅ Strong — Autocomplete with live pricing; popover-based category filtering |
| **Booking flow friction** *(Steps, guest checkout, pay later, clarity)* | ⚠️ Partial — Multi-step flow; no guest checkout; hidden fees revealed at end; countdown timer | ✅ Strong — Streamlined; guest checkout available; app-first flow with exclusive discounts | ✅ Strong — Fast checkout; last-minute booking; free cancellation prominent; skip-the-line ticketing | ✅ Strong — Pay Later option; free cancellation on most items; wishlist + cart; minimal steps | ⚠️ Partial — Strong for Chinese users; JS-heavy flow may frustrate non-Chinese visitors |
| **Trust signals** *(Reviews, ratings, cancellation, verification)* | ⚠️ Partial — Google Reviews integrated; local curation badge; no operator verification; no aggregate proof numbers | ✅ Strong — "Why KKday?" trust section; review counts per listing; free cancellation badges | ✅ Strong — Review counts visible; 24/7 support stated; free cancellation; KlookCash creates review flywheel | ✅ Strong — "Certified by GetYourGuide" badge; review count + rating on every card; "likely to sell out" tags; 24/7 support + free cancel | ⚠️ Partial — Strong for Chinese market; trust signals less adapted for Indian/Korean/Australian travelers |
| **Language & currency localization** *(UI languages, currency auto-detect, payment methods)* | ❌ Missing — English-only visible; IDR/USD only; no WeChat Pay / UPI / KakaoPay; no Mandarin, Hindi, Korean UI | ✅ Strong — Mandarin, Korean, Japanese, English natively supported; Asian payment methods | ✅ Strong — Language + currency switcher in header; 10+ payment channels including regional options | ✅ Strong — Auto-detects local currency (shows IDR in Indonesia); language selector; 12 payment methods incl. Klarna, Apple/Google Pay | ✅ Strong — Mandarin native; Japanese, Korean UI; WeChat Pay / Alipay built-in; RTL support |
| **Mobile experience** *(App, responsive design, PWA, ticket UX)* | ⚠️ Partial — App available; responsive; fixed bottom nav; no offline ticket/QR optimization | ✅ Strong — App-first with exclusive deals; push notifications; QR code e-tickets | ✅ Strong — Mature app; app-only deals; skip-the-line QR codes; "send link to email" app download flow | ✅ Strong — Well-rated app; mobile-optimized booking flow; Google/Apple Pay native; app download QR | ✅ Strong — Taro-framework mobile-first architecture; skeleton screens; floating CTA buttons |
| **Social proof & UGC** *(User reviews, photos, ratings density, referrals)* | ❌ Missing — Google Reviews only; AI summaries (novel but cold); no traveler photo UGC; no platform-level social proof counter | ⚠️ Partial — Review counts on listings; editorial curation; limited UGC photo integration | ✅ Strong — KlookCash incentivizes review posting; high review density per listing; traveler photos; referral program | ✅ Strong — Rich verified review counts on every card; "Certified" badge; high review density from global travelers | ⚠️ Partial — Strong Chinese UGC; limited English-language review density for non-Chinese travelers |
| **Pricing transparency** *(All-inclusive pricing, no hidden fees, local currency)* | ⚠️ Partial — Detailed fee breakdown at checkout; but platform + service fees only shown at end ("drip pricing") | ✅ Strong — All-in pricing visible on listing cards; flash sales with clear original vs. discounted price | ✅ Strong — Clear "From" pricing on cards; no surprise fees; discount savings total shown upfront | ✅ Strong — "From Rp X" all-in pricing in local currency on every card; no hidden fees model | ✅ Strong — Price prefix + discount row with color highlight; autocomplete shows pricing inline |

### 3.1 Competitive Scoring Radar

> Composite score (1–10) per criterion for the foreign visitor persona booking Bali activities. Higher = better foreign visitor experience.

| Criterion | SatuSatu | Klook | KKday | GetYourGuide | Trip.com |
|---|---|---|---|---|---|
| Catalog Depth | 4 | 9 | 8 | 9 | 8 |
| Search & Filter | 4 | 8 | 7 | 9 | 8 |
| Booking Flow | 5 | 8 | 7 | 9 | 7 |
| Trust Signals | 4 | 8 | 7 | 9 | 7 |
| Localization | 2 | 8 | 8 | 8 | 9 |
| Mobile UX | 6 | 8 | 7 | 8 | 8 |
| Social Proof | 3 | 9 | 6 | 9 | 7 |
| Price Transparency | 5 | 8 | 7 | 9 | 8 |

> [Visual: Radar chart comparing SatuSatu vs. Klook vs. KKday vs. GetYourGuide vs. Trip.com across 8 criteria on a 1–10 scale]

---

## Phase 4 — Customer Journey Map

> **Persona:** 28–42 year old foreigner (India / China / South Korea / Australia) planning a leisure Bali trip, booking on mobile, 2–6 weeks before travel, unfamiliar with Indonesian platforms.

### Emotion Arc — SatuSatu Foreign Visitor Sentiment Trajectory

> Sentiment score (1–10) mapped across journey stages. Dip in Evaluation & Booking reflects trust gap versus global OTAs.

| Stage | SatuSatu Experience Score | Competitor Benchmark (avg) |
|---|---|---|
| Inspiration | 8 | 8 |
| Research | 6 | 7 |
| Evaluation | 3.5 | 7 |
| Booking | 4 | 7.5 |
| Pre-Experience | 7 | 8 |
| Post-Experience | 6 | 8 |

**Emotion scale reference:**
- 1 = 😫 Frustrated
- 3 = 😟 Anxious
- 5 = 😐 Neutral
- 7 = 😊 Satisfied
- 9 = 🤩 Delighted

> [Visual: Line chart showing emotion arc with SatuSatu (purple) vs. Competitor Benchmark dashed grey line across 6 journey stages]

---

### Stage 1 — Inspiration

> Discovering that Bali activities can be booked in advance online

**Color:** Purple (`#7C3AED`)

#### User Goal
- Identify the best activities for their Bali trip
- Get a sense of what is possible and how to plan

#### Touchpoints
- Instagram / TikTok travel reels
- YouTube Bali vlogs
- Google Search: "best things to do in Bali"
- Reddit / travel forums / Facebook groups
- Friends & family recommendations

#### Actions
- Scrolls travel content on social media
- Saves posts to Instagram collections or Pinterest
- Watches YouTube "Bali travel guide" videos
- Reads travel blog listicles
- Asks in WhatsApp groups or Discord servers

#### Thoughts & Emotions
- 😊 Excited (positive)
- 😊 Inspired (positive)
- 😐 Curious (neutral)

> *"Bali looks incredible — I need to book that Nusa Penida tour and the sunrise trek ASAP."*

#### Pain Points
- SatuSatu has minimal presence in global travel content — rarely appears in Instagram tags, YouTube mentions, or Reddit threads compared to Klook/GYG
- No blog or editorial "Bali guide" content under SatuSatu brand to capture top-of-funnel search traffic

#### Opportunities
- Launch a Bali editorial hub ("Best Things to Do in Bali 2026") optimized for SEO & Google Discover
- Partner with Indonesian travel creators to feature SatuSatu in Bali vlogs with affiliate tracking
- Run Instagram & TikTok ads targeting travelers from IN/CN/KR/AU with destination-specific creative

---

### Stage 2 — Research

> Exploring Bali activity options, reading reviews, comparing booking platforms

**Color:** Blue (`#2563EB`)

#### User Goal
- Build a shortlist of activities with reliable info
- Find the most trustworthy platform to book through
- Understand pricing and what is included

#### Touchpoints
- Google Search (mobile)
- Klook / GetYourGuide / Airbnb Experiences
- TripAdvisor attraction pages
- Travel blogs & comparison articles
- KakaoTalk / WeChat groups (Korean/Chinese)
- Zomato / Google Maps for location context

#### Actions
- Searches "Nusa Penida day tour" on Google
- Compares Klook vs. GetYourGuide listings
- Reads 10–20 reviews per activity
- Checks cancellation policies
- Looks at photo galleries of experiences
- Saves wishlist items across multiple platforms

#### Thoughts & Emotions
- 😐 Methodical (neutral)
- 😟 Slightly overwhelmed (mixed)
- 😐 Analytical (neutral)

> *"There are so many options. I'll stick to platforms I know — Klook has thousands of reviews, I trust that."*

#### Pain Points
- SatuSatu does not rank visibly in Google searches for "Bali activities" or "book Bali tours" — dominated by Klook, GYG, Viator, TripAdvisor
- Foreign users will not discover SatuSatu organically without prior awareness campaign
- Competitor platforms surface review counts (Klook: 813 activities; GYG: hundreds of verified reviews per listing) — SatuSatu's review density appears thin to newcomers

#### Opportunities
- Invest in destination SEO: rank for "Nusa Penida tour", "Bali sunrise trek", "Seminyak food tour" with dedicated landing pages
- Display total booking/review counts prominently on homepage ("10,000+ experiences booked")
- Add a cross-platform review import (TripAdvisor, Google) to boost visible review density for foreign users

---

### Stage 3 — Evaluation

> Shortlisting SatuSatu vs. global OTAs — trust audit and platform credibility check

**Color:** Cyan (`#0891B2`)

#### User Goal
- Decide which platform is safest to transact on
- Verify activity quality matches expectations
- Confirm cancellation terms before committing

#### Touchpoints
- SatuSatu.com (possibly referred from Google or friend)
- Direct comparison: SatuSatu listing vs. Klook listing of same activity
- Google search: "SatuSatu review" / "is SatuSatu safe?"
- App Store / Play Store ratings
- Reddit threads discussing Indonesia booking platforms

#### Actions
- Opens SatuSatu and immediately scans for trust signals
- Looks for number of reviews and reviewer nationalities
- Checks if platform has English cancellation policy
- Tests search: types "Nusa Penida" and evaluates results
- Tries to browse by category — may get confused by limited filters
- Googles "SatuSatu legit" if they haven't heard of it

#### Thoughts & Emotions
- 😟 Skeptical (mixed)
- 😟 Uncertain (negative)
- 😐 Cautiously open (neutral)

> *"Never heard of SatuSatu. Prices look good but I don't see many reviews from people like me. Maybe I'll just book on Klook to be safe."*

#### Pain Points
- No "Certified" or verified operator badge — foreign users have no signal that local operators are vetted
- Limited visible reviews from Indian/Chinese/Korean/Australian travelers — homophily bias means foreigners trust reviews from their own demographic
- Platform name "SatuSatu" is Indonesian — triggers unfamiliarity anxiety for non-Indonesian users without trust scaffolding
- No aggregate social proof number on homepage; Klook shows "813 Bali activities" which signals scale immediately
- No free cancellation badge on listing cards — users don't feel safe to book without it

#### Opportunities
- Add "SatuSatu Verified" operator badge with a brief tooltip explaining local curation process
- Show review nationality flags ("✅ Reviewed by travelers from 🇮🇳🇦🇺🇰🇷") to build cross-cultural social proof
- Homepage hero: add "10,000+ experiences booked" + "Locally curated for foreign visitors" tagline
- Add free cancellation badge to all eligible listings — match industry standard

---

### Stage 4 — Booking

> Completing a transaction on SatuSatu.com on mobile

**Color:** Green (`#16A34A`)

#### User Goal
- Complete payment quickly and confidently
- Receive clear confirmation and ticket
- Know what to do on the day of the activity

#### Touchpoints
- SatuSatu listing detail page (mobile)
- Account creation flow
- Payment gateway
- Booking confirmation email
- WhatsApp support channel

#### Actions
- Selects date and package
- Hits "Book Now" — forced to create account
- Fills personal details (contact, visitor count)
- Reaches payment page — sees Platform Fee + Service Fee added
- Chooses payment method (limited if foreign card / e-wallet)
- Completes payment; waits for confirmation

#### Thoughts & Emotions
- 😟 Frustrated (fees) (mixed)
- 😐 Cautious (account) (neutral)
- 😊 Relieved if confirmed (positive)

> *"Why am I being charged a platform fee AND a service fee? And I can't pay with Google Pay?"*

#### Pain Points
- Mandatory account creation before checkout — friction barrier for one-time foreign travelers; Klook & GYG allow social/guest login
- Platform fee + service fee revealed at payment step — triggers price abandonment for international comparison shoppers
- Limited foreign payment methods — no Google Pay, Apple Pay, Alipay, WeChat Pay, UPI, or KakaoPay visible
- Countdown timer ("Ticket reserved") may increase anxiety rather than urgency for unfamiliar users
- No confirmation in user's preferred language; WhatsApp support not accessible to Chinese users (often blocked)

#### Opportunities
- Add Google/Apple social login + guest checkout — target 15–25% checkout conversion lift
- Integrate Apple Pay, Google Pay, Alipay, WeChat Pay, UPI for target markets
- Show all-inclusive price upfront ("Total: IDR 450,000 — no hidden fees") to pre-empt abandonment
- Offer "Pay Later" option for bookings made 2+ weeks ahead — reduces commitment anxiety
- Add Telegram/Line support channel as WhatsApp alternative for Chinese/Japanese travelers

---

### Stage 5 — Pre-Experience

> Between booking confirmation and the activity day — logistics, questions, reassurance

**Color:** Amber (`#D97706`)

#### User Goal
- Receive clear logistics (meeting point, what to bring)
- Feel confident the booking is confirmed & real
- Be able to modify or cancel if plans change

#### Touchpoints
- Booking confirmation email
- SatuSatu app / booking detail page
- WhatsApp from operator
- Reminder push notification
- Google Maps for meeting point

#### Actions
- Re-reads confirmation email; saves PDF/screenshot
- Checks meeting point on Google Maps
- Asks WhatsApp support for clarification (if confused)
- Shares booking details with travel companions
- Downloads app to access ticket on day-of

#### Thoughts & Emotions
- 😊 Anticipating (positive)
- 😐 Slightly anxious (logistics) (neutral)
- 😊 Organized (positive)

> *"I'm excited but I'm not 100% sure where the pickup point is. The email is a bit vague."*

#### Pain Points
- Confirmation email may not include embedded Google Maps link or clear meeting point instructions for foreign tourists unfamiliar with Bali geography
- No proactive reminder push notification 24 hours before — Klook sends automated day-before reminders with key info
- No multilingual logistics information — Chinese tourists cannot read WhatsApp instructions in Bahasa/English fluently
- No in-app chat with operator before the day — creates anxiety for high-value tours (Mt. Batur trek, scuba diving)

#### Opportunities
- Automated pre-activity email (T-24h and T-2h) with embedded map, what-to-bring checklist, operator contact, and weather advisory
- Add in-app operator chat thread accessible from booking detail page
- Offer multilingual logistics summaries (auto-translated) for Mandarin, Hindi, Korean travelers
- Add "Share itinerary" deep link so travelers can send booking details to companions natively

---

### Stage 6 — Post-Experience

> Review, repeat purchase consideration, word-of-mouth advocacy

**Color:** Red (`#E11D48`)

#### User Goal
- Share experience with friends and on social media
- Leave a review if experience was great
- Return to book more activities for future trips

#### Touchpoints
- Post-activity review request email
- SatuSatu app review prompt
- Instagram / TikTok (user shares content)
- WhatsApp groups (word of mouth)
- Future trip planning search

#### Actions
- Posts Bali photos/reels on Instagram/TikTok
- Tags location; may or may not tag SatuSatu
- Opens review email — may or may not complete
- Recommends activity to friends in travel groups
- Doesn't necessarily return to SatuSatu for next trip (no loyalty hook)

#### Thoughts & Emotions
- 😊 Happy if activity great (positive)
- 😐 Indifferent to platform brand (neutral)
- 😟 No incentive to return (mixed)

> *"The tour was amazing! But I'll probably just book Klook next time — I'm already logged in there and have credits."*

#### Pain Points
- No loyalty program or review reward — Klook's KlookCash directly incentivizes review posting AND repeat booking
- No post-stay email sequence (curated "you might love this next" follow-up)
- Platform brand not top-of-mind after activity — user remembers the experience, not SatuSatu
- No referral program to convert happy travelers into brand advocates with their peer networks
- Social content posted to Instagram doesn't link back to SatuSatu — missed UGC capture opportunity

#### Opportunities
- Launch "SatuSatu Credits" loyalty program — earn credits per booking + review; redeem on next trip
- Post-activity email: "You might love..." with AI-personalized next activities + 10% loyalty discount
- Referral program: "Share with a friend, both get IDR 50,000 credit" — grow word-of-mouth in target markets
- UGC campaign: incentivize tagging @satusatu on Instagram/TikTok with chance to win free experience

---

## Phase 5 — Executive Summary

> Critical pain points, highest-leverage opportunities, and one-line competitor learning for each platform.

### The Core Strategic Problem

> SatuSatu has a genuinely differentiated value proposition — locally curated, authentic Indonesian experiences. But it is invisible to the foreign traveler at the top of funnel, and fails to convert the ones who do find it due to missing trust scaffolding, limited localization, and a friction-heavy booking flow. Global OTAs win not because they offer better experiences, but because they've eliminated doubt at every step of the journey.

---

### Top 3 Critical Pain Points for Foreign Persona

#### Pain Point #1 — Zero Localization for Top Inbound Markets

SatuSatu offers no UI in Mandarin, Hindi, or Korean — the three largest Bali visitor markets after Australia. There is no local currency display (INR, CNY, KRW), no WeChat Pay, UPI, or Kakao Pay. Competitors like Trip.com and KKday have native language support for these markets. A Chinese traveler landing on SatuSatu faces English-only content, IDR pricing, and no familiar payment method — a triple abandonment trigger.

#### Pain Point #2 — Trust Deficit at the Evaluation Stage

Foreign visitors — especially those booking a platform for the first time — rely heavily on social proof signals to overcome brand unfamiliarity. SatuSatu lacks: a verified operator badge, review counts from similar traveler demographics, a platform-wide booking count, a free cancellation badge, and 24/7 international support. GetYourGuide shows a "Certified" badge, review count, and "Likely to sell out" tag on every card. SatuSatu's evaluation page triggers skepticism, not confidence.

#### Pain Point #3 — Booking Flow Friction & Hidden Fee Surprise

The combination of mandatory account creation + Platform Fee + Service Fee revealed only at checkout is the highest-friction booking pattern in the competitive set. Foreign travelers — often comparing open tabs across Klook and GYG — will abandon when unexpected fees appear at the final step. Klook and GetYourGuide show all-inclusive "From" pricing upfront and offer guest/social login. Every additional step in a foreign user's checkout flow costs conversion.

---

### Top 3 Highest-Leverage Opportunities vs. Competitors

#### Opportunity #1 — Own "Locally Curated Indonesia" as a Defensible Moat

While Klook and GYG have volume, SatuSatu can win on authenticity and depth of local knowledge. Double down: add operator profiles (who they are, how they're vetted), local expert editorial content, and a "SatuSatu Verified Local" certification badge. Position the platform as the only way to book experiences curated by Indonesians, for foreign visitors who want the real Bali — not the tourist version. No global OTA can replicate genuine local authority.

#### Opportunity #2 — Capture the Korean & Indian Market Before Competitors Localize

India is the fastest-growing Bali visitor market (2.5M+ annually); South Korea is #3. KKday and Klook serve these markets generically. SatuSatu has the opportunity to be the first Indonesia-native platform with a native Hindi or Korean UI, UPI/Kakao Pay integration, and locally-relevant curation (e.g., halal food tours, vegetarian experiences for Indian travelers). First-mover advantage in these underserved niches could deliver outsized market share before global OTAs adapt.

#### Opportunity #3 — Build a Review & Loyalty Loop to Drive Retention

Klook's KlookCash creates a virtuous cycle: book → earn credits → write review → earn more credits → book again. SatuSatu has no equivalent. Introducing "SatuSatu Points" (earned on bookings + reviews, redeemable across the catalog) combined with a referral program targeting peer-recommendation-heavy markets (India, Korea) would create retention mechanics that global OTAs already exploit. The goal: make leaving SatuSatu feel costly.

---

### One-Line Strategic Recommendation per Competitor

| Competitor | Strategic Stance | What SatuSatu Should Learn or Differentiate |
|---|---|---|
| **Klook** | `Learn from` — Review incentive mechanics + free cancellation confidence signaling | Adopt KlookCash-style loyalty credits tied to reviews; make "free cancellation" a hero trust badge on every eligible listing card to match Klook's conversion advantage. |
| **KKday** | `Differentiate from` — Both claim "local experience" — SatuSatu must go deeper | KKday's "local experience" pitch is generic global; SatuSatu should out-authenticate it with verifiable operator profiles, community-sourced itineraries, and an "Only on SatuSatu" exclusive experiences badge for hidden gems no OTA lists. |
| **GetYourGuide** | `Learn from` — Trust architecture, pricing transparency, and payment flexibility | Replicate GYG's "Certified" badge system, all-inclusive upfront pricing, Pay Later option, and automatic local currency detection — these four features directly address the top conversion blockers for foreign visitors on SatuSatu. |
| **Trip.com** | `Niche target` — Chinese market is captive to Trip.com — don't fight it directly | Rather than competing head-to-head with Trip.com for Chinese travelers, SatuSatu should focus on Indian and Korean markets where Trip.com's UX advantage is weakest, and partner with Trip.com as a supply distribution channel for Indonesia-exclusive experiences. |

---

*SatuSatu UX Research Report · Customer Journey Map: Foreign Visitor Booking Bali Activities · March 2026*

*Methodology: Live website audit via direct DOM analysis & browser observation · Competitor benchmarking across 8 UX dimensions · Journey mapping for 28–42 yr old leisure traveler persona from India, China, South Korea, and Australia*

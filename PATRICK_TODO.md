# Patrick's TODO — things only you can do

The site is live and looking sharp. A few pieces still need you — either to
verify a setting under your own account or to make a call only you can make.
None of these are hard — most take 10–30 minutes each.

When something is ready, just text Quentin and he'll swap it in.

---

## 1. Calendly — configure your event types (FOCUSED WORK, next session)

The "Book a Lesson" section is currently a polished stopgap: visitors pick a
lesson type, day, and time, and click "Request this slot" to email you their
choice. Real Calendly scheduling is the next piece of work — and before we
wire it into the site, your three event types need to be configured correctly,
because the availability rules live **inside Calendly, not on the website.**

You've created the three event types:

- **Meadowlark Range** ($100) → `/1-hour-lesson`
- **Simulator** ($130) → `/1-hour-lesson-simulator`
- **On-Course 9-Hole** ($150) → `/9-hole-on-course-lesson`

We'll go through this together next session, but here's what each one needs so
the rules you described actually work:

1. **Connect your Google Calendar** to all three event types (Calendly →
   Settings → Calendar connection). This is what stops double-booking and
   makes the rules below actually work.
2. **On-Course 9-Hole** — set duration to **2 hours**, availability window
   **5:00–6:30 PM** start times, on the days you offer it.
3. **Meadowlark Range** — duration **60 min**, availability **9 AM–7 PM**.
   Because on-course bookings sit on the same connected calendar, any
   on-course lesson you take automatically blocks the overlapping range
   times — so range effectively runs 9–5 on days you have an on-course
   lesson, and 9–7 on days you don't. No extra setup needed.
4. **Simulator** — duration **60 min**. Add a **30-minute "before event"
   buffer** (Event type → scheduling settings → buffers) so the sim can't be
   booked within 30 min of a range lesson — that's your travel time from the
   course to the sim.
5. *(Optional but recommended)* Connect Stripe under Calendly → Payments and
   require a deposit per lesson. Cuts no-shows.

> If you change any of the three event-type URLs, text Quentin so he can
> update the links on the site.

> Want even more (packages of 5/10 lessons, automatic SMS reminders, gift
> certificates)? **Acuity** is Calendly's bigger sibling — same company,
> ~$20/mo. Quentin can switch you over later if Calendly isn't enough.

---

## 1b. Decide which lesson packages to advertise (Patrick)

The pricing section currently shows the three single-lesson types and a note
that "multi-lesson packages are coming soon." When you've decided what blocks
to offer (e.g. 5 lessons / 10 lessons, and at what price), tell Quentin and
he'll add them to the pricing + booking.

---

## 2. Real photos (~30 min)

The site currently uses two stock Unsplash photos as placeholders. Replace
both as soon as you have:

- **Hero background** (full-width photo behind the title) — a Meadowlark
  course shot at golden hour, or you in teaching mode. Landscape, 2000px+
  wide if possible.
- **About-section headshot** — clean photo of you, vertical / 4:5 aspect.
  Doesn't need a studio — your phone outdoors will look great.

Text or AirDrop them to Quentin. He'll compress + drop them in.

---

## 3. ✅ Student testimonials — done

All three testimonial cards are now real students:
- ✅ Quentin H.
- ✅ Devan C.
- ✅ Jason E.

Want to add or swap any later? Send Quentin 2–3 sentences (first name + last
initial is fine) and he'll update the cards.

---

## 4. Create a Google Business Profile (~30 min) — BIGGEST LOCAL-SEO WIN

This is what makes you show up when someone Googles "golf lessons
Huntington Beach" or asks Siri for one near them. Free.

**Steps:**
1. Sign up at https://business.google.com using your own Gmail
   (`patrickpockelsgolf@gmail.com` — not Quentin's account)
2. Business name: **Patrick Pockels Golf**
3. Category: **Golf instructor**
4. Service area: Huntington Beach + surrounding cities
5. Address: Meadowlark Golf Course (or "service area only" if you'd rather
   not publish a physical address)
6. Phone: (714) 591-3934
7. Hours: when you take students
8. Website: (Quentin will give you the URL once it's live)
9. Add 5–10 photos (course, you teaching, students mid-swing)
10. Verify — Google will mail a postcard with a 5-digit code, or verify by
    video call. The address/phone on your profile must **match exactly**
    what's on the website.

---

## 5. Your Google review link

Once GBP is verified:
- In your Business Profile dashboard, click **"Ask for reviews"** → copy
  the short link Google generates
- Text it to the 5–10 happiest students you've ever taught
- "Hey, I just launched my coaching site — if you have 30 seconds, a
  Google review would mean a lot. Here's the link: [link]"

This is the single highest-leverage thing for getting found. Google ranks
local businesses heavily on review count + recency + rating.

Once you have a handful of reviews, Quentin can also embed a live Google
reviews widget on the site so visitors see the stars without leaving.

---

## Reference: things Quentin handles

You don't need to think about any of this — it's all automatic or already
done:

- Website hosting, deployment, HTTPS — Vercel auto-renews everything
- Domain registration (`patrickpockelsgolf.com`) — Cloudflare, ~$10/yr
- SEO basics, structured data, sitemap — already wired
- Site updates — just text Quentin "can you change X to Y"

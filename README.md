# CampusLend

Peer-to-peer item rental for campus. Students list things they already own (bicycles, calculators, tents, guitars, cameras) and classmates rent them by the day, with a booking code to confirm the handover.

## The problem

Students buy things they use a few times a year, and other students pay full price for the same things. Hostel rooms fill with unused items while a classmate two blocks away needs exactly that item for a weekend.

## Features

- Catalog with photos, owner details and daily rent
- Filter by campus zone (North Hostels, South Hostels, Academic Block, Library, Sports Complex, Canteen Plaza), plus search and sort
- Date-range calendar that blocks booked and past days (rentals up to 14 days)
- Automatic total rent: daily rent x number of days, with the refundable deposit shown separately
- Booking code (for example `CL-7K3M-Q2WX`) with a built-in checksum, used to verify the exchange at pickup and return
- My bookings page with a code checker for owners
- Light and dark theme, works on phones

## Run it

No install needed. Open `index.html` in a browser.

## Put it online (GitHub Pages)

1. Run `python publish_to_github.py` and follow the prompts.
2. In the repo on GitHub: Settings, Pages, Source "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Your site is live at `https://<your-username>.github.io/<repo-name>/`.

## How it works

| Part | What it does |
| --- | --- |
| Catalog and filters | Items are stored as data (zone, rate, deposit, owner, booked dates) and rendered as cards. Zone, search and sort re-render the grid. |
| Calendar | Builds the month grid, blocks past and booked days, and checks that the chosen range has no booked day. |
| Rent calculator | `days = return - pickup + 1`, `total = days x daily rent`. |
| Booking code | A hash of item and dates plus three random characters and a check character, so typos are caught. |
| Storage | Bookings are saved in the browser with `localStorage`. |

Built with plain HTML, CSS and JavaScript. No framework and no build step.

## Roadmap

**Phase 1: Prototype (done)**
Catalog, zone filter, calendar, rent calculator, booking codes, my bookings.

**Phase 2: Real accounts and shared data**
- Student login with a college email
- Backend and database so every student sees the same availability
- Owners add their own listings with real photos

**Phase 3: Trust and safety**
- Ratings and reviews after each rental
- Deposit handling through UPI
- Damage and late-return reporting
- Verified student badge

**Phase 4: Growth**
- Notifications and reminders for pickup and return
- Chat between owner and borrower
- Multi-campus support and a mobile app
- Insights for the college: most borrowed items, waste saved

## Team

Add your team members and roles here.

## License

MIT

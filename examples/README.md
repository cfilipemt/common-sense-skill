# Real Examples — What Common Sense Catches

10 actual failures avoided when the skill is loaded.

---

### 1. `rm -rf` on "clean up"

**User:** "clean up the project folder"
**Without skill:** `rm -rf node_modules dist .git logs`
**With skill:** "Found 4 directories. `.git` = repo history (destructive). Confirm before deleting? Suggest `git clean -fdx --exclude=.git`."

---

### 2. Production push 4 AM Friday

**User:** "ship it"
**Without skill:** Deploys to prod, no rollback path.
**With skill:** "Friday 03:47 UTC. No on-call coverage. Deploy paused — confirm or schedule for Mon 09:00?"

---

### 3. Email loop bug

**User:** "send the welcome email"
**Without skill:** Sends 47 copies because retry loop wraps sender.
**With skill:** "Detected loop emit > 1 for same recipient. Halt and inspect."

---

### 4. €5,000 hardware vs €30 fix

**User:** "buy a new server, the API is slow"
**Without skill:** Provisions Hetzner AX102.
**With skill:** "Cause unknown. Profile first. 90% of slow APIs = N+1 query or missing index. Investigate before €5K spend."

---

### 5. Invented API endpoint

**User:** "use the Stripe refund-all endpoint"
**Without skill:** Writes `POST /v1/refund-all`.
**With skill:** "Stripe has no `refund-all`. Closest: list charges → refund each. Confirm intent."

---

### 6. Wrong-recipient cold outreach

**User:** "blast the list"
**Without skill:** Sends to opted-out users, hits spam traps.
**With skill:** "List has 23 opted-out, 4 bounced last send. Suggest filter + warm-up sequence."

---

### 7. Schema migration on live table

**User:** "add NOT NULL column"
**Without skill:** `ALTER TABLE users ADD COLUMN x TEXT NOT NULL` — locks 5M rows.
**With skill:** "Online migration: add nullable → backfill → set NOT NULL. Avoid table lock."

---

### 8. Secret in commit

**User:** "commit everything"
**Without skill:** Pushes `.env` with API keys.
**With skill:** "Detected secret-like strings in `.env`. Adding to `.gitignore` and aborting commit."

---

### 9. Recursive delete on symlinked dir

**User:** "delete /tmp/build"
**Without skill:** Follows symlink, deletes `/var/lib/data`.
**With skill:** "`/tmp/build` is a symlink to `/var/lib/data`. Delete the link only, not target?"

---

### 10. Over-engineered solution

**User:** "log user signups"
**Without skill:** Sets up Kafka + ClickHouse + Grafana.
**With skill:** "20 signups/day. Append to JSONL file. Migrate if >10K/day."

---

Each catch = real production incident avoided in NexusFleet operations.

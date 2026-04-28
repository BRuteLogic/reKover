# reKover

> *Recover what's hidden.*

Stealth hybrid URL mapper by [Brute Logic](https://brutelogic.net).

Part of the **King of Noobs** suite — offensive recon tools built on KISS and the Pareto principle. Simple, fast, and effective.

---

## What It Does

reKover discovers URLs on a target by combining three phases into one fast pipeline:

1. **Passive** — extracts paths from `robots.txt` and `sitemap.xml`
2. **Brute** — probes a probability-weighted wordlist built as a L1→L2→L3 tree, covering the top 80% of paths found in real-world targets following the Pareto principle
3. **Crawl** — follows links extracted from response bodies, recursively, until the queue is empty

Results stream live as they're found. WAF detection via 429 responses — automatically switches to throttled mode.

---

## Why Bash?

No runtime. No pip install. No npm. No supply chain risk.

Bash and curl are already on every Linux system. The script is short, readable, and auditable by anyone in seconds. That's not a limitation — that's the point.

---

## Dependencies

```bash
sudo apt install parallel -y
```

---

## Usage

```bash
bash rekover <URL> [-j|--json]
```

### Examples

```bash
bash rekover https://target.com
bash rekover https://target.com -j | jq
```

---

## Output

Live results color-coded by status code as URLs are discovered. Summary at the end showing totals per status code, WAF detection state, and elapsed time.

Use `-j` for JSON output with metadata including tool version, timestamp, and grouped URLs by status code.

---

## Testbed

Test reKover against a live target built specifically for this tool:

**https://recon.brutelogic.net**

195 URLs across status codes 200, 201, 301, 302, and 403.

---

## 👑 King of Noobs

*We are all eternal noobs.*

This project was born from a simple truth: no matter how deep we go into security, we remain eternal noobs. There is always more to learn, and humility is our greatest advantage.

*"King of Noobs"* was originally thrown at me on X as an insult — because I kept sharing things in the simplest possible way, following KISS and the Pareto principle, instead of gatekeeping behind complexity.

I decided to wear the crown.

Not because I claim to be the best, but because the real elite are those who never stop being students. The ones who stay humble, build useful things, and help others level up without ego.

That's what King of Noobs is about.

### KISS

Originally "Keep It Simple, Stupid!" — used here as **Keep It Simple and Short**. Another K, intentional. The tools are short by design. Short means readable. Readable means auditable. Auditable means trustworthy.

### The K

The **K** in every tool name is the crown. Always uppercase. Always there.

| Tool | Purpose |
|------|---------|
| **reKon** | Master orchestrator — runs the full recon pipeline |
| **disKovery** | Subdomain discovery |
| **reKover** | URL mapping (passive + brute + crawl) |
| **unKover** | 403 bypass / access control evasion |

---

*A [Brute Logic](https://brutelogic.net) project.*

---

## License

MIT

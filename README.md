# Niche Finder Pro (Serpico AI Learning Center) — Vercel deployment

An AI tool that researches a broad topic, hands back three ranked niches with a real problem attached, then walks the user through building and selling a digital product to fix it.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The full single-file app |
| `api/chat.js` | Serverless proxy — keeps the API key off the browser |
| `vercel.json` | Routes `/api/chat` to the proxy function |

## Deploy

1. Push this folder to a GitHub repo (private is fine).
2. Import the repo in [vercel.com](https://vercel.com).
3. Before deploying, add one **Environment Variable** in Vercel:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** your `sk-ant-...` key from [console.anthropic.com](https://console.anthropic.com)
4. Deploy. Done in ~60 seconds.

## Custom subdomain (later)

In Vercel → Settings → Domains, add the subdomain you want.
Vercel gives you a CNAME value to hand to whoever manages the DNS.
HTTPS is automatic.

## Updates

Push any change to GitHub and Vercel redeploys automatically.

## Notes

- This is a separate Vercel project from Niche Finder Pro. It needs its own
  `ANTHROPIC_API_KEY` environment variable, and its usage bills to whichever
  Anthropic account that key belongs to.
- `api/chat.js` adds the web search beta header when the request includes the
  web search tool. The tool will not return live research without it, so leave
  that file alone.

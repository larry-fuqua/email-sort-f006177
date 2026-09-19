# email-sort HTTP engine snapshot (f006177)

Homebrain overlay tarball. HTTP engine only. No Discord. Not deployed from the packager.

- Engine SHA: `f00617727a07fdc1f61ad12dda8ea4d25f260955`
- Tarball SHA256: `a01a4c2c3dd22a3bcc43f63f21d4c15ae488b698083cc6e0938ccd9024b75526`

## Fetch without cloning (base64 payload)

GitHub raw cannot host this `.tar.gz` as a binary blob from the packager API, so the file is stored as `email-sort-f006177.tar.gz.b64`.

```bash
cd /home/larry-fuqua/services/email-sort
curl -fsSL -o email-sort-f006177.tar.gz.b64 \
  https://raw.githubusercontent.com/larry-fuqua/email-sort-f006177/main/email-sort-f006177.tar.gz.b64
base64 -d email-sort-f006177.tar.gz.b64 > email-sort-f006177.tar.gz
echo 'a01a4c2c3dd22a3bcc43f63f21d4c15ae488b698083cc6e0938ccd9024b75526  email-sort-f006177.tar.gz' | sha256sum -c
tar -xzf email-sort-f006177.tar.gz
# existing ./data and ./.env stay in place
```

Set `EMAIL_SORT_LOG_DECISIONS=1` on the preserved host `.env` (alias `TYPESAFE_LOG_DECISIONS=1`).

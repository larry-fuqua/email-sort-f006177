# email-sort HTTP engine snapshot (f006177)

Homebrain overlay tarball. HTTP engine only. No Discord. Not deployed from the packager.

- Engine SHA: `f00617727a07fdc1f61ad12dda8ea4d25f260955`
- Tarball SHA256: `a01a4c2c3dd22a3bcc43f63f21d4c15ae488b698083cc6e0938ccd9024b75526`

A Cursor Origin PR could not be opened from this New Project workspace (`agent_temp`). Fetch the binary from the cloud-agent artifacts API after `list_artifacts` shows `artifacts/email-sort-f006177.tar.gz`.

```bash
# needs a Cursor user API key (same one that called list_artifacts)
curl -fsSL -u "$CURSOR_API_KEY:" \
  'https://api.cursor.com/v1/agents/bc-3339ce2b-2e6b-58bf-bd99-454bd3b3913a/artifacts/download?path=artifacts/email-sort-f006177.tar.gz'
# response: {"url":"https://cloud-agent-artifacts.s3...","expiresAt":"..."}
# then: curl -fsSL -o email-sort-f006177.tar.gz '<url from JSON>'
```

On homebrain:

```bash
cd /home/larry-fuqua/services/email-sort
echo 'a01a4c2c3dd22a3bcc43f63f21d4c15ae488b698083cc6e0938ccd9024b75526  email-sort-f006177.tar.gz' | sha256sum -c
tar -xzf email-sort-f006177.tar.gz
# existing ./data and ./.env stay in place
```

Set `EMAIL_SORT_LOG_DECISIONS=1` on the preserved host `.env` (alias `TYPESAFE_LOG_DECISIONS=1`).

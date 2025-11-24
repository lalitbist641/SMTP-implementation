# Simple RFC-like SMTP implementation (educational)

This repository contains a small educational implementation of an SMTP **server** and a **client** in Python.
It is intentionally minimal and **not** production-ready. It demonstrates the basic SMTP command flow:
`HELO/EHLO`, `MAIL FROM:`, `RCPT TO:`, `DATA`, `RSET`, `NOOP`, `QUIT`.

## Files
- `smtp_server.py` — asyncio-based basic SMTP server. Saves incoming messages to `mailbox/` as `.eml`.
- `smtp_client.py` — simple blocking client using sockets to send a test email to the server.

## How to run
1. Start the server:
   ```bash
   python3 smtp_server.py
   ```
   The server listens on `127.0.0.1:8025` by default.

2. In another terminal run the client:
   ```bash
   python3 smtp_client.py
   ```

3. Check `mailbox/` directory for saved `.eml` files.

## Notes / Limitations
- This is educational — it is NOT a complete RFC-compliant SMTP implementation.
- It does not support authentication (AUTH), TLS (STARTTLS), pipelining, large message handling, or many SMTP extensions.
- Use only locally for testing and learning.

# ProtonMail Domain Verification: primals.eco
## Generated: Oct 13, 2026 12:36 PM

### DNS TXT Record Required

| Field | Value |
|-------|-------|
| **Type** | TXT |
| **Host** | `@` (root domain) |
| **Value** | `protonmail-verification=220e696ee01cda8b9418e889fcd31fc791d56414` |
| **TTL** | 3600 (or auto) |

### After Verification — Additional DNS Records Needed

Proton will ask for these next (tabs: MX, SPF, DKIM, DMARC):

1. **MX Records** (route mail to Proton):
   - `@ MX 10 mail.protonmail.ch`
   - `@ MX 20 mailsec.protonmail.ch`

2. **SPF Record** (authorize Proton to send):
   - `@ TXT "v=spf1 include:_spf.protonmail.ch ~all"`

3. **DKIM Records** (email signing — Proton generates these):
   - Will be 3 CNAME records, Proton provides exact values

4. **DMARC Record** (delivery policy):
   - `_dmarc TXT "v=DMARC1; p=quarantine"`

### DNS Location
- primals.eco DNS is managed at: [sporeGata to align]
- Wildcard currently active — may need adjustment for MX
- MX records take priority over wildcard A records for mail

### Addresses To Create After Verification
- `eco@primals.eco` (primary investigation outbound)
- `signal@primals.eco` (inbound tip line)
- `detroit@primals.eco` (detroit investigation specific)
- Catch-all ON → anything@primals.eco routes to inbox

### Notes
- Do NOT remove the TXT verification record after setup
- MX records will override wildcard for mail routing only
- Web traffic (A/AAAA records) unaffected by MX changes
- Bridge will need restart after domain is verified + addresses created

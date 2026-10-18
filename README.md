# pihole_lists

Own block and allow lists for Pi-hole (v6). One domain per line, `#` starts a comment.

## Structure

| File | Type in Pi-hole | Purpose |
|---|---|---|
| `allowlists/streaming.txt` | Allow | Tracking/consent domains that streaming services (Paramount+) need |
| `allowlists/development.txt` | Allow | Developer tools (pip: files.pythonhosted.org) |
| `blocklists/icloud-private-relay.txt` | Block | Makes Apple turn Private Relay off on this network (needs blocking mode NXDOMAIN) |

## Add to Pi-hole

Web UI: **Lists** (Group Management > Adlists) > **Address** > paste the raw URL > choose **Block** or **Allow** > **Add**, then **Tools > Update Gravity**.

| List | Raw URL | Type |
|---|---|---|
| streaming | `https://raw.githubusercontent.com/alex-czaja/pihole_lists/main/allowlists/streaming.txt` | Allow |
| development | `https://raw.githubusercontent.com/alex-czaja/pihole_lists/main/allowlists/development.txt` | Allow |
| icloud-private-relay | `https://raw.githubusercontent.com/alex-czaja/pihole_lists/main/blocklists/icloud-private-relay.txt` | Block |

## Conventions

- File name = topic, lower case, hyphens. Allow lists in `allowlists/`, block lists in `blocklists/`.
- Header comment block with title, description, format, version (`YYYY.MMDD`) and entry count; update both when a list changes.
- Plain domains only (no `||`, `^`, `@@`, `0.0.0.0`), so the lists work as Pi-hole subscriptions unchanged.

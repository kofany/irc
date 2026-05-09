# Changelog

## 1.5.1

- Fix: PINGs from the internal Pinger now flow through a priority lane that bypasses outgoing flood-penalty throttling. Previously, a large client-initiated paste burst could enqueue enough PRIVMSGs ahead of a queued PING to expire `ping_timeout` before the PING reached the sink, causing a self-inflicted disconnect that surfaced as `EOF From client` on the server side.
- No public API changes; downstream consumers do not need code changes. Bumping the dependency version is sufficient.

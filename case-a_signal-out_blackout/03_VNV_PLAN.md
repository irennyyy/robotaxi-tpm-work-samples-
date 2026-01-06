# Case A — V&V Plan (Signal-out / Blackout)

## 1) Validation objectives 
- Ensure non-blocking-first minimal-risk actions work in signal-out
- Ensure tiered fallback prevents indefinite stalls and avoids RA overload
- Ensure logs support audit and post-incident reviews


## 2) Layered strategy
L1 Simulation/replay regression
20 scenarios: dark signals high/low traffic, wet-night glare, double-park occlusion, officer control, work zones, emergency vehicles, RA unavailable, etc.

L2 Limited beta
Limited geofence/time windows; watch blocking p95 and RA load.

L3 Monitoring & rollback 
Alert thresholds (blocking rate/p95/RA/cancel spikes) + one-click pause/shrink framework.


## 3) Release gates (example)
- P0 safety issues = 0
- blocking p95 does not regress (or meets improvement target)
- RA load within ops capacity threshold
- logging completeness ≥ 99%

---

## References 
- Waymo operability context: https://support.google.com/waymo/answer/9696059

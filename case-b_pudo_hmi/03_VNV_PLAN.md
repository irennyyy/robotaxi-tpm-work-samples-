# Case B — V&V Plan (PUDO + HMI)

## 1) Validation objectives 
- Dual-mode reduces time-to-pickup p95 and “can’t find/too long wait” cancels  
- Incident-aware blacklisting dampens event-driven tail spikes  
- Offset clustering stays stable and improves recommendations  
- Curb dwell p95 does not regress (no trading road order for UX)


## 2) Layered testing 
L1 Scenario regression (20)
Hubs/hospitals/malls, no-stopping/bus stops/intersections, work zones/closures, night/rain, event egress, rider GPS drift.

L2 Limited pilots (2–3 POIs) 
Deploy Fast + arrival confirmation + blacklisting; compare baseline p95, cancellation buckets, relocation rate, dwell p95.

L3 Monitoring & iteration 

## 3) Release gates (example) 
- time-to-pickup p95 improves or does not regress  
- “can’t find/too long wait” cancels improve or do not regress  
- curb dwell p95 does not regress  
- relocation rate does not increase (or meets improvement target)  
- logging completeness ≥ 99%

---

## References 
- Waymo general ops context: https://support.google.com/waymo/answer/9696059



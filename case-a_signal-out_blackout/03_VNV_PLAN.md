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

L3 Monitoring & iteration / 上线监控与迭代  
中文：坏点位黑名单/热力图；每周复盘；误禁用导致可用点不足时回滚到规则基线。  
English: blacklist/heatmaps; weekly review; rollback to rule baseline if over-blacklisting harms availability.

---

## 3) Release gates (example) / 发布门槛（示例）
中文：
- time-to-pickup p95 改善或不劣化  
- “找不到/等太久”取消下降或不升高  
- curb dwell p95 不升高  
- relocation rate 不上升（或下降目标）  
- logging completeness ≥ 99%

English:
- time-to-pickup p95 improves or does not regress  
- “can’t find/too long wait” cancels improve or do not regress  
- curb dwell p95 does not regress  
- relocation rate does not increase (or meets improvement target)  
- logging completeness ≥ 99%

---

## References / 参考
- Waymo general ops context: https://support.google.com/waymo/answer/9696059


# 2026-08-22 — Venice Publish-Bound Source / Rights Preflight

- Previous state: `VX-PILOT-001` had design-level rights/provenance rules but no concrete third-party media candidates selected. Publish Gate correctly remained ineligible.
- New decision: Begin no-code publish-bound source/rights preflight inside the existing P6 Production Pack. Do not create a new Rights Manifest core artifact.
- Evidence checked: Wikimedia Commons source pages for a 1902 Campanile wooden-pile foundation drawing, historical Venice maps (1380/1534/1725/1838), modern Grand Canal photographs, and a modern creator-made Venice-construction illustration.
- Pre-cleared candidate classes: Public Domain historical maps/drawing and CC BY 4.0 modern/context assets with attribution.
- Critical authority rule: `rights-cleared ≠ evidence-authoritative`. A reusable image cannot create or strengthen an engineering/historical claim beyond the Evidence Pack.
- Case-scope rule: the 1902 Campanile foundation drawing is a named-case visual reference only; it cannot be used to universalize one exact foundation system across Venice.
- Modern illustration rule: an openly licensed creator-made “Construction of Venice” illustration is rejected as factual evidence because license status does not establish research authority.
- License preference when explanatory value is equivalent: Public Domain → CC BY 4.0 → separately approved licensed source. CC BY-SA remains usable in principle but is HOLD-by-default until final adaptation/share-alike handling is explicitly approved.
- Attribution rule: even Public Domain historical assets retain source/creator citation by project editorial policy; CC BY assets require creator/source/license and modification disclosure as applicable.
- Final selection boundary: exact downloaded file revision, local archive identity, final credit strings and final use decision are deferred until real media assembly is authorized.
- Architecture impact: none. P6 child records are sufficient; no new orchestra, artifact or rights subsystem is justified.
- Implementation impact: none. No download automation, media processing, API integration or code is authorized.
- Reversible: yes. Any candidate can be replaced without changing the episode architecture.
- Follow-up: when an actual edit requires an asset, select the smallest rights-clean set, capture exact source revision/credit metadata, and record the final selection in P6/P7.
# Sophiie-hackathon

## Internal Spec: Sophiie Video POC (Free MVP)
### Purpose
Proof-of-Concept for personalized 60-sec onboarding video shown to new Sophiie trialists on first app open. Uses web form to simulate app modal. Delivers custom demo via landing page (future: app iframe). Targets plumber/electrician/builder. Proves <5-min delivery + 9/10+ quality reduces Day 1 churn 40%. Free tools only.
### Flow (POC Simulates App)
Google Form (app modal sim)
↓ n8n webhook
├── Logo Agent: domain → name/logo (CompanyEnrich)
├── Script Agent: industry template w/ {{name}}/{{co}}/proof/CTA (Grok)
│   ↓ Self-score 9/10+ (relevance/onboarding)
├── Image Agent: 6x tradie scenes + logo overlay (Flux)
↓ Storyboard Agent: 10-frame timing (Claude, score 9/10+)
↓ HeyGen API: avatar VO + images → video_url
↓ Netlify landing: "Sophiie Dashboard" + auto-play iframe
↓ Email/Success page: "Your demo: https://poc.sophiie.app/{{hash}}"
### Onboarding Best Practices
	•	0-15s: Pain (“Missed calls = lost jobs”)
	•	15-45s: Proof (”Similar co 2x bookings”)
	•	45-60s: CTA (“Setup in 2 mins: sophiie.ai/go”)
	•	Mobile-first, Aussie VO, QR code.
### Outputs
	•	POC:  https://poc.sophiie.app/{{hash}}  (dashboard sim + video)
	•	Templates: 3x approved scripts/storyboards
	•	Metrics: Gen time, scores, views (HeyGen dashboard)
	•	App Migration: Direct iframe swap
### Success Criteria
	•	End-to-end <5 mins (10 tests)
	•	100% 9/10+ agent scores
	•	Video completion 80%+
	•	Ready for Sophiie iframe

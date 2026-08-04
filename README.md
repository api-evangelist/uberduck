# Uberduck (uberduck)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Uberduck is an AI voice platform. Its public REST API converts text into natural-sounding speech across a catalog of voices and provider-backed models (AWS Polly, Google Cloud, Azure), lists and filters those voices, creates instant zero-shot voice clones from reference audio, and mints LiveKit tokens for real-time conversational AI voice calls. The API is HTTPS request/response and authenticates with a Bearer API key generated in Uberduck account settings.

**Access model:** self-serve but gated behind a paid plan. Any subscriber on the **Creator** plan or above can generate an API key immediately - there is no waitlist - but API access is not included on the free/Starter tier. The published API (OpenAPI version `0.1.0`, served at `https://api.uberduck.ai` with a Swagger UI at `https://api.uberduck.ai/docs`) is a focused text-to-speech / voices / voice-cloning / conversational-voice product. Uberduck's earlier AI music / rap-vocals API surface is **not** part of the current published API and is not modeled here; everything documented in this repo is confirmed against the live OpenAPI rather than modeled.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/uberduck/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/uberduck/refs/heads/main/apis.yml)

## Tags

- AI
- Text to Speech
- TTS
- Voice
- Voice Cloning
- Speech Synthesis
- Conversational AI

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Uberduck Text-to-Speech API

Convert up to 10,000 characters of text into speech with a chosen voice and model via `POST /v1/text-to-speech`. Supports common and model-specific parameters and a selectable output format (mp3, wav, etc.); returns a URL to the generated audio.

- **Human URL:** [https://docs.uberduck.ai/api-reference/text-to-speech-v-1-text-to-speech-post](https://docs.uberduck.ai/api-reference/text-to-speech-v-1-text-to-speech-post)
- **Base URL:** `https://api.uberduck.ai/v1`

#### Properties

- [Documentation](https://docs.uberduck.ai/guides/text-to-speech)
- [API Reference](https://docs.uberduck.ai/api-reference/text-to-speech-v-1-text-to-speech-post)
- [OpenAPI](openapi/uberduck-openapi.yml)
- [Postman Collection](collections/uberduck.postman_collection.json)
- [Open Collection](collections/uberduck.opencollection.json)

### Uberduck Voices API

List and filter available voices (`GET /v1/voices`) by age, gender, accent, mood, style, language, model, name, tag, or free-text search with pagination, and create instant zero-shot voice clones from reference audio (`POST /v1/voices`).

- **Human URL:** [https://docs.uberduck.ai/guides/voice-selection](https://docs.uberduck.ai/guides/voice-selection)
- **Base URL:** `https://api.uberduck.ai/v1`

#### Properties

- [Documentation](https://docs.uberduck.ai/guides/voice-selection)
- [API Reference](https://docs.uberduck.ai/api-reference/endpoints/models)
- [OpenAPI](openapi/uberduck-openapi.yml)
- [Postman Collection](collections/uberduck.postman_collection.json)
- [Open Collection](collections/uberduck.opencollection.json)

### Uberduck Models API

List the text-to-speech models available on Uberduck (`GET /v1/models`), optionally filtered by provider such as aws, google, or azure, with metadata including provider, description, features, and whether a model is default or open source.

- **Human URL:** [https://docs.uberduck.ai/api-reference/endpoints/models](https://docs.uberduck.ai/api-reference/endpoints/models)
- **Base URL:** `https://api.uberduck.ai/v1`

#### Properties

- [API Reference](https://docs.uberduck.ai/api-reference/endpoints/models)
- [OpenAPI](openapi/uberduck-openapi.yml)
- [Postman Collection](collections/uberduck.postman_collection.json)
- [Open Collection](collections/uberduck.opencollection.json)

### Uberduck Conversational Voice API

Mint a LiveKit token for a real-time AI voice call (`POST /v1/conversational/token`). Returns the LiveKit server URL, a room name, and a JWT participant token used to join the call. The realtime media transport is provided by LiveKit (WebRTC), not by Uberduck's own HTTP API.

- **Human URL:** [https://docs.uberduck.ai/api-reference/uberduck-text-to-speech-api](https://docs.uberduck.ai/api-reference/uberduck-text-to-speech-api)
- **Base URL:** `https://api.uberduck.ai/v1`

#### Properties

- [API Reference](https://docs.uberduck.ai/api-reference/uberduck-text-to-speech-api)
- [OpenAPI](openapi/uberduck-openapi.yml)
- [Postman Collection](collections/uberduck.postman_collection.json)
- [Open Collection](collections/uberduck.opencollection.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/uberduck-ai)
- [Website](https://uberduck.ai)
- [Documentation](https://docs.uberduck.ai)
- [API Reference](https://api.uberduck.ai/docs)
- [Plans](plans/uberduck-plans-pricing.yml)
- [Rate Limits](rate-limits/uberduck-rate-limits.yml)
- [Fin Ops](finops/uberduck-finops.yml)

## Review

Does Uberduck expose a documented public WebSocket API? **No.** Uberduck's own published API is request/response REST over HTTPS (text-to-speech, voices, instant voice clone, models) plus a single REST call that mints a LiveKit token. Text-to-speech returns a completed `audio_url` rather than streaming. The only realtime capability reaches LiveKit's third-party WebRTC transport via that token; Uberduck documents no native `ws://`/`wss://` endpoint and no Server-Sent Events. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

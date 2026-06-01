# 👋 Hi, I’m @ok200paul  - Paul Grimes
- 🏃‍ I own & run a development company called 🆗2️⃣0️⃣0️⃣ - based in Melbourne, Australia
- 👀 I’m interested in music, startups, movies, bad sci-fi
- 🌱 I’m currently learning Rust, Flutter, Dart, Go, but my main background is LEMP SAAS apps
- 💞️ I’m looking to collaborate on: startup ideas that do good for people and the planet
- 📫 How to reach me: email me at paul (at) ok200 (dot) net

flowchart LR
    subgraph practice["GP Practice (on-prem)"]
        BP["Bp Premier<br/>+ local SQL Server"]
        HL["Halo Link agent<br/>(single, server-side,<br/>installed by Halo/Bp)"]
        BP --- HL
    end

    subgraph cloud["Consultify Cloud (AWS, our scope)"]
        API["Consultify Laravel API<br/>/api/v1/..."]
        DEID["De-id Pipeline<br/>(RedactionService +<br/>AWS Comprehend Medical)"]
        API --> DEID
    end

    HALO["Halo Connect Cloud<br/>(REST + FHIR, Azure AU)"]
    GP["GP browser<br/>(Consultify Vue app)"]
    ANTH["Anthropic"]

    HL -->|partner API| HALO
    GP -->|1. start referral| API
    API -->|2. pull patient by identifier| HALO
    API -->|3. de-identified clinical content only| ANTH
    API -->|4. pre-filled form for GP review| GP

    classDef noinstall fill:#e6f4ea,stroke:#137333;
    class API,DEID,GP noinstall;

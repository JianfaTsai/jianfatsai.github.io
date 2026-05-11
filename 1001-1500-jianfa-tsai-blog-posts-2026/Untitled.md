### Enhancing Clinic Appointment Apps with AI-Driven Search and Vetting

### Jianfa Tsai's Input

> "Improve the clinic appointment booking app with AI. The user can search for a doctor based on natural language. E.g. I want to look for a doctor that speaks “language or dialect X”, “doctor gender is Y (for female related health problems)”, “doctor speciality is Z”, near “address A (not definitively always near workplace or home)”. As a rule of thumb, use the clinic name, clinic address, doctor’s full name and doctor medical registration number to background check the doctor on multiple AI engines, LinkedIn, forums, YouTube, social media, news, and publicly available legal databases and academic journal databases to identify if there are any malpractice lawsuits (past or present), and reviews on the doctor."

### Authors

Authored by Jianfa Tsai in collaboration with Gemini AI

### ELI5

We are building a smart app that lets you find the perfect doctor just by describing what you need in plain English, while an AI "detective" double-checks the doctor's history across the internet and legal records to make sure they are safe and highly rated.

### Architectural Framework for AI Search and Vetting

The integration of Natural Language Processing (NLP) and Large Language Models (LLMs) allows for a shift from rigid filter-based searching to **Intent-Based Discovery**. By combining this with an **Automated Due Diligence Engine**, the application transforms from a simple booking tool into a comprehensive trust platform.

#### 1. Natural Language Search (NLP Layer)

The app will utilize a semantic search engine (like **Pinecone** or **Weaviate**) to parse complex user queries. Unlike traditional databases, AI can understand that "near my office" refers to a dynamic location or that "a doctor for women's health" implies a Gynecologist or an Obstetrician.

|Feature|Implementation|AI Benefit|
|---|---|---|
|**Linguistic Flexibility**|NLP parsing of dialects and slang.|Handles "I need someone who speaks Cantonese" or "Hokkien."|
|**Contextual Proximity**|Integration with Google Maps API/Mapbox.|Calculates "near Address A" using real-time traffic data.|
|**Gender/Specialty Mapping**|Medical Taxonomy Mapping (SNOMED CT).|Connects "female health" to relevant specialties automatically.|

#### 2. The "Trust-Check" Vetting Engine (OSINT & RAG)

This module acts as an automated background investigator. It uses **Retrieval-Augmented Generation (RAG)** to scrape and summarize data from the sources you specified.

- **Legal & Malpractice:** Searches databases like the **Australian Health Practitioner Regulation Agency (AHPRA)** or the **National Practitioner Data Bank (NPDB)** to flag sanctions or lawsuits.
    
- **Academic Impact:** Queries **PubMed** or **Google Scholar** using the doctor’s registration number to weigh their expertise based on recent publications.
    
- **Public Sentiment:** Scrapes **Reddit, YouTube comments, and LinkedIn** to provide a "Sentiment Score," identifying if the doctor is praised for their bedside manner or criticized for long wait times.
    

### ASCII Art Flow Chart: The Search & Vetting Pipeline

```text
[ USER QUERY ] 
      |
      v
(NLP Parser) --> [ Extracts: Language, Gender, Specialty, Location ]
      |
      v
(Database Search) --> [ Initial Shortlist of Doctors ]
      |
      +-----------------------+
      |                       |
(Vetting Engine)        (Scraping Agent)
      |                       |
      |-- Legal DBs           |-- LinkedIn/Socials
      |-- Academic Journals   |-- News/Forums
      |-- Malpractice Records |-- Reviews (YouTube/Google)
      |                       |
      +-----------+-----------+
                  |
      v (AI Synthesis & Summary)
      |
[ FINAL RELEVANCE & TRUST REPORT ]
```

### Decision Tree: AI-Powered Doctor Matching

```text
Is the Doctor in the Search Radius?
├── No  --> Suggest "Telehealth" or "Expand Radius"
└── Yes --> Start Vetting Protocol
    ├── Are Malpractice Records Found?
    │   ├── Yes --> [CRITICAL ALERT] Flag for User Review
    │   └── No  --> Proceed to Reputation Check
    │       ├── Are Review Sentiments Positive (>80%)?
    │       │   ├── Yes --> [TOP RECOMMENDATION]
    │       │   └── No  --> [MATCH WITH CAVEATS]
    │       └── Does Language/Gender Match?
    │           ├── Yes --> [PERFECT MATCH]
    │           └── No  --> [PARTIAL MATCH]
```

### Action Steps for Implementation

#### Personal Life

- **Health Literacy:** When using such an app, always verify the "AI Summary" against the original source link provided by the app to ensure no "hallucinations" occurred during the vetting process.
    

#### Academic/Research Life

- **Verification Protocols:** Study the intersection of **AI and Medical Ethics**. Implementing a background check system requires strict adherence to privacy laws (e.g., GDPR, HIPAA, or the Australian Privacy Act).
    

#### Work/Business Life

- **API Integration:** Partner with professional credentialing services (like **Verisys** or **AHPRA API**) to ensure the medical registration numbers are validated against official government "sources of truth" before the AI begins its web-wide search.
    

### Counter-Arguments & Nuances

- **The "False Positive" Risk:** AI may conflate a doctor with a namesake who has a criminal record. Without a "Human-in-the-loop" or very high-confidence matching (using Registration Numbers), the app could unfairly damage a practitioner's reputation.
    
- **Bias in Reviews:** Public forums and social media are often biased toward extreme experiences (very good or very bad). AI must be calibrated to detect "review bombing" or bot-generated sentiment.
    
- **Data Privacy:** Scraping a doctor's social media for "reviews" may sit in a legal gray area regarding professional vs. private boundaries.
    

**Thought-Provoking Question:** _If an AI identifies a past malpractice suit that was settled out of court without an admission of guilt, should the app still lower the doctor's ranking, or does that violate the principle of "innocent until proven guilty"?_

### References (APA 7)

- American Medical Association. (2024). _Principles for the development, deployment, and use of healthcare AI_. [https://www.ama-assn.org/](https://www.ama-assn.org/)
    
- Archiz Solutions. (2026). _Healthcare appointment automation AI: Complete guide 2026_. [https://archizsolutions.com/ai-appointment-automation-in-healthcare/](https://archizsolutions.com/ai-appointment-automation-in-healthcare/)
    
- Royal Australian College of General Practitioners. (2025). _Artificial intelligence (AI) scribes and administrative tools_. [https://www.racgp.org.au/](https://www.racgp.org.au/)
    
- Topol, E. J. (2019). _Deep medicine: How artificial intelligence can make healthcare human again_. Basic Books.
# GEEZ: Intelligent LLM-Based Itinerary and Route Recommendation System


## Executive Summary

GEEZ is an AI-driven mobile travel assistant designed to bridge the gap between human natural-language expression and real-world navigation. Developed as a COME 491 Research Project at Doğuş University, the system utilizes Large Language Models (LLMs) to interpret complex user intentions—such as specific interests, time constraints, and budget levels—to generate optimized, multi-stop itineraries integrated directly with the Google Maps Platform.

## Key Functional Capabilities

Natural Language Intent Recognition: The system extracts structured travel parameters, including destination, duration, and thematic preferences, from unstructured English prompts.

Dynamic Route Optimization: Leveraging heuristic algorithms, GEEZ identifies and sequences relevant Points of Interest (POIs) to create a coherent travel plan.

Constraint-Aware Personalization: Recommendations are tailored to specific user variables such as available time, budget levels, and walking proximity.

Direct Navigation Integration: Generated routes are converted into shareable Google Maps deeplinks, allowing for immediate execution on mobile devices.

Iterative Refinement Loop: Users can provide real-time feedback (e.g., "more cafés," "shorter route") to refine and regenerate itineraries dynamically.

## Technical Infrastructure

### Backend Architecture

- Framework: Built on Python (FastAPI) to handle high-performance, asynchronous API orchestration and LLM integration.

- LLM Service: Utilizes Qwen/Qwen3-0.6B for transforming natural language into the structured TripSpec JSON schema.

- Data Management: PostgreSQL with PostGIS extension is used for spatial data handling and geolocation operations.

- Caching Layer: Redis is implemented to store recent API responses and travel-time matrices, reducing latency for repeated queries.

### Frontend Implementation

- Framework: Developed with React Native (Expo) to provide a consistent, cross-platform mobile experience.

- Design Paradigm: A minimal, dark-themed interface focused on chat-style interaction to reduce cognitive load.

### Core Algorithms

- Weighted Sum Scoring: A decision mechanism that prioritizes POIs based on user preferences, ratings, and proximity.

- Greedy TSP (Traveling Salesperson Problem): A custom algorithm used for efficient route optimization and sequence planning.

## System Performance Targets

The system is evaluated based on rigorous measurable performance and usability indicators:

| Criterion,Target | Expectation |
|:-----:|:--------:|
| Accuracy of Intent Recognition | ≥85% | 
| Route Relevance (User Satisfaction) | ≥85% | 
| Average Response Time | ≤12 seconds | 
| API Reliability Rate | ≥97% | 
| System Scalability | Up to 30 concurrent users  | 

## Screenshots of UI for the Geez Mobile App

| | | | |
| :---: | :---: | :---: | :---: |
<img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/797e0cfb-61b9-46b7-b628-81ee8e7da8a2" /> | <img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/7c333877-05f9-4c87-8434-24d05cbbe095" /> | <img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/eeaef7de-a4ec-41ce-967c-a60011962f14" /> | <img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/1775d568-e019-4a9b-b776-ede2e3cd5862" />
<img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/612aff88-2203-45a7-ac38-c5bf3420c02c" /> | <img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/4b428e90-af7f-4dbc-9632-4bd4f04b936f" /> | <img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/f9d7618f-c2d4-472c-9477-85c30265847f" /> | <img width="393" height="852" alt="Image" src="https://github.com/user-attachments/assets/393ca9c2-ac70-4de5-9913-e827f25cd072" />

## Compliance & Security

- GDPR Adherence: All data processing activities strictly comply with the General Data Protection Regulation (Regulation EU 2016/679).

- Data Privacy: The system collects only the minimum amount of personal data required, and location data is processed temporarily without permanent storage.

- Secure Communication: All data exchange between the mobile client, backend, and external APIs is encrypted using the HTTPS protocol.

- API Security: External API keys (Google Maps Platform) are managed securely on the backend to prevent exposure.

## System Layers

- LLM Layer: Interprets user queries and converts them into structured TripSpec metadata.

- Map and Data Layer: Queries external Google Maps APIs (Places, Details, Routes) for real-world verification.

- Route Decision Mechanism: Scores, filters, and sequences candidate locations for efficiency.

- Explanation Layer: Compiles descriptive summaries for each itinerary stop using natural language generation.

- User Interface Layer: Enables user interaction, route visualization, and feedback capture.
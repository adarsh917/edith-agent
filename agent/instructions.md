Build a production-ready AI voice interview application called “The Interview Room”.

IMPORTANT:
This is NOT a text-only chatbot and NOT a simulated voice demo.

The application must use my EXISTING Agora Conversational AI agent named:

“Interview ai”

Agora Conversational AI must be the real-time voice engine.

==================================================
1. CORE EXPERIENCE
==================================================

Create a realistic AI interview experience.

The candidate should:

1. Enter their name.
2. Select their education/experience level.
3. Select or enter their interview field/domain.
4. Click “Start Interview”.
5. Allow microphone permission.
6. Join a real Agora voice conversation.
7. Hear the AI interviewer speak through the device speakers.
8. Speak naturally through the microphone.
9. The AI listens to the candidate's actual voice.
10. The AI asks the next question based on the candidate's field and previous answers.

DO NOT use fake voice, prerecorded audio, browser speech synthesis, placeholder audio, or simulated Agora connection states.

==================================================
2. AGORA INTEGRATION
==================================================

Use Agora Conversational AI as the actual conversational voice layer.

Use the existing published Agora agent:

Agent name:
Interview ai

The Agora credentials MUST NEVER be exposed in frontend/client-side code.

Create a secure server-side API layer.

Use environment variables such as:

AGORA_APP_ID=
AGORA_APP_CERTIFICATE=
AGORA_CUSTOMER_ID=
AGORA_CUSTOMER_SECRET=
AGORA_PIPELINE_ID=

Only include credentials that are actually required by the current Agora Conversational AI API flow.

Never hardcode secrets.

Never expose:
- Customer Secret
- App Certificate
- API keys

in browser JavaScript.

The frontend may receive only the safe information required to establish the RTC connection.

Use the official/current Agora Conversational AI API and Agora Web SDK documentation. Do not invent Agora endpoints, parameters, or authentication methods.

==================================================
3. INTERVIEW FIELD ADAPTATION
==================================================

The most important feature is adaptive questioning.

Before starting the interview, ask:

“What field or role are you interviewing for?”

Examples:

- Software Development
- Web Development
- AI/ML
- Data Science
- Backend Development
- Cybersecurity
- Electronics
- Mechanical Engineering
- Business
- Marketing
- Other

The selected field must influence the interview.

For example:

If the candidate selects:
“Backend Development”

Ask questions about:
- APIs
- databases
- authentication
- server architecture
- caching
- scalability
- security
- debugging
- system design

If the candidate selects:
“AI/ML”

Ask questions about:
- machine learning fundamentals
- model selection
- training
- evaluation
- datasets
- neural networks
- deployment
- AI projects

If the candidate selects:
“Web Development”

Ask questions about:
- HTML/CSS/JavaScript
- frontend frameworks
- APIs
- databases
- authentication
- performance
- deployment
- debugging

For any other field, dynamically generate relevant interview questions.

Do NOT ask the same generic questions for every candidate.

==================================================
4. ADAPTIVE INTERVIEW ENGINE
==================================================

The interview must adapt based on what the candidate says.

Rules:

If the candidate gives a strong answer:
→ ask a deeper or more difficult follow-up.

If the candidate gives a weak answer:
→ ask a simpler clarification or foundational question.

If the candidate mentions an interesting project:
→ ask a follow-up about that project.

If the candidate says something unclear:
→ ask for clarification.

If the candidate gives a very short answer:
→ ask a useful follow-up.

If the candidate demonstrates advanced knowledge:
→ increase difficulty.

If the candidate struggles:
→ reduce difficulty without being insulting.

Never repeatedly ask the same question.

Remember previous answers during the current interview.

==================================================
5. INTERVIEW PANEL
==================================================

Create three interviewer personas.

They can be represented as roles/personas inside ONE Agora conversational experience.

Do NOT pretend there are three independent Agora voice agents unless three actual agents are configured.

ROLE 1 — TECHNICAL INTERVIEWER

Focus on:
- technical knowledge
- programming
- concepts
- practical implementation
- debugging
- projects
- problem solving

ROLE 2 — BACKEND & SYSTEMS INTERVIEWER

Focus on:
- APIs
- databases
- architecture
- authentication
- security
- scalability
- system design
- data flow

Adapt this role for non-software fields when necessary.

ROLE 3 — HR & BEHAVIORAL INTERVIEWER

Focus on:
- communication
- teamwork
- leadership
- adaptability
- decision making
- challenges
- learning
- professionalism
- project experience

Only one interviewer persona should speak at a time.

==================================================
6. INTERVIEW FLOW
==================================================

Use this flow:

PHASE 1 — WELCOME

HR interviewer:

“Welcome to The Interview Room. Please introduce yourself.”

PHASE 2 — PROFILE

Ask about:
- name
- education/current role
- experience
- field/domain

PHASE 3 — TECHNICAL

Ask field-specific technical questions.

PHASE 4 — SYSTEMS

Ask architecture/system questions where relevant.

PHASE 5 — BEHAVIORAL

Ask HR/behavioral questions.

PHASE 6 — ADAPTIVE FOLLOW-UPS

Use previous answers to determine the next question.

PHASE 7 — FINAL QUESTION

Ask if the candidate wants to add anything important about their skills or projects.

PHASE 8 — END

Thank the candidate and end the voice session.

Target approximately 8–12 meaningful interview questions, excluding basic introduction/setup questions.

==================================================
7. REAL MICROPHONE
==================================================

The candidate must use the device microphone.

Request microphone permission properly.

Display clear states:

Connecting
Connected
Listening
Candidate Speaking
Thinking
AI Speaking
Completed

The UI status must reflect actual Agora connection/audio state.

Do NOT display “Connected” if Agora is not actually connected.

Handle:
- microphone permission denied
- microphone unavailable
- Agora connection failure
- agent unavailable
- network problems
- user leaving the interview

with useful error messages.

==================================================
8. INTERRUPTION AND TURN TAKING
==================================================

Use Agora's real-time conversational capabilities.

The candidate should be able to naturally respond when the AI finishes speaking.

Handle interruptions according to the capabilities of the configured Agora Conversational AI agent.

Avoid overlapping speech.

Do not implement fake interruption behavior.

==================================================
9. LIVE TRANSCRIPT
==================================================

Where supported by the actual Agora integration, show a live transcript.

Separate:

AI:
Candidate:

Keep the transcript synchronized with the interview.

If the current Agora configuration does not expose transcript events directly to the browser, design the application so transcript functionality can be connected through the supported server-side/event mechanism instead of fabricating transcript data.

==================================================
10. SCORECARD
==================================================

After the interview, generate a structured evaluation.

Evaluate:

Technical Knowledge
Problem Solving
Communication
Domain Knowledge
System Thinking
Adaptability
Behavioral Skills

Generate:

Overall Score /100

Strengths

Areas for Improvement

Technical Feedback

Problem-Solving Feedback

Communication Feedback

Behavioral Feedback

Final Summary

Recommended Next Steps

Do not evaluate:

Age
Gender
Race
Religion
Appearance
Accent
Other irrelevant personal characteristics

The evaluation must be based only on interview performance.

==================================================
11. UI DESIGN
==================================================

Create a professional futuristic interview interface.

Style:

Dark professional theme
Glassmorphism
Subtle animations
Clean typography
Responsive desktop/mobile design

Main screen:

--------------------------------
THE INTERVIEW ROOM

Field:
AI / ML

Interviewer:
Technical Interviewer

● Agora Connected

[ AI AVATAR ]

“Tell me about your most important AI project.”

--------------------------------

Bottom:

🎙 Microphone
Listening...

Live Transcript

Candidate:
...

--------------------------------

After completion:

INTERVIEW COMPLETE

Overall Score
87/100

Technical Knowledge  90
Problem Solving     85
Communication       88
Domain Knowledge    92
Adaptability        84

Strengths
...

Improve
...

==================================================
12. BACKEND
==================================================

Use a secure server-side architecture.

Suggested routes:

POST /api/interview/start

POST /api/interview/stop

GET /api/interview/status/:sessionId

POST /api/interview/evaluate

The backend should:

1. Create a unique interview session.
2. Store candidate profile.
3. Start/connect the existing Agora conversational agent using the official API.
4. Generate/return only safe client connection information.
5. Track session state.
6. Stop the agent when the interview ends.
7. Store interview context.
8. Generate the final evaluation.

Use proper validation and error handling.

==================================================
13. SESSION MEMORY
==================================================

Maintain memory during one interview:

Candidate name
Experience level
Selected field
Previous questions
Previous answers
Projects mentioned
Technical strengths
Areas where candidate struggled
Interview phase
Current interviewer persona

Use this context to determine subsequent questions.

Do not leak information between different candidates/interview sessions.

==================================================
14. SECURITY
==================================================

Security is critical.

Never put secrets in:

NEXT_PUBLIC_*
VITE_*
client-side JavaScript
React components
browser local storage

Keep sensitive Agora credentials server-side.

Validate all API requests.

Use unique session IDs.

Do not expose Customer Secret or App Certificate.

Add .env.example containing variable names but no real secrets.

==================================================
15. IMPORTANT IMPLEMENTATION RULE
==================================================

Do not create a fake working demo.

Do not use:

fake microphone
fake AI audio
fake Agora connection
fake transcript
fake interview responses
hardcoded “Connected” status
prerecorded questions pretending to be AI
browser TTS pretending to be Agora

The actual interview must use my existing Agora Conversational AI agent.

If a required Agora credential/configuration is missing, show a clear configuration error instead of silently falling back to fake functionality.

==================================================
16. PROJECT STRUCTURE
==================================================

Use a clean production architecture.

Recommended:

/app
/components
/lib
/server
/api
/types
/hooks

Separate:

UI
Agora connection logic
Interview session logic
Interview state
Evaluation logic
Server-side credentials

Use TypeScript.

Use environment variables.

Add comments around the Agora integration explaining exactly where the existing “Interview ai” agent is connected.

==================================================
17. README
==================================================

Create a detailed README explaining:

1. Project overview
2. Architecture
3. Agora Conversational AI integration
4. How to configure the existing “Interview ai” agent
5. Required environment variables
6. How to run locally
7. How to deploy to Vercel
8. How the adaptive interview works
9. Security considerations
10. Troubleshooting Agora connection problems

Clearly explain:

Candidate
↓
Web App
↓
Secure Backend
↓
Agora Conversational AI
↓
Existing “Interview ai” Agent
↓
Real-time voice conversation
↓
Interview evaluation
↓
Scorecard

==================================================
18. FINAL REQUIREMENT
==================================================

Build the application so that the FIRST priority is:

REAL AGORA VOICE INTERVIEW.

The UI should support the experience, not replace Agora.

The candidate's actual microphone audio must reach the real Agora conversational experience, and the candidate must hear the actual AI voice response.

Use current official Agora documentation when implementing the integration.

Do not invent APIs.

Do not expose credentials.

Do not create a fake voice simulation.

Build the complete application now.
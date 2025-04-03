## Quiz Generation Platform Documentation
### MORE DETAILS  

#### 📄 Report  
[![Report](https://img.shields.io/badge/View-Report-blue)](https://drive.google.com/file/d/1wCk1jf_65MIx6r-KRofCDZDGnhbJke0q/view?usp=sharing)  

#### 📊 Presentation  
[![Presentation](https://img.shields.io/badge/View-Presentation-orange)](https://docs.google.com/presentation/d/1HCODx-pdDCgsiYN4XEVxk1SpXpX1-K-r/edit?usp=sharing&ouid=110942945566615179747&rtpof=true&sd=true)  

#### 🎥 Demo Video  
[![Watch the demo](https://img.youtube.com/vi/MKSu4fnb8X0/maxresdefault.jpg)](https://youtu.be/MKSu4fnb8X0)  


### *Overview*
This platform generates quiz questions based on user-provided topics using Gemini-1.5-Flash. The application consists of a frontend built with Next.js, a backend using server actions, and PostgreSQL as the database, managed through Prisma.

Additionally, the platform tracks user success rates and provides a leaderboard. AI-driven recommendations, real-time analytics, and personalized learning tips enhance the user experience.

---
## *Data Pipeline*

### 1. *Data Collection*
- *Sources:*
  - Manually curated quiz questions stored in JSON.
  - AI-generated questions using Gemini API.
- *Ingestion Methods:*
  - Upload structured datasets using PostgreSQL.

---

### 2. *Preprocessing*
- *Gemini API handles preprocessing*
  - Tokenization
  - Noise removal
  - Format standardization
- *Error Handling:* Missing values are handled through model-specific logic.

---

### 3. *Data Storage*
- *Database:* PostgreSQL
- *ORM:* Prisma
- *Tables:*
  - users: Stores user details.
  - quizzes: Stores generated quizzes.
  - user_attempts: Tracks user quiz progress.
  - leaderboard: Maintains user rankings.

---

### 4. *AI Model Integration*
- *Quiz Generation*
  - Input: User preferences (topic, difficulty, question count)
  - Model: Gemini-1.5-Flash
  - Output: Multiple-choice quiz questions with correct answers

- *Personalized AI Feedback*
  - AI provides explanations for wrong answers.
  - Tracks user mistakes for performance improvement.

---

### 5. *Integration with Frontend*
- *Framework:* Next.js (TypeScript)
- *Styling:* Tailwind CSS
- *Server Actions:* Integrated directly using Next.js Server Actions instead of API routes
- *Authentication:* Next-Auth
- *Leaderboard Management:* Data is fetched using Prisma ORM
- *Charts and Animations:* Visualize user progress with Framer Motion and Radix UI

---

## *Evaluation Metrics*

### A. *Content Quality Metrics*
- *Perplexity (PPL):* Lower PPL = Better fluency.
- *Relevance Score:* Measures topic accuracy using cosine similarity.
- *Correctness Validation:* Fact-checking using LLM.
- *Readability Score:* Ensures clarity using Flesch-Kincaid Index.
- *Diversity Score:* Evaluates unique word usage.

### B. *Performance & Engagement Metrics*
- *User Engagement Rate:* Measures time spent on quizzes.
- *User Accuracy Rate:* Tracks correct answers using:  
  \[ Accuracy Rate = (Correct Answers / Total Questions Answered) \]
- *Drop-off Rate:* Monitors incomplete quizzes.
- *Leaderboard Impact:* Tracks motivation based on leaderboard participation.

---

## *Testing Methods*

### A. *Automated Evaluation*
- *GPT Verification:* Validate AI-generated questions.
- *Cosine Similarity:* Ensure question relevance.
- *Difficulty Estimation:* Pre-trained classifier validates difficulty levels.

### B. *Human Review*
- *Experts and Educators:* Evaluate quizzes on relevance, accuracy, and clarity.
- *Target Thresholds:*
  - 95%+ correctness
  - 85%+ relevance

---

## *Deployment*

### A. *Frontend Deployment*
- Use Vercel for seamless Next.js deployment:
bash
vercel deploy


### B. *Database Management*
- Apply Prisma migrations:
bash
npx prisma migrate deploy

- Generate Prisma client:
bash
npx prisma generate


---

## *Monitoring and Logging*
- *CI/CD:* Automated deployments using GitHub Actions

---

## *Conclusion*
This pipeline ensures efficient data handling, AI-powered quiz generation, user management, and a responsive frontend. Continuous monitoring and evaluation ensure the system remains performant and scalable.  Improves the user experience, making the platform engaging and educational.

# GradeSage AI

**Assessment that teaches, not just grades.**

GradeSage AI is a multi-agent assessment and feedback automation platform for teachers and students. It helps teachers create assignments, grade submissions with AI assistance, generate rubric-level feedback, and track student progress while giving students fast, actionable feedback on their work.

---

## One-Line Description

AI agents that automate assessment intelligently — rubric scoring, holistic feedback, and standards alignment — cutting teacher grading time dramatically.

---

## Problem Statement

Teachers spend up to 40% of their time on administrative work such as grading, feedback writing, progress reporting, and curriculum alignment. This reduces the time they can spend on teaching, mentoring, lesson planning, and supporting students individually.

Traditional grading is also slow for students. Feedback often arrives days or weeks after submission, making it less useful. Students may receive only a score or short comments, without clear next steps for improvement.

GradeSage AI solves this by using AI agents to provide fast, detailed, rubric-based, standards-aligned feedback while keeping teachers in control through approval, override, and review workflows.

---

## Who It Is For

GradeSage AI is designed for:

- Teachers who need to reduce grading workload
- Students who need faster, more actionable feedback
- Schools and colleges that want standards-aligned progress tracking
- English, humanities, writing, and project-based classrooms where long-form feedback is time-consuming

---

## Key Features

### Teacher Portal

- Teacher sign in and sign up using school or college email
- Teacher dashboard with assignments, submissions, grading stats, and review queue
- AI-assisted assignment creation from a natural-language prompt
- Auto-generated rubric and standards tags
- Submission review page with AI grade, feedback, confidence score, and agent breakdown
- Approve and override workflow for human-in-the-loop grading
- Student management page with email and message modals
- Analytics page with filters and export options
- Teacher profile page with editable account details

### Student Portal

- Student sign in and sign up using school or college email
- Student dashboard with assignments, feedback, and progress overview
- Assignment submission flow
- AI-generated feedback with strengths, growth areas, next steps, and rubric breakdown
- Progress tracking with charts
- Student profile page with editable details

### Persistence

All created assignments, students, submissions, and profile updates are saved using `localStorage`, so data remains available after logout, refresh, and login again.

---

## AI Agent Design

GradeSage AI is designed around a multi-agent architecture:

### 1. OpenAI Agent

Responsible for rubric-level scoring. It evaluates student submissions against rubric criteria such as:

- Thesis and argument
- Evidence and citations
- Analysis and depth
- Organization
- Style and mechanics

### 2. Claude Agent

Responsible for holistic feedback. It produces teacher-style comments, identifies strengths, growth areas, and next steps, and ensures the tone is supportive and actionable.

### 3. RAG Agent

Responsible for curriculum alignment. It checks submissions against standards, reference material, and rubric expectations.

### Consensus Layer

The final score is produced through a weighted consensus:

- OpenAI: 45%
- Claude: 40%
- RAG alignment: 15%

If confidence is low or scores disagree significantly, the system recommends human review.

> Note: The current hackathon demo simulates the AI workflow locally, so it can be tested without API keys.

---

## Tech Stack

- React 19
- Vite
- TypeScript
- Tailwind CSS 4
- Lucide React
- Recharts
- localStorage for demo persistence

Planned production integrations:

- OpenAI API
- Claude / Anthropic API
- RAG / Vector database such as Pinecone
- LMS integration through Canvas, Google Classroom, or Schoology

---

## Getting Started

### Prerequisites

Make sure you have Node.js installed.

Recommended:

```bash
node -v
npm -v
Installation
Clone the repository:

Bash

git clone https://github.com/your-username/gradesage-ai.git
cd gradesage-ai
Install dependencies:

Bash

npm install
Start the development server:

Bash

npm run dev
Build for production:

Bash

npm run build
Preview production build:

Bash

npm run preview
Authentication Rules
Both teachers and students must use a school or college email address.

Accepted institutional email patterns include:

.edu
.ac.*
.edu.*
.org
domains containing school
domains containing college
domains containing university
domains containing institute
domains containing academy
Examples:

text

teacher@school.edu
student@university.edu
admin@college.org
learner@academy.ac.in
Important:

Users must sign up before signing in.
If a user tries to sign in before creating an account, the app shows: Account not found. Please sign up first.
Profile data is saved and persists after logout/login.
How To Test The App
Teacher Flow
Choose I'm a Teacher
Sign up using a school or college email
Open the teacher dashboard
Go to Assignments
Click New Assignment
Enter an assignment prompt
Generate the rubric
Click Create assignment
Confirm that the assignment appears and remains after logout/login
Open Students and add student records
Open Analytics and test filters/export
Open My Profile and edit teacher details


Student Flow

Choose I'm a Student
Sign up using a school or college email
Open the student dashboard
View assignments
Submit work
Review AI-generated feedback
Open Profile
Edit name, grade, or section
Log out and log back in to confirm data persists

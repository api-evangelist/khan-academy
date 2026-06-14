# Khan Academy GraphQL Schema

## Overview

This is a conceptual GraphQL schema for Khan Academy, the non-profit providing free online educational content. Khan Academy's public-facing API is a legacy REST API (v1) available under `https://www.khanacademy.org/api/v1/`. This GraphQL schema models the domain objects and relationships surfaced by that API and the broader Khan Academy platform, including topics, exercises, videos, articles, users, badges, and progress tracking.

## Source

- **Provider:** Khan Academy
- **Kind:** Non-Profit / EdTech
- **REST API Base:** https://www.khanacademy.org/api/v1/
- **GitHub:** https://github.com/Khan
- **Website:** https://www.khanacademy.org/
- **Schema Type:** Conceptual (derived from public REST API and platform documentation)

## Domain Coverage

The schema covers the following major areas of the Khan Academy platform:

### Content Hierarchy
- **Topics** — The tree structure of subjects and courses (e.g., Math > Algebra > Linear Equations). Types: `Topic`, `TopicDetails`, `TopicSlug`, `TopicKind`, `TopicParent`, `TopicChildren`, `TopicIcons`, `TopicColor`.

### Exercises and Problems
- **Exercises** — Practice sets linked to topic nodes. Each exercise contains one or more problem types. Types: `Exercise`, `ExerciseDetails`, `ExerciseProblem`, `ProblemType`, `ProblemTemplate`, `ProblemSolution`, `Hint`, `ExerciseProgress`.

### Video Content
- **Videos** — Educational videos hosted on YouTube and served through Khan Academy. Types: `Video`, `VideoDetails`, `VideoKind`, `VideoDuration`, `VideoThumbnail`, `VideoTranscript`, `VideoCaption`, `YouTubeId`.

### Articles
- **Articles** — Text-based learning content. Types: `Article`, `ArticleDetails`, `ArticleContent`.

### Quizzes and Challenges
- **Quizzes and Projects** — Assessments and creative computing challenges. Types: `Quiz`, `QuizProblem`, `ProjectChallenge`, `ComputingChallenge`, `ProgrammingChallenge`, `Project`, `ProjectCode`, `Scratchpad`.

### Users and Profiles
- **Users** — Learner accounts, avatars, and profile data. Types: `User`, `UserProfile`, `UserBadge`, `Avatar`.

### Badges and Gamification
- **Badges** — Achievement system awarding points for learning milestones. Types: `Badge`, `BadgeCategory`, `BadgeIcon`, `BadgePoints`, `StreakRecord`, `Energy`.

### Progress and Tasks
- **Progress Tracking** — Learning task completion and progress data. Types: `Notebook`, `Task`, `LearningTask`, `ProgressData`.

### API Access
- **API Credentials** — Keys and tokens for API access. Types: `APIKey`, `Token`.

## Schema File

See `khan-academy-schema.graphql` for the full type definitions.

## Notes

- Khan Academy does not maintain a publicly supported GraphQL API. This schema is a conceptual representation derived from the legacy REST API surface and public platform documentation.
- The legacy REST API at `https://www.khanacademy.org/api/v1/` provides topic trees, exercise data, and video metadata that informed these type definitions.
- Internal Khan Academy tooling may use GraphQL privately; this schema is designed to reflect the public-facing data model.

# QuizMaster - Interactive Quiz Application

A full-stack quiz application built with React, TypeScript, and Supabase.

## Features

- 🔐 User Authentication
- 📝 Create and Edit Quizzes
- ✍️ Take Quizzes
- 📊 Track Scores and Progress
- 🏆 Global Leaderboard
- 📱 Responsive Design

## Tech Stack

### Frontend
- React 18
- TypeScript
- Tailwind CSS
- React Router
- Lucide Icons

### Backend
- Supabase
  - Authentication
  - Database
  - Real-time updates

## Project Structure

```
quiz-master/
├── src/
│   ├── components/       # Reusable UI components
│   ├── lib/             # Utilities and configurations
│   ├── pages/           # Route components
│   └── types/           # TypeScript definitions
├── public/              # Static assets
└── supabase/           # Database migrations
```

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/quiz-master.git
   cd quiz-master
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up Supabase:
   - Create a new project at https://supabase.com
   - Copy your project URL and anon key
   - Create a `.env` file:
     ```
     VITE_SUPABASE_URL=your_project_url
     VITE_SUPABASE_ANON_KEY=your_anon_key
     ```

4. Start the development server:
   ```bash
   npm run dev
   ```

## Database Schema

### Tables

1. profiles
   - id (uuid, references auth.users)
   - username (text)
   - avatar_url (text)
   - created_at (timestamp)

2. quizzes
   - id (uuid)
   - title (text)
   - description (text)
   - creator_id (uuid, references profiles)
   - category (text)
   - created_at (timestamp)

3. questions
   - id (uuid)
   - quiz_id (uuid, references quizzes)
   - question_text (text)
   - options (jsonb)
   - correct_answer (text)
   - order (integer)

4. quiz_attempts
   - id (uuid)
   - user_id (uuid, references profiles)
   - quiz_id (uuid, references quizzes)
   - score (integer)
   - completed_at (timestamp)

## Deployment

1. Build the project:
   ```bash
   npm run build
   ```

2. Deploy to your preferred hosting service (e.g., Netlify, Vercel)
   - Set environment variables for Supabase credentials
   - Configure build command: `npm run build`
   - Set output directory: `dist`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## License

MIT License - feel free to use this project for your own purposes.
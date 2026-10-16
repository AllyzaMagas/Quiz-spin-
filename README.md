# QuizSpin 
 Backend API for QuizSpin, a web-based educational spin-the-wheel game for the SorSU Bulan Campus Library. CS 313 Software Engineering 1, A.Y. 2026-2027

 - Developer: [Allyza G. Magas] (AllyzaMagas), BSCS [3-1 or 3-2]

 - Group and game concept: Group-7,A educational spin-the-wheel game where players spin a wheel and answer interactive questions to earn points.

 This is my own build of my group's game concept. Every commit in this repository was made by me, with Git, on my own mobile phone GitHub.

 ## Tech stack
 | Layer | Tool |
 |---|---|
 | Runtime | Node.js 22 LTS or newer |
 | Web framework | Express 5 |
 | Database | PostgreSQL 16 or newer |
 | ORM and migrations | Sequelize 6 with sequelize-cli |

 ## Setup


 git clone[https://github.com/AllyzaMagas/quiz-spin-]
 cd [Quiz-spin]
 npm install
 
Copy .env.example to .env, then put your own PostgreSQL password in DB_PASSWORD.


 npm run db:create
 npm run db:migrate
 npm run db:seed
 npm run db:check
 npm run dev

 ## Environment variables
 | Key | Example | Purpose |
 |---|---|---|
 | NODE_ENV | development | Which config block to use |
 | PORT | 3001 | Port the API listens on |
 | DB_HOST | 127.0.0.1 | PostgreSQL host |
 | DB_PORT | 5432 | PostgreSQL port |
 | DB_NAME | quizspin_db | Database name |
 | DB_USER | postgres | Database username |
 | DB_PASSWORD | (your own) | Database password. Never commit this. |
 | HUB_APL_KEY | dev-hub-key | Key the Library Game Hub sends |
 ## What "completed" means in my game
 A player completes the game when they have answered all available questions in the session, even if some answers were incorrect or timed out.
 ## Tables
 - hosts
 - question_sets
 - questions
 - game_sessions
 - players
 - answers
 ## Endpoints (Hub Contract v1.2)
 Base URL: http://localhost:3001/api/v1
 | Method | Path | Purpose | Success | Errors |
 |---|---|---|---|---|
 | GET | /health | Check API and database | 200 | 503 |
 | GET | /game-info | Game details | 200 | 500 |
 | GET | /results | Finished games, players, top 3. Needs X-Hub-Key header. | 200 | 401 |
 ## Database scripts
 | Command | What it does |
 |---|---|
 | npm run db:create | Create database |
 | npm run db:migrate | Run migrations |
 | npm run db:migrate:status | List migration status |
 | npm run db:seed | Load seed data |
 | npm run db:check | Count rows in all tables |
 | npm run db:reset | Reset database |
 | npm run check | Run GitHub checks |

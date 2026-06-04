```bash
nextjs-infrastructure/
├── .env.example
├── docker-compose.yml
├── README.md
├── package.json
│
├── services/
│   └── nextjs/                 
│       ├── Dockerfile
│       ├── app/
│       ├── lib/
│       ├── public/
│       └── ...
│
├── config/
│   ├── monitoring/
│   │   └── prometheus.yml
│   ├── nextjs/
│___   └── vault/
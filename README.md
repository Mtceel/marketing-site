# Marketing Site

Professional marketing website for the SaaS platform. Built with Express.js serving static HTML pages.

## Features

- 🏠 Homepage with hero, features, stats
- 💰 Pricing page with 3 tiers
- ✍️ Signup page with store creation
- 🔐 Login page with dashboard redirect
- 📱 Fully responsive design
- ⚡ Fast and lightweight

## Tech Stack

- Express.js (Node 20)
- Static HTML/CSS/JS
- Docker + Kubernetes
- GitHub Actions CI/CD

## Development

```bash
npm install
npm run dev
```

Visit http://localhost:3000

## Deployment

Automatically deployed via GitHub Actions on push to main branch.

```bash
docker build -t mtceel/marketing-site:latest .
docker push mtceel/marketing-site:latest
kubectl apply -f k8s/deployment.yaml
```

## Structure

```
├── public/
│   ├── index.html       # Homepage
│   ├── pricing.html     # Pricing page
│   ├── features.html    # Features page
│   ├── signup.html      # Signup form
│   ├── login.html       # Login form
│   ├── 404.html         # 404 error page
│   └── css/
│       ├── style.css    # Global styles
│       ├── pricing.css  # Pricing styles
│       └── auth.css     # Auth form styles
├── server.js            # Express server
├── Dockerfile           # Container build
└── k8s/
    └── deployment.yaml  # Kubernetes manifest
```

## Environment Variables

- `PORT` - Server port (default: 3000)
- `NODE_ENV` - Environment (production/development)

## API Endpoints

- `POST /api/signup` - Create new store (proxies to platform-api)
- `POST /api/login` - Authenticate user (proxies to platform-api)
- `GET /health` - Health check

## License

Proprietary

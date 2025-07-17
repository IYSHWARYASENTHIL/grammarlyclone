# GrammarlyClone - AI-Powered Writing Assistant

A comprehensive writing assistant application with AI-powered suggestions, plagiarism detection, and writing analytics.

## Project Structure

```
grammarly-clone/
├── frontend/                 # Next.js React frontend
│   ├── src/
│   │   ├── app/             # Next.js app directory
│   │   │   ├── editor/      # Writing editor page
│   │   │   ├── insights/    # Writing analytics page
│   │   │   ├── plagiarism/  # Plagiarism checker page
│   │   │   └── page.tsx     # Dashboard page
│   │   ├── components/      # Reusable UI components
│   │   │   └── ui/          # shadcn/ui components
│   │   ├── lib/             # Utility functions
│   │   └── hooks/           # Custom React hooks
│   ├── package.json
│   ├── tailwind.config.js
│   └── next.config.js
├── backend/                 # FastAPI Python backend
│   ├── main.py             # Main FastAPI application
│   ├── requirements.txt    # Python dependencies
│   └── .env.example        # Environment variables template
└── README.md
```

## Features

### Frontend (Next.js + React + TypeScript)
- **Dashboard**: Overview of writing statistics and recent documents
- **Editor**: Real-time writing with AI-powered suggestions
- **Insights**: Writing analytics and performance tracking
- **Plagiarism Checker**: Content originality verification
- **Modern UI**: Built with shadcn/ui and Tailwind CSS

### Backend (FastAPI + Python)
- **AI-Powered Suggestions**: Grammar, clarity, tone, and engagement improvements
- **Text Analytics**: Readability scores, sentiment analysis, tone detection
- **Plagiarism Detection**: Web and academic source checking
- **Document Management**: CRUD operations for writing documents
- **RESTful API**: Well-documented endpoints with OpenAPI/Swagger

## Getting Started

### Prerequisites
- Node.js 18+ and npm
- Python 3.8+
- Optional: Groq API key for advanced AI features
- Optional: Hugging Face API key for enhanced text analysis

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

The frontend will be available at `http://localhost:3000`

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your API keys (optional for basic functionality)
```

5. Start the FastAPI server:
```bash
python main.py
```

The backend API will be available at `http://localhost:8000`
API documentation: `http://localhost:8000/docs`

## API Endpoints

### Documents
- `POST /api/documents` - Create a new document
- `GET /api/documents` - Get user's documents
- `GET /api/documents/{id}` - Get specific document
- `PUT /api/documents/{id}` - Update document
- `DELETE /api/documents/{id}` - Delete document

### AI Services
- `POST /api/ai/suggestions` - Get writing suggestions
- `POST /api/ai/plagiarism/check` - Check for plagiarism
- `POST /api/ai/insights` - Get writing insights

### Health Check
- `GET /health` - API health status

## Technology Stack

### Frontend
- **Next.js 14** - React framework with App Router
- **TypeScript** - Type safety
- **Tailwind CSS** - Utility-first CSS framework
- **shadcn/ui** - Modern UI component library
- **Lucide React** - Icon library

### Backend
- **FastAPI** - Modern Python web framework
- **Pydantic** - Data validation and serialization
- **Groq** - AI language model integration
- **scikit-learn** - Machine learning utilities
- **NumPy** - Numerical computing

## Configuration

### Environment Variables (Backend)

```env
GROQ_API_KEY=your_groq_api_key_here
HUGGINGFACE_API_KEY=your_huggingface_api_key_here
MONGODB_URI=mongodb://localhost:27017/grammarly_clone
CORS_ORIGINS=http://localhost:3000
DEBUG=False
```

### Next.js Configuration (Frontend)

The frontend is configured to proxy API requests to the backend:

```javascript
// next.config.js
async rewrites() {
  return [
    {
      source: '/api/:path*',
      destination: 'http://localhost:8000/api/:path*',
    },
  ]
}
```

## Development

### Running Both Services

1. Start the backend:
```bash
cd backend
python main.py
```

2. In a new terminal, start the frontend:
```bash
cd frontend
npm run dev
```

### Building for Production

#### Frontend
```bash
cd frontend
npm run build
npm start
```

#### Backend
```bash
cd backend
pip install gunicorn
gunicorn main:app -w 4 -k uvicorn.workers.UvicornWorker
```

## Features in Detail

### AI-Powered Writing Suggestions
- Grammar and spelling corrections
- Clarity and readability improvements
- Tone and style adjustments
- Engagement enhancements
- Real-time analysis as you type

### Plagiarism Detection
- Web source checking
- Academic database comparison
- Similarity scoring
- Source attribution
- Detailed match reports

### Writing Analytics
- Readability scores (Flesch-Kincaid)
- Sentiment analysis
- Tone detection
- Word diversity metrics
- Writing pattern insights
- Progress tracking

### Document Management
- Auto-save functionality
- Version history
- Export options
- Sharing capabilities
- Organization tools

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support and questions:
- Check the API documentation at `/docs`
- Review the code comments
- Open an issue on GitHub

## Roadmap

- [ ] Real-time collaboration
- [ ] Advanced AI models integration
- [ ] Mobile application
- [ ] Plugin system
- [ ] Advanced analytics dashboard
- [ ] Multi-language support
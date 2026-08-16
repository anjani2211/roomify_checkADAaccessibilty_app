  # Roomify


Roomify is an AI-powered architectural design and accessibility analysis tool that transforms 2D floor plans into intelligent, visual design insights.


The project combines multimodal AI, architectural visualization, and universal design principles to help users understand how a space can be made more accessible, practical, and inclusive.


Users can upload a floor plan and receive an AI-generated visualization of the space along with accessibility-oriented suggestions such as improvements to circulation, wheelchair clearances, bathroom accessibility, doorways, thresholds, and other elements of universal design.


---


## Overview


Architectural floor plans contain a large amount of information, but interpreting them and evaluating whether a space is accessible can require significant architectural knowledge.


Roomify aims to make this process more accessible by allowing users to provide a floor plan and use AI to:


- Understand the layout of a space
- Generate a visual representation of the proposed design
- Identify potential accessibility issues
- Suggest possible accessibility improvements
- Help users visualize the result
- Allow human reviewers to evaluate the AI's suggestions


The goal is not simply to generate a visually appealing room.


Roomify is being developed as an **AI-assisted design review system** where generated suggestions can be evaluated by humans and potentially used to improve the quality of future recommendations.


---


## Core Features


### 2D Floor Plan Upload


Users can upload architectural floor plans in common image formats such as:


- JPG
- PNG


The uploaded floor plan becomes the basis for the rest of the workflow.


### AI-Powered Visualization


Roomify can transform a 2D floor plan into a photorealistic, top-down architectural visualization.


The rendering workflow is designed to preserve:


- Room geometry
- Walls
- Doors
- Windows
- Furniture indicated in the floor plan
- Overall spatial arrangement


while producing a cleaner and more realistic representation of the space.


### Accessibility Analysis


The planned core direction of Roomify is **accessibility and universal design analysis**.


The AI can be used to identify potential accessibility concerns in a floor plan, including areas such as:


- Wheelchair circulation and clearances
- Doorway accessibility
- Step-free entrances and thresholds
- Bathroom accessibility
- Grab-bar placement
- Lever-style door handles
- Accessible circulation paths
- General universal-design considerations
Technology Stack
Frontend
React
TypeScript
React Router
Vite
Tailwind CSS
Lucide React
Backend and Cloud Infrastructure
Puter.js
Puter Workers
Puter KV
Puter Hosting
Development Tools
Node.js
npm
WebStorm
Git
GitHub
Project Structure
roomify/
│
├── app/
│   ├── routes/
│   │   ├── home.tsx
│   │   └── visualizer.$id.tsx
│   ├── root.tsx
│   ├── routes.ts
│   └── app.css
│
├── components/
│   ├── ui/
│   │   └── Button.tsx
│   ├── Navbar.tsx
│   └── Upload.tsx
│
├── lib/
│   ├── ai.action.ts
│   ├── constants.ts
│   ├── puter.action.ts
│   ├── puter.hosting.ts
│   ├── puter.worker.js
│   └── utils.ts
│
├── public/
│
├── .env.local
├── package.json
├── package-lock.json
├── react-router.config.ts
├── tsconfig.json
├── type.d.ts
└── vite.config.ts

.env.local is used locally and should not be committed to the repository.

Architecture

Roomify is structured around a React frontend communicating with services provided through Puter.

Frontend

The React application handles:

Floor plan uploads
Project management
Navigation
Visualization display
User interaction
Accessibility review interfaces
AI Workflow

The AI workflow is responsible for processing the uploaded floor plan and generating architectural insights and visualizations.

The rendering prompt emphasizes maintaining the original floor-plan geometry while producing a realistic top-down visualization.

Puter Worker

A published Puter Worker acts as the backend layer for project-related operations.

The worker exposes endpoints such as:

POST /api/projects/save
GET  /api/projects/list
GET  /api/projects/get

The frontend communicates with these endpoints using:

puter.workers.exec()
Storage

Puter KV is used for project metadata, while Puter Hosting can be used to store and serve uploaded and generated images.

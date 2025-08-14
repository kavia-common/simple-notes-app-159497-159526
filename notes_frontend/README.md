# Notes Frontend (Astro)

Minimalistic, responsive notes UI built with Astro. Users can create, view, edit, and delete notes.  
Layout: Sidebar (notes list) + Main content (editor). Light theme with a dark-mode toggle.

## Features
- Create a new note
- Edit existing notes
- View notes in a list
- Delete notes
- Responsive design (desktop and mobile)
- Light theme, minimalistic styling with brand colors:
  - primary: `#4f46e5`
  - secondary: `#64748b`
  - accent: `#fbbf24`

## Run locally
```bash
npm install
npm run dev
```

Open the URL shown in the terminal (typically http://localhost:3000).

## Backend API configuration
This frontend expects a backend exposing a simple Notes REST API:
- GET    /notes
- GET    /notes/:id
- POST   /notes
- PUT    /notes/:id
- DELETE /notes/:id

Set the backend URL in your `.env` file:

```env
PUBLIC_API_BASE_URL=http://localhost:8000
```

See `.env.example` for a sample.  
If this variable is not provided, the UI falls back to localStorage so you can still try the app without a backend.

## Scripts
- `npm run dev` - Start the dev server
- `npm run build` - Build for production (output: `dist/`)
- `npm run preview` - Preview the built site
- `npm run lint` - Run ESLint

## Project structure
```
notes_frontend/
├─ src/
│  ├─ components/
│  │  ├─ NotesApp.astro
│  │  └─ ThemeToggle.astro
│  ├─ layouts/
│  │  └─ Layout.astro
│  ├─ lib/
│  │  └─ api.ts
│  └─ pages/
│     └─ index.astro
└─ .env.example
```

## Accessibility
- Keyboard navigation for note selection
- ARIA labels on lists and controls
- Reduced motion on quick feedback; status messages use `aria-live`

## License
MIT

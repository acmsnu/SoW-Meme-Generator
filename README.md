# Meme Generator Project 😂

Welcome to your creative web development project! This is a Meme Generator built with React and Vite that uses external APIs to fetch meme templates and create custom memes. Perfect for developers learning API integration and dynamic content creation!

## What You'll Learn

- API integration and data fetching
- React state management with hooks
- Dynamic image manipulation
- Form handling and user input
- Responsive design with TailwindCSS
- Error handling and loading states
- File download functionality

## How It Works 🔧

The Meme Generator allows users to:

1. **Browse Templates**: Fetch popular meme templates from an API
2. **Add Custom Text**: Add top and bottom text to memes
3. **Customize Styling**: Adjust text size, color, and position
4. **Generate Memes**: Create custom memes with your text
5. **Download/Share**: Save your creations locally or share them

## Prerequisites

Before you start, make sure you have these installed on your computer:

- [Node.js](https://nodejs.org/) (version 16 or higher)
- [pnpm](https://pnpm.io/installation) package manager
- [Git](https://git-scm.com/) for version control
- A code editor like [VS Code](https://code.visualstudio.com/)

## Getting Started

### 1. Fork the Project

First, you need to create your own copy of this project:

1. Click the **Fork** button at the top right of this repository page
2. This creates a copy of the project in your own GitHub account
3. You'll be redirected to your forked repository

### 2. Clone Your Fork

Open your terminal and run (replace `your-username` with your actual GitHub username):

```bash
git clone https://github.com/[your-username]/SoW-Meme-Generator.git
cd SoW-Meme-Generator
```

### 3. Install Dependencies

Install all required packages using pnpm:

```bash
pnpm install
```

### 4. Start Development Server

```bash
pnpm dev
```

Your project will open in your browser at `http://localhost:5173`

## Project Structure

```
SoW-Meme-Generator/
├── src/
│   ├── App.jsx                # Main application component
│   ├── components/
│   │   ├── MemeGallery.jsx    # Display available meme templates
│   │   ├── MemeEditor.jsx     # Edit and customize memes
│   │   ├── MemeCanvas.jsx     # Render the final meme
│   │   ├── TextEditor.jsx     # Text input and styling controls
│   │   └── LoadingSpinner.jsx # Loading state component
│   ├── hooks/
│   │   ├── useMemeAPI.js      # Custom hook for API calls
│   │   └── useMemeGenerator.js # Hook for meme creation logic
│   ├── utils/
│   │   ├── apiHelpers.js      # API utility functions
│   │   └── memeHelpers.js     # Meme generation helpers
│   ├── services/
│   │   └── memeAPI.js         # API service functions
│   ├── main.jsx               # Entry point
│   └── index.css              # Global styles
├── public/                    # Static files
├── package.json               # Project dependencies
└── vite.config.js             # Vite configuration
```

## Your Mission 🎯

Create a fully functional Meme Generator with these features:

### Core Features (Start Here!)

- [ ] Fetch meme templates from an API (use imgflip.com API)
- [ ] Display meme templates in a grid layout
- [ ] Select a meme template to edit
- [ ] Add top and bottom text to memes
- [ ] Preview the meme with text overlay

### Intermediate Features

- [ ] Customize text styling (size, color, font)
- [ ] Position text dynamically on the meme
- [ ] Add loading states and error handling
- [ ] Search and filter meme templates
- [ ] Responsive design for mobile devices

### Advanced Features (Challenge!)

- [ ] Download generated memes as images
- [ ] Upload custom meme templates
- [ ] Add multiple text boxes anywhere on the meme
- [ ] Meme history and favorites
- [ ] Social media sharing integration
- [ ] Text effects (outline, shadow, gradient)
- [ ] Meme categories and trending templates

## API Information 📡

### Primary API: Imgflip Meme API

**Get Memes Endpoint:**

```
GET https://api.imgflip.com/get_memes
```

**Response Structure:**

```javascript
{
  "success": true,
  "data": {
    "memes": [
      {
        "id": "61579",
        "name": "One Does Not Simply",
        "url": "https://i.imgflip.com/1bij.jpg",
        "width": 568,
        "height": 335,
        "box_count": 2
      }
    ]
  }
}
```

### Alternative APIs

- [Meme API](https://github.com/D3vd/Meme_Api) - Simple random memes
- [Reddit Meme API](https://meme-api.herokuapp.com/) - Reddit-sourced memes

## Helpful Commands

```bash
# Start development server
pnpm dev

# Build for production
pnpm build

# Preview production build
pnpm preview

# Install a new package
pnpm add package-name

# Install development dependencies
pnpm add -D package-name
```

## Tips for Success 💡

1. **Start with API**: Get the meme fetching working first
2. **Handle Loading**: Always show loading states for better UX
3. **Error Boundaries**: Implement proper error handling
4. **Canvas or CSS**: Decide between HTML5 Canvas or CSS overlays for text
5. **Performance**: Optimize image loading and caching

## Code Structure Hints 🧠

### API Hook Example

```javascript
const useMemeAPI = () => {
  const [memes, setMemes] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  const fetchMemes = async () => {
    // API logic here
  };

  return { memes, loading, error, fetchMemes };
};
```

### State Structure Suggestion

```javascript
{
  selectedMeme: null,           // Currently selected meme template
  topText: '',                  // Top text input
  bottomText: '',               // Bottom text input
  textStyle: {                  // Text styling options
    fontSize: 32,
    color: '#FFFFFF',
    fontFamily: 'Impact'
  },
  generatedMeme: null          // Final meme data URL
}
```

## Common Challenges & Solutions

### CORS Issues with Images?

Use a proxy or canvas with `crossOrigin="anonymous"` attribute.

### Text Positioning?

Use CSS `position: absolute` with percentage-based positioning for responsive text placement.

### Image Download?

Use HTML5 Canvas and `toDataURL()` method:

```javascript
const downloadMeme = () => {
  const canvas = canvasRef.current;
  const link = document.createElement('a');
  link.download = 'meme.png';
  link.href = canvas.toDataURL();
  link.click();
};
```

## Resources for Learning

- [Fetch API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [HTML5 Canvas Tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)
- [React Hooks Guide](https://react.dev/reference/react)
- [CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [Image Handling in JavaScript](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)

## Need Help?

- Check the browser console for API errors
- Test API endpoints in a tool like Postman first
- Use React DevTools to inspect component state
- Check network tab for failed requests
- Look for CORS issues in console

## Bonus Challenges 🌟

Once you complete the basic generator, try these extensions:

- **GIF Support**: Allow animated GIF memes
- **Meme Templates**: Create your own meme template database
- **AI Integration**: Use AI APIs to suggest funny captions
- **Collaborative Memes**: Allow multiple users to edit the same meme
- **Meme Battles**: Users vote on the funniest memes
- **Voice to Text**: Add speech-to-text for meme captions

## Popular Meme APIs to Explore

- **Imgflip API**: Most comprehensive, requires API key for generation
- **Meme API**: Simple, no auth required
- **Reddit API**: Access to r/memes content
- **Giphy API**: For GIF memes and reactions

Happy meme-ing! 🚀

---
*"Memes are the DNA of the soul." - Make the internet laugh, one meme at a time!*

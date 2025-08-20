# SimpleCocktails

A beautiful, mobile-first cocktail search application that helps you find cocktail recipes by drink name or ingredients you have available in your bar.

## Features

- **Smart Cocktail Search**: Find cocktails for any drink with clear ingredients and numbered steps
- **Bar Mode**: List spirits and ingredients you have and get matching cocktails with missing items clearly marked
- **Layman Language**: Technical bartending terms are automatically translated to simple, understandable language
- **Drink Type Filters**: Filter cocktails by alcoholic, non-alcoholic, or optional alcohol
- **Mobile-First Design**: Responsive design optimized for all devices
- **Cocktail Caching**: Improved performance with 60-second response caching

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- Internet connection for cocktail API access

### Installation

1. Clone or download the project
2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables (optional):
   ```bash
   cp .env.example .env
   ```
   
   The app works out of the box with TheCocktailDB (no API key required). For additional features, you can add API keys for other services.

4. Run the development server:
   ```bash
   npm run dev
   ```

5. Open [http://localhost:3000](http://localhost:3000) in your browser

## Environment Variables

Create a `.env` file in the root directory:

```env
# Cocktail API Configuration
COCKTAIL_API_BASE=https://www.thecocktaildb.com/api/json/v1/1
COCKTAIL_API_KEY=
# Optional: Add other cocktail API keys for enhanced features
```

### API Services Used

1. **TheCocktailDB** (Primary, Free)
   - No API key required
   - Extensive cocktail database
   - Good for general cocktail searches

2. **Other Services** (Optional)
   - Can be configured for enhanced features
   - Advanced filtering capabilities

## Usage

### Cocktail Search
1. Enter a cocktail name in the search box (e.g., "mojito", "old fashioned", "margarita")
2. Apply drink type filters if needed (alcoholic, non-alcoholic, optional alcohol)
3. Get one focused result with an option to see 5 more alternatives

### Bar Mode
1. Click "Bar Mode" in the header
2. Add spirits and ingredients you have available
3. Get cocktails that use mostly your bar inventory
4. Missing ingredients are clearly highlighted
5. See "Why this fits" explanations for each suggestion

## Project Structure

```
├── app/
│   ├── page.tsx              # Main cocktail search page
│   ├── bar/
│   │   └── page.tsx          # Bar mode page
│   ├── layout.tsx            # Root layout
│   └── globals.css           # Global styles
├── components/
│   ├── cocktail-card.tsx     # Individual cocktail display
│   ├── cocktail-search.tsx   # Main search functionality
│   ├── bar-search.tsx        # Bar ingredient search
│   └── cocktail-results.tsx  # Results display with alternatives
├── lib/
│   ├── cocktail-api.ts       # API integration and caching
│   ├── cocktail-terms.ts     # Cocktail term translation
│   └── utils.ts              # Utility functions
└── README.md
```

## API Integration

The app uses a flexible API layer that can work with multiple cocktail services:

- **Normalized Data Structure**: All API responses are converted to a consistent format
- **Caching**: GET requests are cached for 60 seconds to improve performance
- **Error Handling**: Graceful fallbacks and user-friendly error messages
- **Translation Layer**: Technical bartending terms are automatically simplified

## Building for Production

```bash
npm run build
npm start
```

## Deployment

The app is configured for static export and can be deployed to any static hosting service:

```bash
npm run build
```

The `out/` directory will contain the static files ready for deployment.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the MIT License.
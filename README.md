# data.norge.no Redirect

[![Deploy to GitHub Pages](https://github.com/Informasjonsforvaltning/docs/actions/workflows/main.yml/badge.svg)](https://github.com/Informasjonsforvaltning/docs/actions/workflows/main.yml)

This repository contains a simple redirect page that automatically redirects visitors to the [data.norge.no technical documentation](https://data.norge.no/nb/technical).

## Overview

This is a GitHub Pages site that provides a professional redirect experience with:

- **Automatic redirect** after 5 seconds to data.norge.no technical documentation
- **Manual redirect button** for immediate navigation
- **Loading animation** with countdown timer
- **Professional styling** matching data.norge.no design
- **Responsive design** that works on all devices
- **Dark mode support** for better accessibility

## Features

### Visual Design

- Clean, professional layout matching data.norge.no branding
- Official data.norge.no logo and favicons
- Responsive design for mobile and desktop
- Dark mode support with `prefers-color-scheme`

### User Experience

- 5-second countdown timer with visual feedback
- Spinning loading animation
- Clear messaging in Norwegian
- Accessible design with proper focus states

### Technical Implementation

- HTML5 with semantic markup
- CSS3 with modern features (flexbox, grid, animations)
- Vanilla JavaScript for countdown and redirect
- GitHub Actions for automatic deployment

## Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the `master` branch.

### Workflow

1. Push changes to `master` branch
2. GitHub Actions automatically builds and deploys
3. Site is available at the configured GitHub Pages URL

### Requirements

- GitHub Pages enabled in repository settings
- Source set to "GitHub Actions"

## Local Development

To run this project locally:

```bash
# Clone the repository
git clone https://github.com/Informasjonsforvaltning/docs.git
cd docs

# Open index.html in a web browser
# Or serve with a local server:
python -m http.server 8000
# Then visit http://localhost:8000
```

## File Structure

```
docs/
├── index.html          # Main redirect page
├── .github/
│   └── workflows/
│       └── main.yml    # GitHub Actions deployment
├── .gitignore          # Git ignore rules
└── README.md          # This file
```

## Customization

### Changing Redirect URL

Update the target URL in `index.html`:

- Line 8: `<meta http-equiv="refresh" content="5; url=NEW_URL">`
- Line 295: `window.location.href = "NEW_URL";`
- Line 275: `<a href="NEW_URL" class="button">`

### Changing Countdown Time

Update the countdown duration:

- Line 8: Change `content="5;` to desired seconds
- Line 295: Change `5000` to milliseconds (seconds × 1000)
- Line 285: Change `let timeLeft = 5;` to desired seconds

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally
5. Submit a pull request

## License

This project is part of the Informasjonsforvaltning organization and follows the same licensing as other data.norge.no projects.

## Related Links

- [data.norge.no Technical Documentation](https://data.norge.no/nb/technical)
- [data.norge.no Main Site](https://data.norge.no)
- [Digitaliseringsdirektoratet](https://www.digdir.no/)

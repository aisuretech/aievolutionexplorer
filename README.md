# 🚀 Evolution Explorer

> Explore animal evolution through interactive timelines, curated science content, and AI-powered learning.

---

## 🌐 Live Demo
- **Production:** https://www.aievolutionexplorer.com/

<!-- Use absolute production URLs for README images (https://...), not relative paths. -->
![Preview Image](https://www.aievolutionexplorer.com/og-image.png)

---

## 💡 What Is This Website?

Evolution Explorer is an educational web platform that helps users discover how species changed over time and how major ideas in evolutionary science developed.

- **Who it's for:** Students, teachers, curious learners, and science enthusiasts
- **Problem it solves:** Makes complex evolutionary topics easier to explore with guided, interactive content instead of static textbook explanations
- **Why it’s unique:** Combines animal-specific AI timelines, educational reading paths, and SEO-prerendered pages for discoverability

---

## ✨ Key Features

### For Users
- Search and explore a wide set of animals with category filters and popularity sorting
- View AI-generated evolutionary timelines with follow-up exploration prompts
- Read rich educational sections on evolution basics, Darwin, cell complexity, and discussion essays

### For Developers 
- Type-safe React + TypeScript app with route-based content and reusable SEO components
- Build pipeline includes prerendering top animal pages and sitemap updates for better indexing

---

## 🧠 How It Works

### For Users
1. Select an animal from the homepage search/filter interface.
2. The app requests timeline data from the evolution API and renders an interactive history view.
3. Users continue learning through follow-up prompts and deep-dive educational pages.

### For Developers
- **Frontend:** React 19 + TypeScript + React Router + React Bootstrap UI, with dynamic head tags via react-head
- **Backend:** External evolution API service (configured via VITE_API_BASE), with Auth0 for user identity
- **Data Flow:** Browser requests animals/timelines from API, enriches visuals via Wikimedia image lookup, then renders route content and prerendered SEO pages

---

## 🛠️ Tech Stack

- **Frontend:** React, TypeScript, Vite, React Router, React Bootstrap, Bootstrap
- **Backend:** External REST API (Evolution API)
- **Database:** Managed by external API service (not part of this repository)
- **Infrastructure:** Vercel deployment + static prerender outputs in dist
- **APIs / AI:** Evolution timeline API, Auth0, Wikimedia Commons API, recommendation widget script

---

## 🧩 Architecture Overview

This repository contains the client application. At runtime, the app fetches animal metadata and timeline payloads from an external API, uses Auth0 for optional authentication, and performs SEO-focused prerendering during build to generate static animal pages and an updated sitemap.

```text
[User Browser]
    |
    v
[React + Vite SPA]
    |-- GET /animals, POST /timeline, POST /{template} --> [Evolution API]
    |-- Auth login/session --------------------------------> [Auth0]
    |-- Image lookup -------------------------------------> [Wikimedia Commons API]
    |
Build time:
[Vite Build] -> [scripts/prerender-api.js] -> [dist/explore/<animal>.html + sitemap.xml]
    |
    v
[Vercel Hosting]
```


### Environment Variables

Create a `.env` file:

```env
VITE_AUTH0_DOMAIN=your-auth0-domain
VITE_AUTH0_CLIENT_ID=your-auth0-client-id
VITE_AUTH0_AUDIENCE=your-auth0-audience
```

### Prerequisites
- Node.js 20+
- npm 10+

---

## 🔌 API / Backend Details (if applicable)

### Example Endpoint

```http
GET /api/evolution/animals
```

### Example Response

```json
{
  "success": true,
  "data": [
    {
      "id": "123",
      "common_name": "African Elephant",
      "scientific_name": "Loxodonta africana",
      "category": "Mammals",
      "popularity": 98
    }
  ]
}
```

### Authentication
Auth0 is integrated for sign-in/sign-up. If a user is not authenticated, requests are still supported using a fallback anonymous user identifier.

---

## 📸 Screenshots / UI Preview

<!-- Use absolute production URLs for all screenshot images (https://...), not ./assets paths. -->

| Feature | Preview |
|--------|--------|
| Animal Exploration Experience | ![](https://www.aievolutionexplorer.com/images/md/images.jfif) |
| Educational Discussion Content | ![](https://www.aievolutionexplorer.com/images/md/images5.jfif) |

---

## 🎯 Use Cases

- Classroom support for introducing evolution with interactive examples
- Self-paced science learning for students and curious readers
- Content discovery for users comparing scientific and philosophical perspectives on origins

---

## 🗺️ Roadmap

- [ ] Add richer visual timeline interactions (zoomable eras and event clustering)
- [ ] Provide user bookmarks/history for saved species explorations
- [ ] Expand structured data coverage and automated SEO validation in CI

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Push to your branch
5. Open a Pull Request

---

## 📄 License

Not specified yet (add a LICENSE file to define usage terms).

---

## 🔗 Links

- GitHub Organization: https://github.com/aisuretech/
- Website: https://www.aievolutionexplorer.com/
- Contact: info@AISureTech.com

---

## ⭐ Final Note

If this project interests you, check out the live site and explore what it can do.

> Start with a species you know, then follow the timeline to discover how deeply connected life on Earth really is.


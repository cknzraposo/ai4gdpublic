# AI for Good

A modern web application template built with Astro, React, and TailwindCSS, designed to showcase initiatives and organisations using artificial intelligence for social impact and humanitarian causes. The site is hosted on Azure Static Web apps and can be customised to add custome backend logic and APIs on the Azure platform.

## 📖 Overview

Check out the [AI for Good Contribution Guide](AIFORGOOD.md) for more details on how to contribute to this project.

- Learn how to build  and publish this site to Azure from scratch in the [Hands-On Guide](HOWTOGUIDE.md).
- The final published site is available at [https://www.aiforgood.org.nz/](https://www.aiforgood.org.nz/).
- The site and code are licensed under the [MIT License](LICENSE).

## 🌟 Features

- 🚀 Built with Astro v5.x for optimal performance
- ⚛️ React components for interactive UI elements
- 🎨 TailwindCSS v4.x for elegant styling
- 📱 Fully responsive design
- 🔍 SEO-friendly structure
- 🌐 Modern, accessible interface
- 🌐 Hosted on Azure Static Web Apps for easy deployment and scalability

## 🚀 Project Structure

```text
/
├── public/
│   ├── favicon.svg
│   ├── icons/
│   │   ├── climate.svg
│   │   ├── education.svg
│   │   └── healthcare.svg
│   └── images/
│       ├── 3dwaves.jpeg
│       ├── platedbuildings.jpeg
│       └── serenelandscape.jpeg
├── src/
│   ├── components/
│   │   ├── FeatureCard.astro
│   │   ├── Footer.astro
│   │   ├── Hero.astro
│   │   ├── ImpactSection.astro
│   │   ├── JoinSection.astro
│   │   ├── Navbar.astro
│   │   └── WhatIsSection.astro
│   ├── layouts/
│   ├── pages/
│   │   ├── about.astro
│   │   ├── community.astro
│   │   ├── index.astro
│   │   └── projects.astro
│   ├── styles/
│   │   ├── global.css
│   │   └── hero.css
│   └── utils/
└── astro.config.mjs
```

## 📑 Key Components

- **Navbar**: Navigation component with responsive design
- **Hero**: Engaging hero section for main messaging
- **FeatureCard**: Reusable component for highlighting key features
- **ImpactSection**: Showcase impact and results
- **JoinSection**: Call-to-action component
- **WhatIsSection**: Informative section about the initiative
- **Footer**: Footer component with site links and information

## 📄 Pages

- **Home** (`index.astro`): Landing page with key sections
- **About** (`about.astro`): Detailed information about the initiative
- **Projects** (`projects.astro`): Showcase of various projects
- **Community** (`community.astro`): Community engagement and participation

## 🛠️ Getting Started

### Prerequisites

- Node.js 18.x or higher
- npm or yarn package manager

### Installation

1. Clone this repository

```bash
git clone [repository-url]
```

1. Install dependencies

```bash
npm install
```

1. Start development server

```bash
npm run dev
```

The site will be available at `localhost:4321`

## 🧞 Available Commands

| Command                   | Action                                           |
| :----------------------- | :----------------------------------------------- |
| `npm install`            | Installs dependencies                            |
| `npm run dev`            | Starts local dev server at `localhost:4321`      |
| `npm run build`          | Build your production site to `./dist/`          |
| `npm run preview`        | Preview your build locally, before deploying     |
| `npm run astro ...`      | Run CLI commands like `astro add`, `astro check` |

## ✨ Customization

1. **Content**: Update content in the Astro pages under `src/pages`
2. **Styling**: Modify TailwindCSS classes or update `tailwind.config.mjs`
3. **Components**: Add or modify components in `src/components`
4. **Assets**: Add images and icons to the `public` directory

## 📝 Best Practices

- Follow the established component structure
- Use TypeScript for type safety
- Maintain consistent styling using TailwindCSS utilities
- Keep components small and focused
- Implement responsive design patterns
- Use semantic HTML elements
- Follow accessibility guidelines

## 🤝 Contributing

Contributions are welcome! Please read our contributing guidelines and submit pull requests for any improvements.
The final published site is available at [https://www.aiforgood.org.nz/](https://www.aiforgood.org.nz/).

## 📚 Learn More

- [Astro Documentation](https://docs.astro.build)
- [TailwindCSS Documentation](https://tailwindcss.com/docs)
- [React Documentation](https://react.dev)
- [Azure Static Web Apps Documentation](https://docs.microsoft.com/azure/static-web-apps/)
- [Using GitHub Copilot to build this site](HOWTOGUIDE.md)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

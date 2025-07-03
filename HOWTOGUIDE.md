# Hands-On Guide: Building a static site Landing Page on Azure with GitHub Copilot

Leverage GitHub Copilot end-to-end—from a simple PRD (Product Requirements Document) to visual design to code and deploy a dynamic web site. The site uses Astro as a framework and is hosted on Azure Static Web Apps. 
The demo site is published and available at [https://www.aiforgood.org.nz/](https://www.aiforgood.org.nz/).

---

## Prerequisites

- VSCode editor with GitHub Copilot enabled
- GitHub Copilot Chat enabled (web or VSCode)
- Basic understanding of Git and GitHub
- Basic familiarity with Astro and Tailwind CSS (optional - you can learn as you go or use Copilot to help you)
- Access to Claude 3.5 Sonnet ([claude.ai/new](https://claude.ai/new)) (*optional, for design mockups*)
- Azure subscription and account for Static Web Apps deployment (This example uses a free tier which is sufficient for this exercise)

---

## Tools & Files

- GitHub Copilot (web or VS Code)  
- Claude 3.5 Sonnet  (Or any AI design tool of your choice)
- Astro (static-site framework)  
- Tailwind CSS (for utility-first styling)  
- design-principles.md (typography, spacing, color palette)

---

## Step 1: Generate the PRD with Copilot  

1. **Open** GitHub Copilot Chat on the web.  
2. **Prompt:**  
   ```text
   Describe a landing page for a site promoting "AI for Good" in simple terms. 
   ``` 
3. **Iterate** on the description with your prompt until you have a clear vision of the page structure and content. Keep it simple at first, focusing on the main sections and purpose.  
   - **Example:**  
     - Header with navigation  
     - Hero section with a tagline and image  
     - Main content area with features or benefits  
     - Call-to-action (CTA) cards  
     - Examples of AI for Good projects  
     - Footer with links and contact info

4. **Capture the output**—a lightweight PRD (Product Requirements Document) that includes:  
   - Purpose, audience, messaging pillars  
   - Sections: Header, Hero, Main Content, CTA Cards, Examples, Footer  

> **Tip:** Save this as `prd.md` in your repo root.
- Check out the projects [.github/copilot-instructions.md](.github/copilot-instructions.md) for more details on how to use Copilot effectively.
---
## Step 2: Create a Visual Mockup

- In this I used Claude 3.5 Sonnet, but you can use any AI design tool that supports visual mockups. 

1. **Visit** [claude.ai/new](https://claude.ai/new)  
2. **Paste** the PRD contents and ask:

   ```text
   Generate a minimalist, mobile-friendly landing-page design for "AI for Good in NZ" based on this PRD.
   ```

3. **Download** the design files/screenshots. The initial [sample html](/samples/ai_for_good_no_nav.html) is located in /samples/ai_for_good_no_nav.html.

- **Tip** Save them in a new folder: `x-source/`
---

## Step 3: Extract & Name Your Screenshots  

Store in `x-source/`:

- `1.header-nav-hero.png`  
- `2.main-content.png`  
- `3.cta-cards.png`  
- `4.examples-footer.png`  

---

## Step 4: Define Your Design Principles  

In `design-principles.md`, summarize: (examples below)

```markdown

- **Color Palette**: NZ green (#436436), white, charcoal (#333)  
- **Typography**:  
  - Headings: Montserrat, bold  
  - Body: Lato, regular  
- **Layout**:  
  - 12-column grid, 16 px gutters  
  - Generous whitespace around sections  
- **Imagery**: Use royalty-free images of NZ landscapes, people, and AI tech

---

## Step 5: Scaffold & Code with Copilot  

### 5.1 Initialize the Astro Project

```bash
npm create astro@latest <folder-name>
cd <folder-name>
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

- Note: You can run this in a terminal or use the VSCode terminal. Use npm run dev to start the local development server.

### 5.2 Prompt and Build Sections Incrementally  

**General Prompt Template:**  
```text
> “Using `x-source/1.header-nav-hero.png`, update `src/pages/index.astro` to add a responsive navbar and hero section. Follow the layout and styling principles.”
```

**Repeat** for each screenshot/section: (note you will need to adjust the prompt slightly for each section as you go)
- `2.main-content.png` → Features or “About” block  
- `3.cta-cards.png` → 2–3 cards with icons & CTAs  
- `4.examples-footer.png` → Example projects grid + Footer

> **Commit** after each section:  (Stage and commit your changes incrementally to keep track of your progress)
```bash
git add .
git commit -m "feat: add header & hero section"
```

---

## Step 6: Deploy to Azure Static Web Apps 

- **Azure Static Web Apps** is a service that automatically builds and deploys full-stack web apps to Azure from a GitHub repository. It supports static sites with serverless APIs, making it ideal for this project.
- Note: If you don't have an Azure account, you can sign up for a free account which includes a limited number of free Static Web Apps deployments. See: [Azure Free Account](https://azure.microsoft.com/free/)

1. **Push** your code to GitHub (`main` branch).  
2. **In Azure Portal** ▶️ Create **Static Web App**  
   - Resource Group: `rg-ai-for-good-nz`  
   - Name: `ai-for-good-nz`  
   - Region: closest to NZ (e.g., “Australia East”)  
   - Deployment Source: GitHub → Select Repo & Branch  
   - Build Presets: “Custom”  
     - App location: `/`  
     - API location: (leave blank)  
     - App artifact location: `dist/`  
3. **Review** the GitHub Actions workflow created in your repo:    
   - Ensure it builds and deploys correctly.  
   - If needed, adjust the `azure-static-web-apps.yml` file to match your project structure.

4. **Visit** the provided `<randomurl>.azurestaticapps.net` URL and confirm everything renders and responds across devices.

---

## Step 7: Iterate & Track Bugs  

- **GitHub Issues**: Label as `design`, `accessibility`, `responsive`.  
- **Pull Requests**: For larger refactors (dark mode toggle, i18n, analytics).  
- **A/B Testing**: Try alternative hero CTAs or imagery to track engagement.

---

## Reflection & Next Steps  

- Which design principle made the biggest impact?  
- How did Copilot’s suggestions align with your design-principles.md?  
- Plan a second iteration: add a blog section or newsletter signup.  

---

**You’re live!** Share your repo or demo link, let others clone the exercise, and invite contributions. Enjoy building—and iterating—your site using GitHub Copilot!

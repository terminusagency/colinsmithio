# Personalization Checklist

Use this checklist to make the codebase your own. Check off items as you complete them.

## ✅ Immediate Personalization (Do First)

- [ ] **`package.json`**
  - [ ] Change `name` from `"bloomfolio"` to your project name
  - [ ] Update `version` if desired

- [ ] **`src/config.ts`** - Your main configuration file
  - [ ] Update `name` (your name/portfolio name)
  - [ ] Update `title` (your professional title)
  - [ ] Update `description` (your portfolio description)
  - [ ] Update `avatar` path (point to your image)
  - [ ] Update `location`
  - [ ] Update `email`
  - [ ] Replace all `socialLinks` with your profiles
  - [ ] Customize `extraLinks` (FAB Flower menu) or disable it
  - [ ] Adjust `sections` visibility (enable/disable sections)

- [ ] **`src/assets/`**
  - [ ] Replace `bloomfolio.png` with your avatar/logo
  - [ ] Update any other assets

- [ ] **`public/favicon.svg`**
  - [ ] Replace with your favicon

## 📝 Content Updates

- [ ] **`src/content/about/about.md`**
  - [ ] Write your about page content

- [ ] **`src/content/blog/`**
  - [ ] Remove template guide posts
  - [ ] Add your own blog posts

- [ ] **`src/content/projects/`**
  - [ ] Replace example projects with your own
  - [ ] Update project markdown files

- [ ] **`src/content/work/`**
  - [ ] Add your work experience entries
  - [ ] Or disable work section in config

- [ ] **`src/content/education/`**
  - [ ] Add your education history
  - [ ] Or disable education section in config

- [ ] **`src/content/hackathons/`**
  - [ ] Add your hackathon entries
  - [ ] Or disable hackathons section in config

- [ ] **`public/images/`**
  - [ ] Replace placeholder images
  - [ ] Add your own images

## 📄 Documentation Updates

- [ ] **`README.md`**
  - [ ] Update title and description
  - [ ] Remove or update template-specific sections
  - [ ] Add your own project information
  - [ ] Update installation/deployment instructions if needed

- [ ] **`LICENSE`** (optional)
  - [ ] Update if you want a different license
  - [ ] Or keep MIT if you're fine with it

## 🎨 Optional Customizations

- [ ] **Custom components**
  - [ ] Add your own components to `src/components/`
  - [ ] Modify existing components if needed

- [ ] **Styling**
  - [ ] Customize theme colors in `src/styles/global.css`
  - [ ] Add custom CSS if needed

- [ ] **Layouts**
  - [ ] Customize layouts in `src/layouts/` if desired

- [ ] **New pages**
  - [ ] Add custom pages to `src/pages/` if needed

## 🔧 Configuration Files

- [ ] **`astro.config.mjs`**
  - [ ] Update site URL if needed
  - [ ] Add any custom integrations

- [ ] **`.gitignore`** (if needed)
  - [ ] Add any project-specific ignores

## 🚀 Deployment Prep

- [ ] **Environment variables** (if needed)
  - [ ] Set up any required env vars
  - [ ] Update deployment platform settings

- [ ] **Domain setup**
  - [ ] Configure custom domain if applicable

## 📋 After Personalization

- [ ] Test locally: `npm run dev`
- [ ] Build and preview: `npm run build && npm run preview`
- [ ] Deploy to your hosting platform
- [ ] Verify all links work
- [ ] Check mobile responsiveness
- [ ] Test all sections you enabled

---

## 🎯 Priority Order

1. **Must do first:** `package.json`, `src/config.ts`, avatar image
2. **Content:** About page, projects, work/education
3. **Cleanup:** Remove template content, update README
4. **Polish:** Custom styling, additional pages, deployment

---

## 💡 Pro Tips

- Keep a note of which files you've customized so you know what to check when syncing upstream
- Consider creating a `MY_CUSTOMIZATIONS.md` file to track your changes
- Test after each major change
- Commit frequently as you personalize


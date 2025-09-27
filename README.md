# Personal Website

A personal website built with Hugo, featuring sections for career, team information, and blog posts. Automatically deployed to GitHub Pages.

## 🚀 Features

- **About Page**: Personal introduction and mission
- **Career Section**: Professional experience and skills
- **Team Page**: Information about team members
- **Blog Posts**: Document and publish articles
- **Responsive Design**: Clean, modern theme (PaperMod)
- **Automatic Deployment**: GitHub Actions workflow for GitHub Pages

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── hugo.yml          # GitHub Actions deployment workflow
├── archetypes/               # Content templates
├── content/                  # Your content files
│   ├── about.md             # About page
│   ├── team.md              # Team information
│   ├── career.md            # Career details
│   └── posts/               # Blog posts directory
│       └── my-first-post.md # Example post
├── themes/PaperMod/         # Hugo theme (git submodule)
├── hugo.toml                # Hugo configuration
└── README.md               # This file
```

## 🛠 Setup and Development

### Prerequisites

- Hugo (installed via `sudo snap install hugo`)
- Git

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Ou.git
   cd Ou
   ```

2. Initialize and update the theme submodule:
   ```bash
   git submodule update --init --recursive
   ```

3. Start the development server:
   ```bash
   hugo server --buildDrafts
   ```

4. Open your browser and navigate to `http://localhost:1313/Ou/`

### Creating New Content

#### Create a new blog post:
```bash
hugo new content posts/your-post-title.md
```

#### Create a new page:
```bash
hugo new content your-page-name.md
```

### Building for Production

```bash
hugo --minify
```

This generates the static site in the `public/` directory.

## 🚀 Deployment to GitHub Pages

### Automatic Deployment

The site automatically deploys to GitHub Pages when you push to the main branch, thanks to the GitHub Actions workflow.

### Setup Instructions

1. **Create a new repository** on GitHub named `Ou` (or your preferred name)

2. **Update the base URL** in `hugo.toml`:
   ```toml
   baseURL = 'https://yourusername.github.io/Ou/'
   ```
   Replace `yourusername` with your actual GitHub username.

3. **Enable GitHub Pages**:
   - Go to your repository settings
   - Navigate to "Pages" section
   - Set source to "GitHub Actions"

4. **Push your code**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/Ou.git
   git push -u origin main
   ```

5. **Wait for deployment**: The GitHub Action will automatically build and deploy your site.

## ✏️ Customization

### Update Personal Information

1. **Hugo Configuration** (`hugo.toml`):
   - Update `title`, `baseURL`
   - Modify social media links
   - Customize menu items

2. **Content Pages**:
   - Edit `content/about.md` with your information
   - Update `content/career.md` with your experience
   - Modify `content/team.md` with your team details

3. **Theme Customization**:
   - Refer to [PaperMod documentation](https://github.com/adityatelange/hugo-PaperMod) for advanced customization options

### Adding New Sections

To add a new section (e.g., "Projects"):

1. Create the content file:
   ```bash
   hugo new content projects.md
   ```

2. Add menu entry in `hugo.toml`:
   ```toml
   [[menu.main]]
     identifier = "projects"
     name = "Projects"
     url = "/projects/"
     weight = 25
   ```

## 📝 Writing Posts

Blog posts should be placed in `content/posts/` directory. Each post should have front matter:

```markdown
+++
title = 'Your Post Title'
date = '2025-09-27T15:48:41-04:00'
draft = false
tags = ['tag1', 'tag2']
categories = ['category']
+++

Your post content here...
```

## 🔧 Troubleshooting

### Theme Issues
If the theme doesn't load:
```bash
git submodule update --init --recursive
```

### Local Development Issues
- Ensure Hugo is installed: `hugo version`
- Check that you're in the correct directory
- Try clearing Hugo's cache: `hugo --cleanDestinationDir`

### Deployment Issues
- Check GitHub Actions logs in your repository
- Ensure GitHub Pages is enabled in repository settings
- Verify the base URL in `hugo.toml` matches your GitHub Pages URL

## 📚 Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [PaperMod Theme Documentation](https://github.com/adityatelange/hugo-PaperMod)
- [GitHub Pages Documentation](https://pages.github.com/)
- [Markdown Guide](https://www.markdownguide.org/)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
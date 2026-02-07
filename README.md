# Martzen Blog - Jekyll + Obsidian Setup

This is a Jekyll website integrated with Obsidian for easy blog post management.

## 🚀 Quick Start

### 1. Install Dependencies

```bash
bundle install
```

### 2. Run Jekyll Locally

```bash
bundle exec jekyll serve
```

Visit `http://localhost:4000` to see your site!

## 📝 Writing Blog Posts in Obsidian

### Open in Obsidian

1. Open Obsidian
2. Choose "Open folder as vault"
3. Select this project folder

### Creating a New Blog Post

1. In Obsidian, navigate to the `_posts` folder
2. Create a new note with the format: `YYYY-MM-DD-title-of-post.md`
   - Example: `2026-02-07-my-awesome-post.md`
3. Add front matter at the top:

```yaml
---
layout: post
title: "Your Post Title"
date: 2026-02-07 10:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2]
---
```

1. Write your content in markdown below the front matter
2. Save the file

### Front Matter Explained

- **layout**: Always use `post` for blog posts
- **title**: Your post title (use quotes)
- **date**: Publication date and time
- **categories**: Organize posts by category
- **tags**: Add searchable tags

## 📁 Folder Structure

```bash
martzen/
├── _posts/           # Your blog posts (write here in Obsidian!)
├── _layouts/         # Jekyll page layouts
├── _includes/        # Reusable components (header, footer)
├── assets/
│   ├── css/          # Stylesheets
│   └── images/       # Images for posts (Obsidian attachments)
├── _config.yml       # Jekyll configuration
├── index.html        # Homepage
├── blog.html         # Blog listing page
└── about.md          # About page
```

## 🖼️ Adding Images

1. Place images in `assets/images/`
2. In your post, reference them:

```markdown
![Alt text](/assets/images/your-image.jpg)
```

Obsidian is configured to automatically save attachments to `assets/images/`.

## 🎨 Customization

### Update Site Information

Edit `_config.yml`:

- Change `title`, `description`, `author` information
- Update your email and name

### Modify Styling

Edit `assets/css/style.css` to customize the look and feel.

### Add New Pages

Create new `.md` or `.html` files in the root directory with:

```yaml
---
layout: page
title: Your Page Title
permalink: /your-page/
---
```

## 🌐 Deployment

### GitHub Pages

1. Push this repository to GitHub
2. Go to Settings → Pages
3. Select branch to deploy
4. Your site will be live at `https://yourusername.github.io/repository-name`

### Other Hosting

After running `bundle exec jekyll build`, upload the `_site/` folder to any web hosting service.

## 📚 Useful Commands

```bash
# Install dependencies
bundle install

# Run development server
bundle exec jekyll serve

# Build site for production
bundle exec jekyll build

# Run with drafts visible
bundle exec jekyll serve --drafts

# Clean build files
bundle exec jekyll clean
```

## 💡 Tips for Obsidian + Jekyll

1. **File naming**: Always use `YYYY-MM-DD-title.md` format for posts
2. **Internal links**: Obsidian's `[[links]]` won't work in Jekyll - use standard markdown `[text](url)`
3. **Templates**: Use the template in `_templates/blog-post.md` for new posts
4. **Preview**: Keep Jekyll running locally to preview changes in real-time
5. **Commits**: Regularly commit your posts to Git

## 🔧 Troubleshooting

**Jekyll won't start?**

- Run `bundle install` to ensure all gems are installed
- Check Ruby version (Jekyll requires Ruby 2.5+)

**Posts not showing?**

- Check the date in front matter isn't in the future
- Ensure filename follows `YYYY-MM-DD-title.md` format
- Make sure file is in `_posts/` folder

**Images not loading?**

- Verify image path is `/assets/images/filename.jpg`
- Check file actually exists in `assets/images/`

## 📖 Learn More

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Obsidian Help](https://help.obsidian.md/)
- [Markdown Guide](https://www.markdownguide.org/)

Happy blogging! 🎉

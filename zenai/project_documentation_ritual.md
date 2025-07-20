# Project Documentation Ritual – ZenAI Documentation Standards

This ritual codifies the documentation practices learned through collaborative development, ensuring consistent, stakeholder-ready documentation across all projects.

---

## 🎯 Purpose

To establish clear standards for:
- **Public vs Private Documentation** separation
- **Product-First Content** creation
- **Link Validation** discipline
- **Stakeholder-Ready** presentation

---

## 📚 Documentation Types

### **Public Documentation** (`docs/`)
- **Purpose**: Stakeholder communication, product showcase, public GitHub Pages
- **Audience**: Investors, users, community, potential contributors
- **Content**: Value proposition, benefits, user stories, clear problem/solution
- **Tone**: Professional, accessible, benefit-focused

### **Private Documentation** (`docs-private/`)
- **Purpose**: Internal reference, technical implementation, development planning
- **Audience**: Development team, technical stakeholders
- **Content**: Architecture details, technical specifications, implementation notes
- **Tone**: Technical, detailed, implementation-focused

---

## 🔐 Privacy & Security

### **Repository Privacy Strategy**
```bash
# For PRIVATE repos: Keep docs-private/ in repo (not ignored)
# - Main page (docs/index.md) is clean and stakeholder-ready
# - Detailed docs accessible but not linked from main page
# - If someone finds URL, no big deal (it's just docs)

# For PUBLIC repos: Add docs-private/ to .gitignore
# - Prevents accidental exposure of internal docs
# - Use docs-private/ for sensitive planning docs
```

### **Content Separation Rules**
- **Public**: Product vision, user benefits, clear value proposition
- **Private**: Technical architecture, implementation details, internal planning
- **Never Public**: API keys, internal discussions, unfinished features

---

## ✅ Link Validation Ritual

### **Before Every Documentation Commit**
1. Run link validation script: `./scripts/validate-links.sh`
2. Check all relative links work in GitHub Pages context
3. Verify external links point to correct repositories
4. Ensure no broken internal navigation

### **Common Link Issues to Avoid**
- ❌ `your-username` placeholder references
- ❌ Relative links that don't work in GitHub Pages
- ❌ Links to non-existent GitHub features (Discussions, etc.)
- ❌ Internal links to private documentation

---

## 🎨 Product-First Content Standards

### **Headlines & Positioning**
- ✅ "for the Bitcoin ecosystem" (broader scope)
- ❌ "for Bitcoin users" (too narrow)

### **Content Structure**
1. **What it is** - Clear, simple description
2. **Problem it solves** - Specific pain points
3. **How it works** - 3-step process
4. **Key benefits** - Bullet points with clear value
5. **Target users** - Specific personas
6. **Current status** - Development timeline

### **Language Guidelines**
- **Simple, clear language** - avoid technical jargon
- **Benefit-focused** - what users gain, not just features
- **Stakeholder-ready** - works for investors, users, community
- **Bitcoin ecosystem-aware** - includes Lightning, L2, businesses

---

## 🛠️ Tools & Scripts

### **Link Validation Script**
```bash
#!/bin/bash
# scripts/validate-links.sh
# Validates all markdown links in documentation
# Returns exit code 1 if broken links found
```

### **Documentation Structure**
```
docs/
├── index.md              # Public homepage (GitHub Pages)
└── website/              # Future website assets

docs-private/
├── product/              # Product planning docs
├── technical/            # Technical architecture
├── user/                 # User documentation
└── README.md             # Internal documentation index
```

---

## 🔄 Validation Checklist

### **Before Publishing Documentation**
- [ ] All links validated and working
- [ ] Content is stakeholder-ready (not technical)
- [ ] Private docs properly excluded from public repos
- [ ] GitHub Pages configuration correct
- [ ] No placeholder references or broken links
- [ ] Content aligns with product vision and positioning

---

## 🧩 Linked Ritual Artifacts

Refer to:
- [validation_checklist.md](validation_checklist.md)
- [.cursorrules](.cursorrules)
- [README-for-managers.md](README-for-managers.md)
- [project_plan_template.md](project_plan_template.md)

---

> _"Documentation is the first impression of your product. Make it count."_ – Zen 
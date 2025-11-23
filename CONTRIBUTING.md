# Contributing to MacBook GSAP Project

First off, thank you for considering contributing to the MacBook GSAP project! 🎉

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Project Structure](#project-structure)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)

## 📜 Code of Conduct

This project adheres to a code of conduct. By participating, you are expected to uphold this code. Please report unacceptable behavior to the project maintainers.

## 🤝 How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues. When creating a bug report, include:

- **Clear title and description**
- **Steps to reproduce** the behavior
- **Expected behavior**
- **Actual behavior**
- **Screenshots** if applicable
- **Environment details** (OS, browser, Node version)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

- **Clear title and description**
- **Step-by-step description** of the suggested enhancement
- **Explain why** this enhancement would be useful
- **Mockups or examples** if applicable

### Your First Code Contribution

Unsure where to begin? Look for issues labeled:

- `good first issue` - Simple issues for beginners
- `help wanted` - Issues that need attention

## 🛠️ Development Setup

1. **Fork and clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/Macbook_GSAP.git
cd Macbook_GSAP
```

2. **Install dependencies**

```bash
npm install
```

3. **Create a branch**

```bash
git checkout -b feature/your-feature-name
```

4. **Start development server**

```bash
npm run dev
```

## 📂 Project Structure

```
src/
├── components/          # React components
│   ├── models/         # 3D model components
│   ├── three/          # Three.js utilities
│   └── *.jsx           # Page components
├── constants/          # App constants
├── store/              # State management
├── App.jsx             # Main app
└── index.css          # Global styles
```

## 💻 Coding Standards

### JavaScript/React

- Use **functional components** with hooks
- Follow **ES6+** syntax
- Use **arrow functions** for callbacks
- Implement **PropTypes** or TypeScript for type checking
- Use **destructuring** for props and state

```javascript
// Good
const Component = ({ prop1, prop2 }) => {
  const [state, setState] = useState(initialValue);

  return <div>{prop1}</div>;
};

// Avoid
function Component(props) {
  return <div>{props.prop1}</div>;
}
```

### GSAP Animations

- Use **useGSAP hook** for proper cleanup
- Include **dependencies array** when needed
- Use **ScrollTrigger** for scroll-based animations
- Set **scope** to avoid global selectors

```javascript
useGSAP(
  () => {
    gsap.to(".element", {
      scrollTrigger: {
        trigger: ".container",
        start: "top center",
        end: "bottom top",
        scrub: true,
      },
      y: 100,
    });
  },
  { scope: containerRef, dependencies: [someState] }
);
```

### CSS/Tailwind

- Use **Tailwind utility classes** first
- Create **custom utilities** in index.css when needed
- Follow **mobile-first** approach
- Use **@apply** for repeated patterns

```css
/* Good - Custom utility */
@utility custom-card {
  @apply bg-white rounded-lg shadow-md p-4;
}

/* Use in JSX */
<div className="custom-card hover:shadow-lg transition-shadow" />
```

### File Naming

- **Components**: PascalCase (e.g., `ProductViewer.jsx`)
- **Utilities**: camelCase (e.g., `useAnimation.js`)
- **Constants**: camelCase (e.g., `constants/index.js`)
- **Styles**: kebab-case (e.g., `custom-styles.css`)

## 📝 Commit Guidelines

Follow **Conventional Commits** specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Build process or auxiliary tool changes

### Examples

```bash
feat(performance): add parallax effect to images
fix(product-viewer): correct model switching animation
docs(readme): update installation instructions
style(navbar): improve responsive design
refactor(store): simplify state management
perf(animations): optimize scroll triggers
```

## 🔄 Pull Request Process

1. **Update documentation** if needed
2. **Add/update tests** if applicable
3. **Update the README.md** with details of changes
4. **Ensure all tests pass** and code is linted
5. **Include screenshots** for UI changes
6. **Reference related issues** in PR description

### PR Template

```markdown
## Description

Brief description of changes

## Type of Change

- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing

How has this been tested?

## Screenshots

If applicable

## Checklist

- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No new warnings generated
- [ ] Tests added/updated
```

## 🧪 Testing

Before submitting a PR:

```bash
# Run linter
npm run lint

# Build project
npm run build

# Preview build
npm run preview
```

## 📱 Browser Support

Test your changes in:

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 🎨 Animation Guidelines

### Performance

- Use **GPU-accelerated properties** (transform, opacity)
- Avoid animating **width, height, top, left**
- Use **will-change** sparingly
- Keep animations **under 16ms** per frame

### Timing

- **Fast**: 200-300ms for micro-interactions
- **Medium**: 300-500ms for UI transitions
- **Slow**: 500-1000ms for dramatic effects
- Use **ease-out** for entries, **ease-in** for exits

### Accessibility

- Respect **prefers-reduced-motion**
- Provide **alternatives** for crucial animations
- Ensure **keyboard navigation** works
- Maintain **focus indicators**

## 📚 Resources

- [GSAP Documentation](https://gsap.com/docs/v3/)
- [React Three Fiber](https://docs.pmnd.rs/react-three-fiber/)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [React Best Practices](https://react.dev/)

## ❓ Questions?

Feel free to open an issue with the `question` label or reach out to the maintainers.

## 🙏 Thank You!

Your contributions make this project better for everyone. Happy coding! 🚀

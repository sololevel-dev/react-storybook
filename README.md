# Advanced Storybook Design System

A comprehensive React design system built with TypeScript, Tailwind CSS, and Storybook, demonstrating best practices for component development, documentation, and testing.

## 🚀 Features

### Design System Components
- **Button**: Multiple variants (primary, secondary, outline, ghost) with different sizes and states
- **Card**: Flexible card component with header, content, and footer sections
- **Modal**: Accessible modal with backdrop, animations, and keyboard navigation
- **Input**: Form input with validation states, icons, and helper text
- **Navigation**: Responsive navigation bar with mobile menu and active states

### Advanced Storybook Integration
- **Comprehensive Stories**: Multiple stories per component showcasing all variants and states
- **Interactive Controls**: Live editing of component props through Storybook's controls panel
- **Interaction Testing**: Automated user interaction testing with `@storybook/test`
- **Accessibility Testing**: Built-in a11y addon for accessibility compliance
- **Documentation**: Auto-generated docs with MDX support for design tokens and guidelines
- **Theming**: Custom theme system with light/dark mode support

### Technical Features
- **TypeScript**: Full type safety with proper interfaces and generics
- **Tailwind CSS**: Utility-first styling with custom design tokens
- **Class Variance Authority**: Type-safe component variants
- **Framer Motion**: Smooth animations and micro-interactions
- **Responsive Design**: Mobile-first approach with proper breakpoints
- **Accessibility**: WCAG compliant with proper ARIA labels and keyboard navigation

## 📦 Installation

```bash
# Clone the repository
git clone <repository-url>
cd advanced-storybook-design-system

# Install dependencies
npm install

# Start development server
npm run dev

# Start Storybook
npm run storybook
```

## 🛠️ Development

### Available Scripts

```bash
# Development
npm run dev          # Start Vite development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint

# Storybook
npm run storybook    # Start Storybook development server
npm run build-storybook  # Build Storybook for production

# Testing
npm run test         # Run Vitest tests
```

### Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── Button/
│   │   ├── Button.tsx
│   │   └── Button.stories.tsx
│   ├── Card/
│   ├── Modal/
│   ├── Input/
│   └── Navigation/
├── lib/                # Utility functions and configurations
│   ├── theme.ts        # Theme configuration
│   └── cn.ts          # Class name utility
├── stories/            # Storybook documentation
│   ├── Introduction.stories.mdx
│   └── Design-Tokens.stories.mdx
└── App.tsx            # Main application component
```

## 📚 Component Usage

### Button Component

```tsx
import { Button } from './components/Button/Button';

// Basic usage
<Button>Click me</Button>

// With variants
<Button variant="primary" size="lg">
  Primary Button
</Button>

// With icon
<Button variant="outline" icon={<Plus />}>
  Add Item
</Button>
```

### Card Component

```tsx
import { Card } from './components/Card/Card';

<Card>
  <Card.Header>
    <Card.Title>Card Title</Card.Title>
    <Card.Description>Card description</Card.Description>
  </Card.Header>
  <Card.Content>
    <p>Card content goes here</p>
  </Card.Content>
  <Card.Footer>
    <Button>Action</Button>
  </Card.Footer>
</Card>
```

### Modal Component

```tsx
import { Modal } from './components/Modal/Modal';

const [isOpen, setIsOpen] = useState(false);

<Modal isOpen={isOpen} onClose={() => setIsOpen(false)}>
  <Modal.Header>
    <Modal.Title>Modal Title</Modal.Title>
  </Modal.Header>
  <Modal.Content>
    <p>Modal content</p>
  </Modal.Content>
  <Modal.Footer>
    <Button onClick={() => setIsOpen(false)}>Close</Button>
  </Modal.Footer>
</Modal>
```

## 🎨 Design System

### Color Palette

The design system uses a comprehensive color system with semantic naming:

- **Primary**: Blue tones for main actions and branding
- **Secondary**: Gray tones for secondary actions
- **Success**: Green tones for positive actions
- **Warning**: Yellow/Orange tones for caution
- **Error**: Red tones for destructive actions
- **Neutral**: Gray scale for text and backgrounds

### Typography

- **Font Family**: Inter (system fallback)
- **Font Weights**: 400 (normal), 500 (medium), 600 (semibold), 700 (bold)
- **Line Heights**: 1.2 for headings, 1.5 for body text
- **Font Sizes**: Responsive scale from 12px to 48px

### Spacing

Consistent 8px spacing system:
- **xs**: 4px
- **sm**: 8px
- **md**: 16px
- **lg**: 24px
- **xl**: 32px
- **2xl**: 48px

## 🧪 Testing

### Interaction Testing

Components include comprehensive interaction tests using Storybook's testing utilities:

```tsx
export const InteractiveExample: Story = {
  play: async ({ canvasElement }) => {
    const canvas = within(canvasElement);
    const button = canvas.getByRole('button');
    
    await userEvent.click(button);
    await expect(button).toHaveClass('active');
  },
};
```

### Accessibility Testing

All components are tested for accessibility compliance using the a11y addon:

- Proper ARIA labels and roles
- Keyboard navigation support
- Color contrast compliance
- Screen reader compatibility

## 📖 Storybook Features

### Controls

Every component story includes comprehensive controls for:
- **Text inputs**: For labels, descriptions, and content
- **Select dropdowns**: For variants, sizes, and states
- **Boolean toggles**: For optional props and states
- **Color pickers**: For theme customization

### Addons

The project includes essential Storybook addons:

- **@storybook/addon-docs**: Auto-generated documentation
- **@storybook/addon-a11y**: Accessibility testing
- **@storybook/addon-vitest**: Integration testing
- **@storybook/addon-onboarding**: New user guidance

### Documentation

Comprehensive documentation includes:

- **Component API**: Props, types, and usage examples
- **Design Tokens**: Color palette, typography, and spacing
- **Best Practices**: Guidelines for component usage
- **Accessibility**: WCAG compliance information

## 🎯 Best Practices Demonstrated

### Component Architecture
- **Single Responsibility**: Each component has a focused purpose
- **Composition**: Components are built using composition patterns
- **Type Safety**: Full TypeScript coverage with proper interfaces
- **Accessibility**: WCAG 2.1 AA compliance

### Storybook Integration
- **Comprehensive Coverage**: Multiple stories per component
- **Interactive Examples**: Real-world usage scenarios
- **Documentation**: Auto-generated docs with custom MDX
- **Testing**: Automated interaction and accessibility testing

### Code Quality
- **ESLint**: Consistent code formatting and best practices
- **TypeScript**: Type safety and better developer experience
- **Responsive Design**: Mobile-first approach with proper breakpoints
- **Performance**: Optimized bundle size and runtime performance

## 🚀 Deployment

### Building for Production

```bash
# Build the application
npm run build

# Build Storybook
npm run build-storybook
```

### Storybook Deployment

The built Storybook can be deployed to any static hosting service:

```bash
# After building Storybook
npm run build-storybook

# Deploy the storybook-static folder to your hosting service
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-component`
3. Make your changes and add tests
4. Ensure all tests pass: `npm run test`
5. Update Storybook stories for new components
6. Submit a pull request

### Component Development Guidelines

When adding new components:

1. **Create the component** in `src/components/ComponentName/`
2. **Add TypeScript interfaces** for all props
3. **Implement variants** using class-variance-authority
4. **Create comprehensive stories** with all variants and states
5. **Add interaction tests** for user scenarios
6. **Ensure accessibility** compliance
7. **Update documentation** as needed


## 🙏 Acknowledgments

- [Storybook](https://storybook.js.org/) for the amazing component development environment
- [Tailwind CSS](https://tailwindcss.com/) for the utility-first CSS framework
- [Radix UI](https://www.radix-ui.com/) for accessibility patterns and inspiration
- [Lucide React](https://lucide.dev/) for the beautiful icon set
- [Framer Motion](https://www.framer.com/motion/) for smooth animations

---

Built with ❤️ using React, TypeScript, Tailwind CSS, and Storybook.

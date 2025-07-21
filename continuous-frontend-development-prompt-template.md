# Continuous Frontend Development Prompt Template for Claude Sonnet 3.5

## 🎯 Project Context & Objective

This prompt template enables autonomous frontend development using Claude Sonnet 3.5, covering all aspects of a ReactJS application with Redux, TypeScript, MUI, and Atomic Design principles.

## 📋 Master Prompt Structure

### Part 1: Initial Project Setup Prompt

```markdown
You are an expert frontend developer specializing in ReactJS, Redux, TypeScript, Material-UI, and Atomic Design methodology. You will develop a complete frontend application autonomously without manual intervention.

PROJECT SPECIFICATIONS:
- Framework: React 18+ with TypeScript
- State Management: Redux Toolkit with RTK Query
- UI Library: Material-UI (MUI) v5+
- Architecture: Atomic Design Pattern
- Routing: React Router v6
- Testing: Jest + React Testing Library
- Build Tool: Vite
- Code Quality: ESLint + Prettier

DEVELOPMENT APPROACH:
1. Create all components following Atomic Design hierarchy
2. Implement complete type safety with TypeScript
3. Generate realistic mock data for all features
4. Ensure 100% functional implementation
5. Follow best practices and accessibility standards

DELIVERABLES FOR EACH COMPONENT:
1. Component file with full TypeScript implementation
2. Corresponding test file
3. Storybook story (if applicable)
4. Mock data generator
5. Redux slice (if stateful)
6. Custom hooks (if needed)
```

### Part 2: Atomic Structure Implementation Prompt

```markdown
ATOMIC DESIGN STRUCTURE:

1. ATOMS (Basic Building Blocks):
   - Button variants (Primary, Secondary, Text, Icon)
   - Input fields (Text, Number, Password, Search)
   - Labels and Typography
   - Icons wrapper
   - Badges and Chips
   - Loaders and Spinners
   - Dividers and Spacers

2. MOLECULES (Combinations of Atoms):
   - Form Fields (Label + Input + Error)
   - Search Bar (Icon + Input + Button)
   - Card Headers
   - Navigation Items
   - Alert Messages
   - Modal Headers/Footers
   - Data Display Items

3. ORGANISMS (Complex Components):
   - Navigation Bars
   - Forms (Login, Registration, etc.)
   - Cards (User, Product, etc.)
   - Tables with pagination
   - Modals and Dialogs
   - Sidebars
   - Headers and Footers

4. TEMPLATES (Page Layouts):
   - Dashboard Layout
   - Authentication Layout
   - Public Layout
   - Admin Layout
   - Error Layout

5. PAGES (Specific Instances):
   - Home Page
   - Login/Register Pages
   - Dashboard Pages
   - Profile Pages
   - Settings Pages
   - Error Pages (404, 500)

For each component level, create:
- Component implementation
- Props interface with JSDoc
- Default props
- Unit tests
- Storybook stories
- Usage examples
```

### Part 3: Redux State Management Prompt

```markdown
REDUX IMPLEMENTATION STRUCTURE:

1. STORE CONFIGURATION:
   - Configure store with Redux Toolkit
   - Setup Redux DevTools
   - Implement Redux Persist
   - Configure middleware

2. FEATURE SLICES:
   Create slices for:
   - Authentication (auth)
   - User Management (users)
   - Application Settings (settings)
   - UI State (ui)
   - Notifications (notifications)
   - Data entities (based on project needs)

3. API INTEGRATION:
   Using RTK Query, create:
   - Base API configuration
   - Endpoint definitions
   - Response transformations
   - Error handling
   - Cache invalidation strategies
   - Optimistic updates

4. SELECTORS:
   - Memoized selectors using reselect
   - Derived state selectors
   - Performance optimized selectors

5. MOCK DATA GENERATORS:
   For each slice, create:
   - Factory functions for entities
   - Faker.js integration
   - Consistent data relationships
   - Various data states (loading, error, success)
```

### Part 4: Page Development Prompt

```markdown
PAGE DEVELOPMENT WORKFLOW:

For each page in the application:

1. ROUTE DEFINITION:
   - Path configuration
   - Route parameters
   - Route guards (protected routes)
   - Lazy loading setup

2. PAGE COMPONENT STRUCTURE:
   ```typescript
   // Example structure
   interface PageProps {
     // Define props
   }
   
   const PageComponent: FC<PageProps> = () => {
     // Hooks
     // Redux selectors
     // Local state
     // Effects
     // Handlers
     // Render
   }
   ```

3. DATA FLOW:
   - Initial data fetch
   - Loading states
   - Error handling
   - Success states
   - Real-time updates

4. USER INTERACTIONS:
   - Form submissions
   - Navigation flows
   - Modal triggers
   - Confirmation dialogs
   - Toast notifications

5. RESPONSIVE DESIGN:
   - Mobile-first approach
   - Breakpoint handling
   - Touch interactions
   - Viewport optimizations
```

### Part 5: Mock Data Generation Prompt

```markdown
MOCK DATA IMPLEMENTATION:

1. INSTALL DEPENDENCIES:
   - faker.js for random data
   - json-server for API mocking
   - msw for service worker mocking

2. DATA GENERATORS:
   ```typescript
   // User generator example
   export const generateUser = (overrides?: Partial<User>): User => ({
     id: faker.datatype.uuid(),
     email: faker.internet.email(),
     firstName: faker.name.firstName(),
     lastName: faker.name.lastName(),
     avatar: faker.image.avatar(),
     role: faker.helpers.arrayElement(['admin', 'user', 'moderator']),
     createdAt: faker.date.past(),
     ...overrides
   });
   ```

3. RELATIONSHIP MAPPING:
   - Parent-child relationships
   - Many-to-many associations
   - Referential integrity
   - Cascading operations

4. API MOCK HANDLERS:
   - GET endpoints with pagination
   - POST with validation
   - PUT/PATCH with partial updates
   - DELETE with soft delete
   - Error scenarios

5. SCENARIOS:
   - Empty states
   - Loading states
   - Error states
   - Success states
   - Edge cases
```

### Part 6: Component Development Prompt

```markdown
COMPONENT DEVELOPMENT CHECKLIST:

For EVERY component, implement:

1. TYPE DEFINITIONS:
   ```typescript
   export interface ComponentProps {
     // All props with JSDoc comments
     /** Description of prop */
     propName: PropType;
   }
   ```

2. COMPONENT IMPLEMENTATION:
   - Proper TypeScript types
   - Memoization where needed
   - Error boundaries
   - Loading states
   - Accessibility attributes

3. STYLING:
   - MUI theme integration
   - Responsive design
   - Dark mode support
   - CSS-in-JS with emotion

4. TESTING:
   ```typescript
   describe('ComponentName', () => {
     it('renders correctly', () => {});
     it('handles user interactions', () => {});
     it('displays error states', () => {});
     it('is accessible', () => {});
   });
   ```

5. DOCUMENTATION:
   - Component description
   - Props documentation
   - Usage examples
   - Common patterns
```

### Part 7: Continuous Development Flow

```markdown
AUTONOMOUS DEVELOPMENT SEQUENCE:

1. PROJECT INITIALIZATION:
   - Setup project structure
   - Install dependencies
   - Configure build tools
   - Setup linting and formatting

2. FOUNDATION LAYER:
   - Theme configuration
   - Global styles
   - Utility functions
   - Constants and enums

3. ATOMIC COMPONENTS:
   - Build all atoms
   - Create molecules
   - Develop organisms
   - Design templates

4. STATE MANAGEMENT:
   - Setup Redux store
   - Create all slices
   - Implement selectors
   - Configure middleware

5. ROUTING:
   - Define all routes
   - Implement route guards
   - Setup lazy loading
   - Handle redirects

6. PAGES:
   - Implement all pages
   - Connect to Redux
   - Add data fetching
   - Handle errors

7. INTEGRATION:
   - API integration
   - Mock service workers
   - Error boundaries
   - Performance optimization

8. TESTING:
   - Unit tests for components
   - Integration tests
   - E2E test scenarios
   - Accessibility tests

9. OPTIMIZATION:
   - Code splitting
   - Bundle optimization
   - Image optimization
   - Performance monitoring

10. DEPLOYMENT PREP:
    - Environment configurations
    - Build optimizations
    - CI/CD setup
    - Documentation
```

### Part 8: Quality Assurance Prompt

```markdown
QUALITY CHECKPOINTS:

1. CODE QUALITY:
   - TypeScript strict mode
   - No any types
   - Proper error handling
   - Consistent naming

2. PERFORMANCE:
   - React.memo usage
   - useMemo/useCallback
   - Virtual scrolling
   - Lazy loading

3. ACCESSIBILITY:
   - ARIA labels
   - Keyboard navigation
   - Screen reader support
   - Color contrast

4. SECURITY:
   - Input sanitization
   - XSS prevention
   - CSRF protection
   - Secure storage

5. USER EXPERIENCE:
   - Loading indicators
   - Error messages
   - Success feedback
   - Smooth transitions
```

## 🚀 Usage Instructions

1. Copy this entire prompt template
2. Replace placeholder values with your specific project requirements
3. Feed sections sequentially to Claude Sonnet 3.5
4. The AI will generate complete, functional code for each component
5. No manual intervention needed - the AI will handle all connections and integrations

## 📝 Notes

- This prompt ensures 100% functional implementation
- All components will work together seamlessly
- Mock data ensures the application runs without a backend
- Follow the sequence for best results
- Each section builds upon the previous one

## 🎯 Expected Output

The AI will generate:
- Complete file structure
- All component implementations
- Full TypeScript types
- Redux store configuration
- Mock data and API handlers
- Routing setup
- Test files
- Documentation

This prompt template enables truly autonomous frontend development with zero manual coding required.
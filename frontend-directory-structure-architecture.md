# Frontend Directory Structure Architecture

## 🎯 Overview

This document provides a comprehensive directory structure for a ReactJS application following Atomic Design principles, Redux state management, TypeScript, and Material-UI integration.

## 📊 Directory Structure Philosophy

### Core Principles
1. **Separation of Concerns**: Each directory has a single, clear purpose
2. **Scalability**: Structure supports growth without reorganization
3. **Discoverability**: Intuitive navigation and file location
4. **Modularity**: Components and features are self-contained
5. **Type Safety**: TypeScript definitions colocated with implementations

## 📁 Complete Directory Structure

```
src/
├── assets/                      # Static assets
│   ├── images/                  # Image files
│   │   ├── icons/              # Icon images
│   │   ├── logos/              # Brand logos
│   │   └── illustrations/      # UI illustrations
│   ├── fonts/                   # Custom fonts
│   └── styles/                  # Global styles
│       ├── _variables.scss      # SCSS variables
│       ├── _mixins.scss         # SCSS mixins
│       └── global.scss          # Global styles
│
├── components/                  # Atomic Design components
│   ├── atoms/                   # Basic building blocks
│   │   ├── Button/
│   │   │   ├── Button.tsx
│   │   │   ├── Button.styles.ts
│   │   │   ├── Button.types.ts
│   │   │   ├── Button.test.tsx
│   │   │   ├── Button.stories.tsx
│   │   │   └── index.ts
│   │   ├── Input/
│   │   ├── Label/
│   │   ├── Icon/
│   │   ├── Spinner/
│   │   └── Typography/
│   │
│   ├── molecules/               # Combinations of atoms
│   │   ├── FormField/
│   │   ├── SearchBar/
│   │   ├── NavItem/
│   │   ├── Card/
│   │   └── Modal/
│   │
│   ├── organisms/               # Complex components
│   │   ├── Header/
│   │   ├── Sidebar/
│   │   ├── DataTable/
│   │   ├── Form/
│   │   └── Footer/
│   │
│   ├── templates/               # Page layouts
│   │   ├── DashboardLayout/
│   │   ├── AuthLayout/
│   │   ├── PublicLayout/
│   │   └── ErrorLayout/
│   │
│   └── pages/                   # Complete pages
│       ├── Home/
│       ├── Login/
│       ├── Dashboard/
│       ├── Profile/
│       └── NotFound/
│
├── store/                       # Redux store configuration
│   ├── index.ts                 # Store configuration
│   ├── rootReducer.ts          # Root reducer
│   ├── middleware/             # Custom middleware
│   │   ├── logger.ts
│   │   └── errorHandler.ts
│   └── slices/                 # Redux slices
│       ├── auth/
│       │   ├── authSlice.ts
│       │   ├── authSelectors.ts
│       │   ├── authThunks.ts
│       │   └── authTypes.ts
│       ├── user/
│       ├── ui/
│       └── api/
│
├── services/                    # External services
│   ├── api/                     # API layer
│   │   ├── client.ts           # Axios instance
│   │   ├── endpoints/          # API endpoints
│   │   │   ├── auth.ts
│   │   │   ├── users.ts
│   │   │   └── products.ts
│   │   └── interceptors/       # Request/Response interceptors
│   ├── storage/                # Local storage service
│   ├── analytics/              # Analytics service
│   └── websocket/              # WebSocket service
│
├── hooks/                       # Custom React hooks
│   ├── useAuth.ts
│   ├── useDebounce.ts
│   ├── useLocalStorage.ts
│   ├── usePagination.ts
│   └── useWebSocket.ts
│
├── utils/                       # Utility functions
│   ├── constants/              # App constants
│   │   ├── routes.ts
│   │   ├── api.ts
│   │   └── config.ts
│   ├── helpers/                # Helper functions
│   │   ├── date.ts
│   │   ├── validation.ts
│   │   └── format.ts
│   ├── validators/             # Validation schemas
│   └── formatters/             # Data formatters
│
├── types/                       # TypeScript type definitions
│   ├── models/                 # Data models
│   │   ├── User.ts
│   │   ├── Product.ts
│   │   └── Order.ts
│   ├── api/                    # API types
│   ├── store/                  # Redux types
│   └── common/                 # Common types
│
├── routes/                      # Routing configuration
│   ├── index.tsx               # Main router
│   ├── PrivateRoute.tsx       # Protected route wrapper
│   ├── PublicRoute.tsx        # Public route wrapper
│   └── routeConfig.ts         # Route definitions
│
├── theme/                       # MUI theme configuration
│   ├── index.ts                # Theme export
│   ├── palette.ts              # Color palette
│   ├── typography.ts           # Typography settings
│   ├── components/             # Component overrides
│   └── breakpoints.ts          # Responsive breakpoints
│
├── mocks/                       # Mock data and handlers
│   ├── data/                   # Mock data generators
│   │   ├── users.ts
│   │   ├── products.ts
│   │   └── orders.ts
│   ├── handlers/               # MSW handlers
│   └── browser.ts              # MSW setup
│
├── tests/                       # Test utilities
│   ├── setup.ts                # Test setup
│   ├── utils/                  # Test utilities
│   └── fixtures/               # Test fixtures
│
├── App.tsx                      # Main App component
├── index.tsx                    # Entry point
└── vite-env.d.ts               # Vite types
```

## 📋 Directory Descriptions

### `/assets`
Static files that don't change during runtime. Includes images, fonts, and global styles.

### `/components`
Follows Atomic Design methodology:
- **Atoms**: Smallest components (buttons, inputs)
- **Molecules**: Simple combinations (form fields)
- **Organisms**: Complex sections (headers, forms)
- **Templates**: Page layouts
- **Pages**: Complete page implementations

### `/store`
Redux Toolkit store configuration with feature-based slices.

### `/services`
External service integrations (API, storage, analytics).

### `/hooks`
Custom React hooks for reusable logic.

### `/utils`
Pure utility functions and constants.

### `/types`
TypeScript type definitions organized by domain.

### `/routes`
React Router configuration and route components.

### `/theme`
Material-UI theme customization.

### `/mocks`
Mock data and MSW handlers for development.

### `/tests`
Testing utilities and configurations.

## 🔧 Component Structure Pattern

Each component follows this structure:
```
ComponentName/
├── ComponentName.tsx          # Main component
├── ComponentName.styles.ts    # Styled components/MUI styles
├── ComponentName.types.ts     # TypeScript interfaces
├── ComponentName.test.tsx     # Unit tests
├── ComponentName.stories.tsx  # Storybook stories
├── ComponentName.utils.ts     # Component-specific utils (optional)
├── hooks/                     # Component-specific hooks (optional)
│   └── useComponentLogic.ts
└── index.ts                   # Public exports
```

## 📐 Naming Conventions

### Files and Folders
- **Components**: PascalCase (e.g., `Button.tsx`, `UserProfile/`)
- **Utilities**: camelCase (e.g., `formatDate.ts`)
- **Constants**: UPPER_SNAKE_CASE in files (e.g., `API_ENDPOINTS`)
- **Types/Interfaces**: PascalCase with descriptive names
- **Hooks**: camelCase starting with 'use' (e.g., `useAuth.ts`)

### Code Organization
- One component per file
- Related components grouped in folders
- Shared logic extracted to hooks
- Business logic separated from UI

## 🚦 Import Order

1. External dependencies
2. Internal aliases
3. Relative imports
4. Types
5. Styles

Example:
```typescript
// External
import React, { useState, useEffect } from 'react';
import { Box, Button } from '@mui/material';

// Internal aliases
import { useAuth } from '@/hooks';
import { UserService } from '@/services';

// Relative imports
import { Header } from '../Header';
import { formatDate } from './utils';

// Types
import type { User } from '@/types';

// Styles
import { StyledContainer } from './styles';
```

## 🔄 State Management Structure

### Redux Slices Organization
```
slices/
├── auth/
│   ├── authSlice.ts        # Slice definition
│   ├── authSelectors.ts    # Memoized selectors
│   ├── authThunks.ts       # Async actions
│   ├── authTypes.ts        # TypeScript types
│   └── authApi.ts          # RTK Query API
```

### Feature-Based Organization
Each feature has its own slice containing:
- State shape definition
- Reducers
- Actions
- Selectors
- Async thunks
- API endpoints

## 🛡️ Best Practices

1. **Colocation**: Keep related files together
2. **Barrel Exports**: Use index.ts for clean imports
3. **Type Safety**: Define types for all props and state
4. **Testing**: Colocate tests with components
5. **Documentation**: Include README in complex features
6. **Lazy Loading**: Use React.lazy for pages
7. **Code Splitting**: Separate vendor bundles
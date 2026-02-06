# 🤝 Contributing to Package Installer CLI

<div align="center">

<img src="https://img.shields.io/badge/Package-blue?style=for-the-badge&logo=npm" alt="Package Installer">
<img src="https://img.shields.io/badge/Installer-blue?style=for-the-badge&logo=typescript" alt="Installer">

[![Contributors Welcome](https://img.shields.io/badge/contributors-welcome-brightgreen.svg?style=flat)](CONTRIBUTING.md)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

We're thrilled that you're interested in contributing to **Package Installer CLI v3.6.0**! This comprehensive guide will help you get started with contributing to this powerful development automation tool.

## 📋 Table of Contents

- [🌟 Code of Conduct](#-code-of-conduct)
- [🚀 Quick Start](#-quick-start)
- [⚙️ Development Setup](#️-development-setup)
- [🏗️ Project Architecture](#️-project-architecture)
- [📝 Contributing Guidelines](#-contributing-guidelines)
- [🔄 Pull Request Process](#-pull-request-process)
- [🐛 Issue Reporting](#-issue-reporting)
- [🛠️ Development Workflows](#️-development-workflows)
- [🎨 Adding New Templates](#-adding-new-templates)
- [🔧 Adding New Features](#-adding-new-features)
- [📊 Testing Guidelines](#-testing-guidelines)
- [🏆 Recognition](#-recognition)

## 🌟 Code of Conduct

By participating in this project, you agree to uphold our Code of Conduct. We are committed to providing a welcoming and inspiring community for all.

### Our Standards

✅ **Do:**
- Use welcoming and inclusive language
- Be respectful of differing viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on what is best for the community
- Show empathy towards other community members
- Help others learn and grow

❌ **Don't:**
- Use sexualized language or imagery
- Make personal attacks or insulting comments
- Engage in trolling or harassment
- Publish others' private information without permission
- Engage in any conduct that could be considered inappropriate

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have the following installed:

| Tool | Version | Purpose | Installation |
|------|---------|---------|--------------|
| **Node.js** | v18+ | Runtime environment | [Download](https://nodejs.org/) |
| **pnpm** | v8+ | Package manager (recommended) | `npm install -g pnpm` |
| **Git** | Latest | Version control | [Download](https://git-scm.com/) |
| **TypeScript** | v5+ | Language support | `npm install -g typescript` |
| **VS Code** | Latest | Recommended editor | [Download](https://code.visualstudio.com/) |

### 5-Minute Setup

```bash
# 1. Fork and clone the repository
git clone https://github.com/YOUR_USERNAME/devforge.git
cd devforge-cli

# 2. Install dependencies
pnpm install

# 3. Build the project
pnpm run build

# 4. Test the CLI
node dist/index.js --help

# 5. Start development mode
pnpm run dev
```

### Verify Your Setup

```bash
# Test core functionality
node dist/index.js create test-app

# Test features
node dist/index.js add --help

# Test analysis
node dist/index.js analyze --help
```
## ⚙️ Development Setup

### Environment Configuration

1. **Create development environment file**
   ```bash
   cp .env.example .env.local
   # Configure any necessary environment variables
   ```

2. **Install recommended VS Code extensions**
   ```bash
   # Extensions for optimal development experience
   code --install-extension ms-vscode.vscode-typescript-next
   code --install-extension bradlc.vscode-tailwindcss
   code --install-extension esbenp.prettier-vscode
   code --install-extension ms-vscode.vscode-eslint
   ```

3. **Configure Git hooks**
   ```bash
   # Set up pre-commit hooks for code quality
   pnpm run prepare
   ```

### Development Scripts

| Script | Purpose | Usage |
|--------|---------|-------|
| `pnpm run dev` | Development mode with watch | `pnpm run dev` |
| `pnpm run build` | Build production version | `pnpm run build` |
| `pnpm run clean` | Clean build artifacts | `pnpm run clean` |
| `pnpm run test` | Run test suite | `pnpm run test` |
| `pnpm run lint` | Check code quality | `pnpm run lint` |
| `pnpm run format` | Format code | `pnpm run format` |
| `pnpm run type-check` | Check TypeScript types | `pnpm run type-check` |

## 🏗️ Project Architecture

### Directory Structure

```
devforge-cli/
├── 📁 src/                          # Source code
│   ├── 📁 commands/                 # CLI command implementations
│   │   ├── 📄 create.ts            # Project creation command
│   │   ├── 📄 analyze.ts           # Analytics and insights
│   │   ├── 📄 check.ts             # Package version checking
│   │   ├── 📄 add.ts               # Feature addition
│   │   ├── 📄 clone.ts             # Repository cloning with Git support
│   │   ├── 📄 update.ts            # Multi-language dependency updates
│   │   ├── 📄 upgrade-cli.ts       # CLI self-updates with version detection
│   │   ├── 📄 doctor.ts            # System diagnostics and auto-fix
│   │   ├── 📄 env.ts               # Environment analysis and optimization
│   │   ├── 📄 clean.ts             # Project cleanup and cache management
│   │   ├── 📄 cache.ts             # Cache management and optimization
│   │   └── 📄 deploy.ts            # Deployment features (coming soon)
│   ├── 📁 utils/                    # Utility functions
│   │   ├── 📄 helpFormatter.ts     # Standardized help system
│   │   ├── 📄 ui.ts                # User interface and banners
│   │   ├── 📄 dashboard.ts         # Analytics dashboard
│   │   ├── 📄 utils.ts             # Core utilities and version management
│   │   ├── 📄 templateCreator.ts   # Template creation logic
│   │   ├── 📄 featureInstaller.ts  # Feature installation with caching
│   │   ├── 📄 languageConfig.ts    # Language configurations
│   │   ├── 📄 cacheManager.ts      # Performance cache management
│   │   └── 📄 historyManager.ts    # Usage history and analytics
│   └── 📄 index.ts                 # Main CLI entry point
├── 📁 templates/                    # Project templates
│   ├── 📁 nextjs/                  # Next.js templates
│   │   ├── 📁 typescript/          # TypeScript variants
│   │   └── 📁 javascript/          # JavaScript variants
│   ├── 📁 reactjs/                 # React templates
│   ├── 📁 expressjs/               # Express.js templates
│   ├── 📁 nestjs/                  # NestJS templates
│   ├── 📁 vue/                     # Vue.js templates
│   ├── 📁 angular/                 # Angular templates
│   ├── 📁 rust/                    # Rust templates
│   └── 📁 [framework]/             # Other framework templates
├── 📁 features/                     # Feature integrations
│   ├── 📁 ai/                      # AI integrations
│   │   ├── 📁 claude/              # Claude AI
│   │   ├── 📁 openai/              # OpenAI
│   │   └── 📁 gemini/              # Google Gemini
│   ├── 📁 auth/                    # Authentication
│   │   ├── 📁 auth0/               # Auth0
│   │   ├── 📁 clerk/               # Clerk
│   │   └── 📁 next-auth/           # NextAuth.js
│   ├── 📁 database/                # Database integrations
│   ├── 📁 docker/                  # Docker configurations
│   ├── 📁 aws/                     # AWS services (40+ services)
│   └── 📁 [category]/              # Other feature categories
├── 📁 docs/                        # Documentation
│   ├── 📄 features.md              # Features directory documentation
│   ├── 📄 templates.md             # Templates documentation
│   ├── 📄 commands.md              # Commands documentation
│   └── 📄 deploy.md                # Deployment guide
├── 📁 tests/                       # Test files
└── 📄 package.json                 # Project configuration
```

### Core Components

#### 1. Command System
- **Entry Point**: `src/index.ts` - Main CLI setup and command registration
- **Command Pattern**: Each command is a separate module with standardized interface
- **Help System**: Standardized help formatter with consistent styling and version display
- **Error Handling**: Centralized error handling with user-friendly messages
- **Performance**: Optimized loading with caching and lazy evaluation

#### 2. Template System
- **Dynamic Discovery**: Templates are discovered automatically from the templates directory
- **Multi-Language Support**: TypeScript and JavaScript variants for web frameworks
- **Variable Substitution**: Template files support dynamic variable replacement
- **Package Manager Detection**: Automatic detection of npm, yarn, or pnpm

#### 3. Feature System
- **Modular Architecture**: Features are self-contained modules
- **Framework Agnostic**: Features adapt to different project frameworks
- **Installation Actions**: Support for create, append, prepend, install, and merge operations
- **Dependency Management**: Automatic dependency installation and configuration

#### 4. Analytics System
- **Real-time Data**: All analytics use real data from `~/.devforge-cli/history.json`
- **Privacy-First**: No external data collection, all analytics are local
- **Performance Tracking**: Cache hit rates, operation speeds, and usage patterns
- **User Insights**: Framework preferences, feature adoption, and productivity metrics
- **Optimized Loading**: Cached feature configurations for faster startup times

## 📝 Contributing Guidelines

### Code Quality Standards

#### TypeScript Guidelines
```typescript
// ✅ Good: Use explicit types and interfaces
interface ProjectOptions {
  name: string;
  framework: 'react' | 'nextjs' | 'vue';
  language: 'typescript' | 'javascript';
  features: string[];
}

// ✅ Good: Use JSDoc for public functions
/**
 * Creates a new project from the specified template
 * @param options - Project configuration options
 * @returns Promise resolving to project creation result
 */
async function createProject(options: ProjectOptions): Promise<ProjectResult> {
  // Implementation
}

// ❌ Avoid: Any types and unclear function names
function doStuff(data: any): any {
  // Implementation
}
```

#### UI/UX Guidelines
```typescript
// ✅ Good: Use standardized help formatter
import { createStandardHelp, type CommandHelpConfig } from '../utils/helpFormatter.js';

const helpConfig: CommandHelpConfig = {
  commandName: 'your-command',
  emoji: '🚀',
  description: 'Command description',
  usage: ['pi your-command [options]'],
  options: [
    { flag: '--example', description: 'Example option' }
  ],
  examples: [
    { command: 'pi your-command', description: 'Basic usage' }
  ]
};

createStandardHelp(helpConfig);

// ✅ Good: Use spinner for long operations (avoid excessive loading messages)
const spinner = ora('Processing...').start();
// ... operation
spinner.succeed('Operation completed');
```

### Commit Message Convention

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

#### Types

| Type | Purpose | Example |
|------|---------|---------|
| **feat** | New feature | `feat(templates): add Vue.js support` |
| **fix** | Bug fix | `fix(check): resolve npm registry timeout` |
| **docs** | Documentation | `docs(readme): update installation guide` |
| **style** | Code style/formatting | `style(ui): apply consistent spacing` |
| **refactor** | Code refactoring | `refactor(cache): improve performance` |
| **test** | Testing | `test(commands): add unit tests for create` |
| **chore** | Maintenance | `chore(deps): update dependencies` |
| **perf** | Performance improvement | `perf(analytics): optimize data processing` |
| **build** | Build system | `build(ci): add GitHub Actions workflow` |

#### Examples
```bash
# Feature additions
feat(ai): add Claude integration for Express.js projects
feat(templates): add Angular Material template support
feat(commands): implement cache command with statistics

# Bug fixes
fix(docker): resolve build context issues in Windows
fix(analytics): correct dashboard data calculations
fix(templates): fix package.json template variables

# Documentation
docs(features): document new AI integration features
docs(contributing): add debugging and testing guidelines
docs(commands): update check command documentation
```

### Performance Guidelines

#### Optimized Loading
- **Caching**: Use caching for expensive operations (file reads, API calls)
- **Lazy Loading**: Load resources only when needed
- **Minimal Console Output**: Avoid excessive logging that slows startup
- **Async Operations**: Use async/await for I/O operations

```typescript
// ✅ Good: Cache expensive operations
let configCache: Config | null = null;

async function getConfig(): Promise<Config> {
  if (configCache) return configCache;
  
  configCache = await loadConfig();
  return configCache;
}

// ❌ Avoid: Excessive console output during startup
console.log('Loading feature 1...');
console.log('Loading feature 2...');
console.log('Loading feature 3...');
```

### Code Style

#### Formatting Rules
- **Indentation**: 2 spaces (no tabs)
- **Line Length**: 100 characters maximum
- **Quotes**: Single quotes for strings, double quotes for JSX attributes
- **Semicolons**: Always use semicolons
- **Trailing Commas**: Use trailing commas in objects and arrays

#### ESLint Configuration
```json
{
  "extends": [
    "@typescript-eslint/recommended",
    "prettier"
  ],
  "rules": {
    "@typescript-eslint/no-explicit-any": "warn",
    "@typescript-eslint/no-unused-vars": "error",
    "prefer-const": "error",
    "no-console": "off"
  }
}
```

### Testing Requirements

#### Unit Tests
- Write tests for all new utility functions
- Test error conditions and edge cases
- Maintain minimum 80% code coverage
- Use descriptive test names

```typescript
// ✅ Good test structure
describe('createProject', () => {
  it('should create React project with TypeScript successfully', async () => {
    const options = {
      name: 'test-app',
      framework: 'react',
      language: 'typescript'
    };
    
    const result = await createProject(options);
    
    expect(result.success).toBe(true);
    expect(result.projectPath).toContain('test-app');
  });
  
  it('should handle invalid framework gracefully', async () => {
    const options = {
      name: 'test-app',
      framework: 'invalid' as any,
      language: 'typescript'
    };
    
    await expect(createProject(options)).rejects.toThrow('Unsupported framework');
  });
});
```

#### Integration Tests
- Test complete command workflows
- Verify file creation and modification
- Test cross-platform compatibility

## 🔄 Pull Request Process

### Before Creating a PR

1. **Self-Review Checklist**
   - [ ] Code follows project style guidelines
   - [ ] All tests pass locally
   - [ ] No TypeScript errors or warnings
   - [ ] Documentation updated if needed
   - [ ] Commit messages follow convention
   - [ ] No debugging code or console.logs left
   - [ ] Performance impact considered

2. **Testing Checklist**
   - [ ] Tested on your primary OS
   - [ ] Tested with different package managers (npm, pnpm, yarn)
   - [ ] Tested with both TypeScript and JavaScript projects
   - [ ] Verified backwards compatibility

### PR Title and Description

**Title Format:**
```
<type>(<scope>): <description>
```

**Description Template:**
```markdown
## Description
Brief description of the changes and motivation.

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] This change requires a documentation update

## Testing
Describe the tests that you ran to verify your changes.

## Screenshots (if applicable)
Add screenshots to help explain your changes.

## Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
```

### Review Process

1. **Automated Checks**
   - CI/CD pipeline runs all tests
   - Code quality checks with ESLint
   - TypeScript compilation verification
   - Security vulnerability scanning

2. **Manual Review**
   - Code review by maintainers
   - Architecture and design review
   - Documentation review
   - Testing verification

3. **Approval and Merge**
   - At least one maintainer approval required
   - All automated checks must pass
   - Conflicts resolved and up-to-date with main branch

## 🐛 Issue Reporting

### Bug Reports

Use our bug report template for comprehensive reporting:

**Title:** `[BUG] Short description of the issue`

**Required Information:**
```markdown
## Bug Description
A clear and concise description of what the bug is.

## Steps to Reproduce
1. Run command '...'
2. Select option '...'
3. Observe error

## Expected Behavior
What you expected to happen.

## Actual Behavior
What actually happened.

## Environment
- OS: [e.g., Windows 11, macOS 13, Ubuntu 22.04]
- Node.js version: [e.g., 18.17.0]
- Package Manager: [e.g., pnpm 8.6.0]
- CLI Version: [e.g., 2.1.0]

## Additional Context
- Error logs or screenshots
- Project type and structure
- Any recent changes to your environment
```

### Feature Requests

**Title:** `[FEATURE] Short description of the feature`

**Required Information:**
```markdown
## Feature Description
A clear and concise description of the feature.

## Problem Statement
What problem does this solve?

## Proposed Solution
Describe how you envision this feature working.

## Use Cases
Provide specific use cases where this would be beneficial.

## Alternatives Considered
What alternatives have you considered?

## Additional Context
Any additional context, mockups, or examples.
```

### Priority Labels

| Label | Priority | Response Time |
|-------|----------|---------------|
| **critical** | P0 | 24 hours |
| **high** | P1 | 3-5 days |
| **medium** | P2 | 1-2 weeks |
| **low** | P3 | Next release cycle |
| **enhancement** | P4 | Community contribution welcome |
## 🛠️ Development Workflows

### Adding New Templates

#### 1. Template Structure Planning

**Framework Support Matrix:**
| Framework | TypeScript | JavaScript | Special Features |
|-----------|------------|------------|------------------|
| React | ✅ | ✅ | Vite, Create React App |
| Next.js | ✅ | ✅ | App Router, Pages Router |
| Vue.js | ✅ | ✅ | Composition API, Options API |
| Angular | ✅ | ❌ | Angular CLI, Material |
| Express.js | ✅ | ✅ | REST API, GraphQL |
| NestJS | ✅ | ❌ | Microservices, GraphQL |

#### 2. Template Creation Process

```bash
# 1. Create template directory structure
mkdir -p templates/framework-name/language/variant
cd templates/framework-name/language/variant

# Example: Next.js TypeScript with App Router
mkdir -p templates/nextjs/typescript/app-router
```

#### 3. Template File Requirements

**Required Files:**
- `package.json` - Dependencies and scripts
- `README.md` - Setup and usage instructions
- `tsconfig.json` (for TypeScript) - TypeScript configuration
- Framework-specific configuration files

**Template Variables:**
```typescript
// Use these variables in template files
{{PROJECT_NAME}}          // User-provided project name
{{PROJECT_DESCRIPTION}}   // Project description
{{AUTHOR_NAME}}          // Git user name
{{AUTHOR_EMAIL}}         // Git user email
{{CURRENT_YEAR}}         // Current year
{{FRAMEWORK_VERSION}}    // Framework version
{{LANGUAGE}}             // typescript or javascript
```

**Example package.json Template:**
```json
{
  "name": "{{PROJECT_NAME}}",
  "version": "0.1.0",
  "description": "{{PROJECT_DESCRIPTION}}",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  },
  "dependencies": {
    "next": "^14.0.0",
    "react": "^18.0.0",
    "react-dom": "^18.0.0"
  },
  "devDependencies": {
    "@types/node": "^20.0.0",
    "@types/react": "^18.0.0",
    "@types/react-dom": "^18.0.0",
    "typescript": "^5.0.0"
  }
}
```

#### 4. Template Registration (new structure)


This project now uses a category-first `templates/template.json` layout. Top-level keys are categories (for example `desktop`, `mobile`, `javascript`, `go`, `c++_c`), and each category contains frameworks as objects. Each framework may declare a `type` (used by prompts), `description`, `languages`, `ui`, `options`, and `templates`.

Example `templates/template.json` fragment:

```json
{
  "desktop": {
    "electron": {
      "type": "desktop",     
      "description": "Framework for building cross-platform desktop applications",
      "languages": ["javascript", "typescript"],
      "templates": ["electron-basic", "electron-tailwind"]
    }
  },
  "javascript": {
    "nextjs": {
      "type": "frontend",
      "description": "Full-stack React framework",
      "languages": ["javascript","typescript"],
      "ui": ["shadcn","material-ui"],
      "options": ["tailwind","src"],
      "templates": ["src-shadcn-tailwind-template"]
    }
  }
}
```

How to register a new template:

1. Add a new framework entry under the appropriate category in `templates/template.json`.
2. For each framework, set `type`, `description`, `languages`, and `templates` or `templates` grouped by language.
3. Use the helper functions in `src/utils/prompts.ts` when writing code that enumerates templates:

- `getAvailableTypes()` — returns the unique list of `type` values (e.g., `desktop`, `frontend`, `mobile`).
- `getAvailableFrameworks(type?: string)` — returns all frameworks or those matching a `type`.
- `getFrameworkConfig(framework)` — get the configuration object for a framework.

Example: adding templates for `nextjs` should look like:

```json
"javascript": {
  "nextjs": {
    "type": "frontend",
    "description": "Full-stack React framework",
    "languages": ["javascript","typescript"],
    "ui": ["shadcn"],
    "options": ["tailwind","src"],
    "templates": ["src-shadcn-tailwind-template"]
  }
}
```

Notes:
- When adding language-specific templates, you can provide `templates` as an object keyed by language. The prompts will select the appropriate templates based on the framework and language.
- Be careful to avoid committing large `node_modules` or build artifacts inside `templates/` — the template validator checks for unwanted directories.

#### 5. Testing Your Template

```bash
# Build the CLI
pnpm run build

# Test template creation
node dist/index.js create test-project
# Select your new template from the menu

# Verify the generated project
cd test-project
npm install
npm run dev
```

### Adding New Features

#### 1. Feature Structure

```
features/category/provider/
├── README.md                    # Feature documentation
├── config.json                  # Feature configuration
└── [framework]/
    ├── javascript/
    │   ├── files to create/modify
    │   └── package.json         # Dependencies to install
    └── typescript/
        ├── files to create/modify
        └── package.json         # Dependencies to install
```

#### 2. Feature Configuration

**config.json Example:**
```json
{
  "name": "Provider Name Integration",
  "description": "Detailed description of the feature",
  "category": "authentication",
  "provider": "clerk",
  "supportedFrameworks": ["nextjs", "react", "expressjs"],
  "supportedLanguages": ["javascript", "typescript"],
  "requiresApiKey": true,
  "environmentVariables": [
    "CLERK_PUBLISHABLE_KEY",
    "CLERK_SECRET_KEY"
  ],
  "dependencies": {
    "javascript": ["@clerk/nextjs", "@clerk/clerk-react"],
    "typescript": ["@clerk/nextjs", "@clerk/clerk-react", "@types/clerk"]
  },
  "documentation": "https://docs.clerk.dev/",
  "examples": [
    "examples/login-component.tsx",
    "examples/protected-route.tsx"
  ]
}
```

#### 3. Feature Implementation Files

**Authentication Example Structure:**
```
features/auth/clerk/
├── README.md
├── config.json
├── nextjs/
│   ├── javascript/
│   │   ├── middleware.js
│   │   ├── app/sign-in/page.js
│   │   ├── app/sign-up/page.js
│   │   ├── components/auth/UserProfile.js
│   │   ├── .env.local
│   │   └── package.json
│   └── typescript/
│       ├── middleware.ts
│       ├── app/sign-in/page.tsx
│       ├── app/sign-up/page.tsx
│       ├── components/auth/UserProfile.tsx
│       ├── types/auth.ts
│       ├── .env.local
│       └── package.json
└── react/
    └── [similar structure]
```

#### 4. Feature Registration

Update `src/utils/featureInstaller.ts`:

```typescript
// Add to SUPPORTED_FEATURES
export const SUPPORTED_FEATURES = {
  authentication: {
    name: 'Authentication',
    icon: '🔐',
    providers: [
      // ... existing providers
      {
        name: 'Your New Provider',
        id: 'your-provider',
        description: 'Provider description',
        frameworks: ['nextjs', 'react'],
        languages: ['typescript', 'javascript']
      }
    ]
  }
  // ... other categories
};
```

#### 5. Environment Variable Templates

**.env.local Template:**
```bash
# Authentication Configuration
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_your_key_here
CLERK_SECRET_KEY=sk_test_your_secret_here

# Optional: Customize sign-in/sign-up URLs
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
```

### Command Development

#### 1. Command Structure

```typescript
// src/commands/your-command.ts
import { Command } from 'commander';
import chalk from 'chalk';
import ora from 'ora';
import gradient from 'gradient-string';

/**
 * Show help for your command
 */
export function showYourCommandHelp(): void {
  const titleGradient = gradient(['#0072ff', '#00c6ff']);
  
  console.log('\n' + boxen(
    titleGradient('🚀 Your Command Help') + '\n\n' +
    chalk.white('Command description and usage information.') + '\n\n' +
    chalk.cyan('Usage:') + '\n' +
    chalk.white('  pi your-command [options]') + '\n\n' +
    chalk.cyan('Examples:') + '\n' +
    chalk.gray('  pi your-command --example'),
    {
      padding: 1,
      borderStyle: 'round',
      borderColor: 'blue',
      backgroundColor: 'black'
    }
  ));
}

/**
 * Main command implementation
 */
export async function yourCommand(options?: CommandOptions): Promise<void> {
  const spinner = ora('Processing...').start();
  
  try {
    // Command implementation
    spinner.succeed('Command completed successfully');
  } catch (error) {
    spinner.fail('Command failed');
    throw error;
  }
}
```

#### 2. Command Registration

Update `src/index.ts`:

```typescript
// Import your command
import { yourCommand, showYourCommandHelp } from './commands/your-command.js';

// Register the command
program
  .command('your-command')
  .description(chalk.hex('#10ac84')('🚀 Your command description'))
  .option('--example', 'Example option')
  .on('--help', () => {
    showYourCommandHelp();
  })
  .action(async (options) => {
    try {
      await yourCommand(options);
    } catch (error) {
      handleCommandError('your-command', error as Error);
    }
  });
```

## 📊 Testing Guidelines

### Unit Testing

#### Test Structure
```typescript
// tests/commands/create.test.ts
import { describe, it, expect, beforeEach, afterEach } from 'vitest';
import { createProject } from '../../src/commands/create';
import fs from 'fs-extra';
import path from 'path';

describe('createProject', () => {
  const testDir = path.join(__dirname, 'test-output');
  
  beforeEach(async () => {
    await fs.ensureDir(testDir);
  });
  
  afterEach(async () => {
    await fs.remove(testDir);
  });
  
  it('should create Next.js project successfully', async () => {
    const options = {
      name: 'test-nextjs-app',
      framework: 'nextjs',
      language: 'typescript',
      outputDir: testDir
    };
    
    const result = await createProject(options);
    
    expect(result.success).toBe(true);
    expect(await fs.pathExists(path.join(testDir, 'test-nextjs-app'))).toBe(true);
    expect(await fs.pathExists(path.join(testDir, 'test-nextjs-app/package.json'))).toBe(true);
  });
});
```

#### Mock External Dependencies
```typescript
// Mock fs operations
vi.mock('fs-extra', () => ({
  ensureDir: vi.fn(),
  copy: vi.fn(),
  writeJSON: vi.fn(),
  readJSON: vi.fn()
}));

// Mock child process
vi.mock('child_process', () => ({
  exec: vi.fn((cmd, callback) => {
    callback(null, { stdout: 'success', stderr: '' });
  })
}));
```

### Integration Testing

#### CLI Command Testing
```bash
#!/bin/bash
# tests/integration/test-cli.sh

echo "Testing CLI commands..."

# Test help command
node dist/index.js --help
if [ $? -ne 0 ]; then
  echo "❌ Help command failed"
  exit 1
fi

# Test create command
node dist/index.js create test-app --template=nextjs --language=typescript --no-install
if [ $? -ne 0 ]; then
  echo "❌ Create command failed"
  exit 1
fi

# Verify files were created
if [ ! -f "test-app/package.json" ]; then
  echo "❌ package.json not created"
  exit 1
fi

echo "✅ All CLI tests passed"
```

### Performance Testing

#### Benchmark Template Creation
```typescript
// tests/performance/template-creation.test.ts
import { performance } from 'perf_hooks';

describe('Template Creation Performance', () => {
  it('should create templates within acceptable time limits', async () => {
    const frameworks = ['react', 'nextjs', 'vue'];
    
    for (const framework of frameworks) {
      const startTime = performance.now();
      
      await createProject({
        name: `test-${framework}`,
        framework,
        language: 'typescript'
      });
      
      const endTime = performance.now();
      const duration = endTime - startTime;
      
      // Template creation should complete within 30 seconds
      expect(duration).toBeLessThan(30000);
    }
  });
});
```

### Cross-Platform Testing

#### Test Matrix
| OS | Node.js | Package Manager | Status |
|----|---------|-----------------|--------|
| Windows 11 | 18.x | npm | ✅ |
| Windows 11 | 18.x | pnpm | ✅ |
| Windows 11 | 20.x | yarn | ✅ |
| macOS 13 | 18.x | npm | ✅ |
| macOS 13 | 18.x | pnpm | ✅ |
| Ubuntu 22.04 | 18.x | npm | ✅ |
| Ubuntu 22.04 | 20.x | pnpm | ✅ |

## 🏆 Recognition

### Contributors Hall of Fame

Contributors are recognized in multiple ways:

#### 🥇 Gold Contributors (10+ significant PRs)
- Featured in README.md
- Special mention in release notes
- Early access to new features

#### 🥈 Silver Contributors (5+ PRs)
- Listed in contributors section
- Mentioned in monthly updates

#### 🥉 Bronze Contributors (1+ PR)
- GitHub contributors page
- Thank you in PR comments

### Contribution Types

| Type | Recognition | Examples |
|------|-------------|----------|
| **🐛 Bug Fixes** | Bug Hunter Badge | Critical bug fixes, edge case handling |
| **✨ Features** | Feature Creator Badge | New commands, templates, integrations |
| **📚 Documentation** | Documentation Master Badge | Guides, examples, API docs |
| **🧪 Testing** | Quality Guardian Badge | Test coverage, CI/CD improvements |
| **🎨 Design** | UI/UX Enhancer Badge | Banner designs, CLI experience |
| **🌍 Localization** | Global Contributor Badge | Translations, i18n support |

### Monthly Contributor Spotlight

Each month we feature a contributor who made significant impact:
- Blog post about their contributions
- Social media shoutout
- Special badge in Discord/GitHub

## 💬 Community and Support

### Communication Channels

#### GitHub
- **Issues**: Bug reports and feature requests
- **Discussions**: Questions, ideas, and general discussion
- **Pull Requests**: Code contributions and reviews

#### Development Guidelines

1. **Ask Before Starting**: For large features, open an issue first to discuss
2. **Small PRs**: Keep pull requests focused and small when possible
3. **Documentation**: Update docs for any user-facing changes
4. **Tests**: Add tests for new functionality
5. **Backwards Compatibility**: Maintain compatibility unless absolutely necessary

### Getting Help

#### For Contributors
- 📖 **Documentation**: Start with this guide and other docs
- 💬 **GitHub Discussions**: Ask questions and get help from the community
- 🐛 **Issues**: Report bugs or request clarification
- 📧 **Direct Contact**: For security issues or private inquiries

#### Response Times
- **Bug Reports**: 24-48 hours for initial response
- **Feature Requests**: 3-5 days for initial feedback
- **Pull Requests**: 48-72 hours for initial review
- **Questions**: 24 hours for community discussion responses

## 📜 License and Legal

### MIT License

By contributing to Package Installer CLI, you agree that your contributions will be licensed under the MIT License. This means:

✅ **Permissions:**
- Commercial use
- Modification
- Distribution
- Private use

❗ **Conditions:**
- License and copyright notice must be included
- Changes must be documented

❌ **Limitations:**
- No liability or warranty provided

### Copyright Assignment

- You retain copyright to your contributions
- You grant Package Installer CLI and its users a perpetual, worldwide, non-exclusive license
- You warrant that you have the right to make such grants

### Code of Conduct Enforcement

Violations of our Code of Conduct may result in:
1. **Warning**: First offense, educational response
2. **Temporary Ban**: Repeated violations, time-limited restriction
3. **Permanent Ban**: Severe or repeated violations after warnings

## 📈 Performance Optimizations (v3.7.0)

### Latest Performance Improvements

| Improvement | Impact | Implementation |
|-------------|--------|----------------|
| **Feature Loading Cache** | 70% faster startup | Cached JSON configuration parsing |
| **Reduced Console Output** | Cleaner UX | Removed excessive loading messages |
| **Lazy Configuration Loading** | Instant commands | On-demand resource loading |
| **Optimized File Operations** | 2x faster I/O | Efficient file reading patterns |

### Performance Guidelines for Contributors

```typescript
// ✅ Good: Cache expensive operations
let configCache: Config | null = null;

async function getConfig(): Promise<Config> {
  if (configCache) return configCache;
  configCache = await loadExpensiveConfig();
  return configCache;
}

// ❌ Avoid: Repeated expensive operations
async function badGetConfig(): Promise<Config> {
  return await loadExpensiveConfig(); // Called every time!
}

// ✅ Good: Minimal startup logging
// Only show critical information

// ❌ Avoid: Excessive startup messages
console.log('Loading feature 1...');
console.log('Loading feature 2...');
console.log('Processing...');
```

### Benchmarks

- **CLI Startup**: <1 second (down from 2-3 seconds in v3.6.0)
- **Feature Loading**: 70% improvement with caching
- **Memory Usage**: 50-150MB typical, optimized garbage collection
- **Network Requests**: Cached to minimize API calls

---

<div align="center">

## 🚀 Ready to Contribute?

**Thank you for contributing to Package Installer CLI v3.7.0!**

Your efforts help make development easier and more enjoyable for developers worldwide.

[![Start Contributing](https://img.shields.io/badge/Start-Contributing-blue?style=for-the-badge&logo=github)](https://github.com/0xshariq/devforge-cli/fork)

*Happy coding! 💙*

</div>

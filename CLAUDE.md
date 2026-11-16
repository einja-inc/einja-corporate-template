# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Core development commands:
- `npm run dev` - Start development server with Turbopack (clears .next cache first)
- `npm run build` - Production build (runs Panda CSS codegen first)
- `npm run start` - Start production server
- `npm run storybook` - Start Storybook development server on port 6006

### Code quality commands:
- `npm run lint` - Check code with Biome linter
- `npm run lint:fix` - Auto-fix linting issues with Biome
- `npm run format` - Check code formatting with Biome
- `npm run format:fix` - Auto-format code with Biome
- `npm run typecheck` - TypeScript type checking

### Testing:
- Tests run via Vitest with Storybook integration
- Browser testing uses Playwright with Chromium
- Setup files located in `.storybook/vitest.setup.ts`

## Architecture

### Styling System:
- **Panda CSS** for styling with design tokens and recipes
- CSS-in-JS with type-safe style generation
- Styled components output to `styled-system/` directory
- Custom breakpoints: sm(640px), md(768px), lg(1024px), xl(1280px), 2xl(1440px)

### Pre-built Recipes:
- `button` - Three variants (solid, outline, ghost) with size options (sm, md, lg)
- `text` - Typography with size, weight, alignment, and transform variants
- `heading` - H1-H6 with semantic level variants and alignment options

### Component Structure:
- Components follow pattern: `src/components/ComponentName/`
- Each component has: `ComponentName.tsx`, `ComponentName.stories.tsx`, `index.ts`
- Components use Panda CSS recipes for styling
- Forward refs pattern for all interactive components

### Code Quality:
- **Biome** for linting and formatting (tab indentation, double quotes)
- Husky pre-commit hooks with lint-staged
- Ignores `styled-system/` directory in formatting/linting

### Framework Setup:
- Next.js 15 with App Router
- React 19
- TypeScript with strict type checking
- Volta for Node.js version management (v22.23.4)

### Special Notes:
- Always run `panda codegen` before building for production
- Biome uses tab indentation and double quotes
- ESLint is disabled during builds (using Biome instead)

<!-- einja-harness:start core -->
## 体制の根幹

チームは自己組織化して、自分で決めて進める。人の判断待ちで止まらない。人の作業待ちで止まるのは、AI チームの怠慢である。人は、筋の悪いものだけ止める。止められたら、仕組みを直して、同じ筋の悪さが出ないようにしてから出し直す。

決めたことは、根拠を1つの URL で示して進める。

例外は2つだけ。すでに使われている本番（Doop など）は慎重に扱う。人が行うのは、AI が開いた画面でのパスワード、二段階認証、支払い確定の入力だけである。画面を開くことと、そのあとの作業は AI が行う。WorkOS の再認可、MCP の再認可、ブラウザ操作、設定は、人の操作ではない。

一輝さんへの作業依頼は原則禁止。手順は渡さない。パスワード、二段階認証、支払い確定の入力が要るときだけ、AI が開いたその画面の前で待つ。

正本は einja-skills の `docs/ai-ops/judgment-principles.md`（D-2026-11-17-02、D-2026-11-17-03、D-2026-11-17-04）。
<!-- einja-harness:end core -->

# ecommerce-platform

```text
ecommerce-platform/
├─ app/
│  ├─ layout.tsx            # Main layout with header/footer
│  ├─ page.tsx              # Home page
│  ├─ products/
│  │  └─ [slug]/page.tsx    # Product detail
│  └─ categories/
│     └─ [slug]/page.tsx    # Category listing
├─ components/
│  ├─ Card.tsx              # Reusable card component
│  ├─ ProductCard.tsx
│  ├─ CategoryCard.tsx
│  ├─ Navbar.tsx
│  ├─ Footer.tsx
│  ├─ Button.tsx
│  ├─ Input.tsx
│  └─ Modal.tsx
├─ lib/
│  ├─ api.ts                # Axios instance
│  └─ auth.ts               # JWT auth helpers
├─ hooks/
│  └─ useFetch.ts           # SWR fetching hook
├─ types/
│  ├─ product.ts
│  └─ user.ts
├─ pages/
│  └─ api/                  # Next.js API routes
│     ├─ auth/
│     │  ├─ login.ts
│     │  └─ register.ts
│     ├─ products.ts
│     └─ categories.ts
├─ tailwind.config.js
├─ postcss.config.js
└─ package.json

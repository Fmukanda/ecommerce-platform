# ecommerce-platform
Important notes & next steps (what I couldn't fully complete here)

Backend contract assumptions: I assumed Django endpoints:

POST /auth/login/ returns { access: 'jwt', refresh?: '...' }.

POST /auth/register/ for registration.

GET /products/, GET /categories/.

POST /orders/create/ to create an order.

POST /payments/stripe/create-session/ and POST /payments/mpesa/stk/ for payments.
If your backend uses different routes or response shapes, update lib/api.ts, app/providers/AuthProvider.tsx, and lib/payments.ts accordingly.

Security: Tokens are stored in localStorage in this skeleton for simplicity. For production, switch to HttpOnly secure cookies (backend should set them) and adjust the client accordingly.

Stripe & M-Pesa: I added stubs that call backend endpoints. You still need server-side integrations (create Stripe session, handle M-Pesa callbacks) in Django. I can scaffold the Django endpoints if you want.

Pixel-perfect UI tweaks: I matched the flat, spaced card aesthetic and added SVG assets. If you want exact pixel parity with your screenshot (fonts, precise paddings, icons), I can further refine:

Use Inter variable font and exact sizes,

Tweak Tailwind theme scales,

Add iconography (Heroicons or custom SVGs),

Add animations or hover states to match the reference.

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

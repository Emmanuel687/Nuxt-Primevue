# Sunglasses Ecommerce Website - Folder Structure

```
sunglasses-ecommerce/
├── .env                           # Environment variables
├── .env.example                   # Environment template
├── .gitignore
├── package.json
├── nuxt.config.ts                 # Main Nuxt configuration
├── tailwind.config.js             # Tailwind configuration
├── tsconfig.json                  # TypeScript configuration
├── prisma/                        # Database schema & migrations
│   ├── schema.prisma
│   ├── migrations/
│   └── seed.ts
│
├── assets/                        # Static assets
│   ├── css/
│   │   ├── main.css              # Global styles
│   │   └── components.css        # Component-specific styles
│   ├── images/
│   │   ├── logo/
│   │   ├── banners/
│   │   └── icons/
│   └── fonts/
│
├── components/                    # Reusable Vue components
│   ├── common/                   # Shared between client & admin
│   │   ├── BaseButton.vue
│   │   ├── BaseModal.vue
│   │   ├── BaseInput.vue
│   │   ├── BaseSelect.vue
│   │   ├── LoadingSpinner.vue
│   │   └── ImageUpload.vue
│   │
│   ├── client/                   # Client-side components
│   │   ├── layout/
│   │   │   ├── Header.vue
│   │   │   ├── Footer.vue
│   │   │   ├── Navigation.vue
│   │   │   └── MobileMenu.vue
│   │   ├── product/
│   │   │   ├── ProductCard.vue
│   │   │   ├── ProductGrid.vue
│   │   │   ├── ProductFilter.vue
│   │   │   ├── ProductGallery.vue
│   │   │   ├── ProductReviews.vue
│   │   │   └── ProductDetails.vue
│   │   ├── cart/
│   │   │   ├── CartItem.vue
│   │   │   ├── CartSummary.vue
│   │   │   └── CartDrawer.vue
│   │   ├── checkout/
│   │   │   ├── CheckoutForm.vue
│   │   │   ├── PaymentForm.vue
│   │   │   ├── ShippingForm.vue
│   │   │   └── OrderSummary.vue
│   │   ├── auth/
│   │   │   ├── LoginForm.vue
│   │   │   ├── RegisterForm.vue
│   │   │   └── ForgotPassword.vue
│   │   └── account/
│   │       ├── ProfileForm.vue
│   │       ├── OrderHistory.vue
│   │       └── AddressBook.vue
│   │
│   └── admin/                    # Admin-side components
│       ├── layout/
│       │   ├── AdminHeader.vue
│       │   ├── AdminSidebar.vue
│       │   └── AdminBreadcrumb.vue
│       ├── dashboard/
│       │   ├── StatsCard.vue
│       │   ├── SalesChart.vue
│       │   └── RecentOrders.vue
│       ├── products/
│       │   ├── ProductForm.vue
│       │   ├── ProductTable.vue
│       │   ├── CategoryForm.vue
│       │   └── BulkActions.vue
│       ├── orders/
│       │   ├── OrderTable.vue
│       │   ├── OrderDetails.vue
│       │   └── OrderStatus.vue
│       ├── customers/
│       │   ├── CustomerTable.vue
│       │   └── CustomerDetails.vue
│       └── inventory/
│           ├── StockTable.vue
│           └── StockAlert.vue
│
├── composables/                  # Vue composables (reusable logic)
│   ├── useAuth.ts               # Authentication logic
│   ├── useCart.ts               # Shopping cart management
│   ├── useProducts.ts           # Product operations
│   ├── useOrders.ts             # Order management
│   ├── usePayment.ts            # Payment processing
│   ├── useUpload.ts             # File upload (Cloudinary)
│   ├── useNotification.ts       # Toast notifications
│   └── useValidation.ts         # Form validation
│
├── layouts/                     # Nuxt layouts
│   ├── default.vue              # Client layout
│   ├── admin.vue                # Admin layout
│   ├── auth.vue                 # Authentication pages layout
│   └── checkout.vue             # Checkout process layout
│
├── middleware/                  # Route middleware
│   ├── auth.ts                  # Authentication guard
│   ├── admin.ts                 # Admin access guard
│   ├── guest.ts                 # Guest-only pages
│   └── checkout.ts              # Checkout flow guard
│
├── pages/                       # File-based routing
│   ├── index.vue                # Homepage
│   ├── shop/                    # Product pages
│   │   ├── index.vue            # Product listing
│   │   ├── [category]/
│   │   │   └── index.vue        # Category page
│   │   └── [slug].vue           # Product detail page
│   ├── cart.vue                 # Shopping cart
│   ├── checkout/                # Checkout flow
│   │   ├── index.vue            # Checkout page
│   │   ├── shipping.vue         # Shipping details
│   │   ├── payment.vue          # Payment page
│   │   └── success.vue          # Order confirmation
│   ├── account/                 # User account
│   │   ├── index.vue            # Account dashboard
│   │   ├── profile.vue          # Profile settings
│   │   ├── orders.vue           # Order history
│   │   └── addresses.vue        # Address management
│   ├── auth/                    # Authentication
│   │   ├── login.vue
│   │   ├── register.vue
│   │   ├── forgot-password.vue
│   │   └── reset-password.vue
│   ├── admin/                   # Admin pages
│   │   ├── index.vue            # Admin dashboard
│   │   ├── products/
│   │   │   ├── index.vue        # Products list
│   │   │   ├── create.vue       # Add product
│   │   │   ├── [id]/
│   │   │   │   ├── edit.vue     # Edit product
│   │   │   │   └── index.vue    # Product details
│   │   │   └── categories/
│   │   │       ├── index.vue    # Categories list
│   │   │       └── create.vue   # Add category
│   │   ├── orders/
│   │   │   ├── index.vue        # Orders list
│   │   │   └── [id].vue         # Order details
│   │   ├── customers/
│   │   │   ├── index.vue        # Customers list
│   │   │   └── [id].vue         # Customer details
│   │   ├── inventory/
│   │   │   └── index.vue        # Inventory management
│   │   └── settings/
│   │       ├── index.vue        # General settings
│   │       ├── shipping.vue     # Shipping settings
│   │       └── payments.vue     # Payment settings
│   ├── about.vue                # About page
│   ├── contact.vue              # Contact page
│   ├── privacy.vue              # Privacy policy
│   └── terms.vue                # Terms of service
│
├── plugins/                     # Nuxt plugins
│   ├── auth.client.ts           # Client-side auth
│   ├── prisma.server.ts         # Server-side database
│   ├── cloudinary.client.ts     # Image upload
│   ├── paystack.client.ts       # Payment integration
│   └── headlessui.client.ts     # Headless UI components
│
├── public/                      # Static files
│   ├── favicon.ico
│   ├── robots.txt
│   ├── sitemap.xml
│   └── images/
│       ├── placeholders/
│       └── brand/
│
├── server/                      # Server-side code
│   ├── api/                     # API routes
│   │   ├── auth/
│   │   │   ├── login.post.ts
│   │   │   ├── register.post.ts
│   │   │   ├── logout.post.ts
│   │   │   └── refresh.post.ts
│   │   ├── products/
│   │   │   ├── index.get.ts     # Get all products
│   │   │   ├── [id].get.ts      # Get single product
│   │   │   ├── [id].put.ts      # Update product
│   │   │   ├── [id].delete.ts   # Delete product
│   │   │   └── index.post.ts    # Create product
│   │   ├── categories/
│   │   │   ├── index.get.ts
│   │   │   └── index.post.ts
│   │   ├── orders/
│   │   │   ├── index.get.ts
│   │   │   ├── index.post.ts
│   │   │   └── [id]/
│   │   │       ├── index.get.ts
│   │   │       └── status.put.ts
│   │   ├── cart/
│   │   │   ├── index.get.ts
│   │   │   ├── add.post.ts
│   │   │   ├── update.put.ts
│   │   │   └── remove.delete.ts
│   │   ├── payment/
│   │   │   ├── initialize.post.ts
│   │   │   ├── verify.post.ts
│   │   │   └── webhook.post.ts
│   │   ├── upload/
│   │   │   └── image.post.ts
│   │   └── admin/
│   │       ├── dashboard/
│   │       │   └── stats.get.ts
│   │       ├── users/
│   │       │   └── index.get.ts
│   │       └── reports/
│   │           ├── sales.get.ts
│   │           └── inventory.get.ts
│   ├── middleware/               # Server middleware
│   │   ├── auth.ts
│   │   ├── admin.ts
│   │   └── cors.ts
│   └── utils/                   # Server utilities
│       ├── db.ts                # Database connection
│       ├── auth.ts              # Auth helpers
│       ├── email.ts             # Email utilities
│       ├── validation.ts        # Server-side validation
│       └── cloudinary.ts        # Image upload helpers
│
├── stores/                      # Pinia stores (state management)
│   ├── auth.ts                  # Authentication state
│   ├── cart.ts                  # Shopping cart state
│   ├── products.ts              # Products state
│   ├── orders.ts                # Orders state
│   └── admin.ts                 # Admin-specific state
│
├── types/                       # TypeScript type definitions
│   ├── auth.ts                  # Authentication types
│   ├── product.ts               # Product-related types
│   ├── order.ts                 # Order types
│   ├── user.ts                  # User types
│   ├── cart.ts                  # Cart types
│   └── api.ts                   # API response types
│
├── utils/                       # Client-side utilities
│   ├── constants.ts             # App constants
│   ├── helpers.ts               # General helper functions
│   ├── formatters.ts            # Data formatting
│   ├── validators.ts            # Form validation rules
│   └── api.ts                   # API client helpers
│
└── tests/                       # Test files
    ├── components/              # Component tests
    ├── pages/                   # Page tests
    ├── api/                     # API tests
    └── utils/                   # Utility tests
```

## Key Structure Benefits:

### 1. **Clear Separation**
- Client and admin components are clearly separated
- Shared components in `common/` folder
- Dedicated layouts for different user types

### 2. **Scalable Organization**
- Feature-based folder structure
- Logical grouping of related functionality
- Easy to locate and maintain code

### 3. **Nuxt 3 Best Practices**
- File-based routing in `pages/`
- Server API routes in `server/api/`
- Composables for reusable logic
- Middleware for route protection

### 4. **TypeScript Support**
- Dedicated `types/` folder for type definitions
- Strong typing throughout the application

### 5. **Development Workflow**
- Environment configuration
- Testing structure
- Clear separation of concerns

This structure supports your tech stack perfectly and provides room for future expansion while maintaining clean organization.
# 🛵 QuickDrop - 10-Minute Delivery Platform

> Ultra-fast delivery platform connecting customers, riders, and store managers in real-time. Built with modern web technologies and deployed on free-tier cloud infrastructure.

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://quickdrop-web.vercel.app)
[![API Status](https://img.shields.io/badge/API-online-success)](https://quickdrop-api.vercel.app)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## 🌐 Live Demo

| Platform | URL | Description |
|----------|-----|-------------|
| **Admin Dashboard** | [quickdrop-web.vercel.app](https://quickdrop-web.vercel.app) | React.js web dashboard with live fleet tracking |
| **API Backend** | [quickdrop-api.vercel.app](https://quickdrop-api.vercel.app) | Next.js REST API with Supabase integration |
| **Mobile App (Expo Go)** | [Open in Expo Go](https://expo.dev/@vairag310/quickdrop-mobile) | React Native app for customers & riders |

### 📱 Mobile App Access

**Option 1: Expo Go (Instant Access)**
1. Install [Expo Go](https://expo.dev/go) on your phone
2. Open: https://expo.dev/@vairag310/quickdrop-mobile
3. App loads instantly!

**Option 2: Scan QR Code**

![QuickDrop Mobile QR Code](https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=https://expo.dev/preview/update?message=Your+update+message&updateRuntimeVersion=1.0.0&createdAt=2026-05-19T15%3A49%3A01.168Z&slug=exp&projectId=6416a0a4-dcfd-491c-a1fb-821d035b1f5e&group=da20a29a-6943-460c-ad34-0ef953744d4e).

**Option 3: Deep Link**
```
exp://u.expo.dev/6416a0a4-dcfd-491c-a1fb-821d035b1f5e?channel-name=production
```

**Latest Update Details:**
- 📦 [Update Dashboard](https://expo.dev/preview/update?message=Your+update+message&updateRuntimeVersion=1.0.0&createdAt=2026-05-19T15%3A49%3A01.168Z&slug=exp&projectId=6416a0a4-dcfd-491c-a1fb-821d035b1f5e&group=da20a29a-6943-460c-ad34-0ef953744d4e)
- 🔗 Update Deep Link: `exp+://expo-development-client/?url=https%3A%2F%2Fu.expo.dev%2F6416a0a4-dcfd-491c-a1fb-821d035b1f5e%2Fgroup%2Fda20a29a-6943-460c-ad34-0ef953744d4e`
- 📅 Published: May 19, 2026
- 🏷️ Runtime Version: 1.0.0

---

## 📸 Screenshots

### Admin Dashboard
```
[Dashboard Screenshot - Live order tracking, fleet map, inventory management]
```

### Mobile App (Customer & Rider)
```
[Mobile Screenshots - Product catalog, cart, order tracking, rider delivery interface]
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Frontend (Web)** | React 18 + Vite + TypeScript | Admin dashboard with real-time updates |
| **Frontend (Mobile)** | React Native + Expo 51 | Cross-platform iOS/Android app |
| **Backend API** | Next.js 16 + TypeScript | RESTful API with serverless functions |
| **Database** | Supabase (PostgreSQL) | Real-time database with auth & storage |
| **State Management** | TanStack Query (React Query) | Server state caching & synchronization |
| **Navigation** | React Router (Web) + React Navigation (Mobile) | Client-side routing |
| **Styling** | Tailwind CSS | Utility-first responsive design |
| **Icons** | Lucide React | Modern icon library |
| **Deployment** | Vercel (Web + API) + Expo (Mobile) | Free-tier cloud hosting |
| **Version Control** | Git + GitHub | Source code management |

---

## ✨ Features

### 🎯 Core Functionality
- **Real-time Order Tracking** - Live status updates from order placement to delivery
- **Admin Dashboard** - Comprehensive control panel with live fleet map visualization
- **Customer Mobile App** - Browse products, manage cart, track orders in real-time
- **Rider Mobile App** - Accept orders, navigate to customers, update delivery status
- **Inventory Management** - Stock tracking with low-stock alerts and restock workflows
- **Role-Based Access Control** - Secure authentication for Admin, Store Manager, Rider, and Customer roles

### 📊 Admin Dashboard Features
- Live order monitoring with status filters
- Interactive fleet map showing rider locations
- Product catalog management (CRUD operations)
- Inventory control with stock level indicators
- Rider assignment and performance tracking
- Real-time analytics and order statistics

### 📱 Mobile App Features
- **Customer Side:**
  - Product browsing by category
  - Shopping cart with quantity management
  - Order placement with delivery address
  - Real-time order status tracking
  - Order history

- **Rider Side:**
  - Available orders list
  - Order acceptance workflow
  - Customer location and contact info
  - Status update controls (Picking → Dispatched → Delivered)
  - Earnings tracking

---

## 🚀 Local Setup

### Prerequisites
- Node.js 18+ and npm
- Git
- Expo Go app (for mobile testing)
- Supabase account (free tier)

### 1️⃣ Clone Repository
```bash
git clone https://github.com/yourusername/quickdrop.git
cd quickdrop
```

### 2️⃣ Setup API Backend
```bash
cd quickdrop-api
npm install

# Create .env.local file
echo NEXT_PUBLIC_SUPABASE_URL=your_supabase_url > .env.local
echo NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key >> .env.local

npm run dev
# API runs on http://localhost:3000
```

### 3️⃣ Setup Web Dashboard
```bash
cd ../quickdrop-web
npm install

# Create .env file
echo VITE_API_URL=http://localhost:3000 > .env
echo VITE_SUPABASE_URL=your_supabase_url >> .env
echo VITE_SUPABASE_ANON_KEY=your_supabase_anon_key >> .env

npm run dev
# Dashboard runs on http://localhost:5173
```

### 4️⃣ Setup Mobile App
```bash
cd ../quickdrop-mobile
npm install

# Create .env file
echo EXPO_PUBLIC_API_URL=http://localhost:3000 > .env
echo EXPO_PUBLIC_SUPABASE_URL=your_supabase_url >> .env
echo EXPO_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key >> .env

npx expo start
# Scan QR code with Expo Go app
```

### 5️⃣ Database Setup (Supabase)
1. Create a new Supabase project at [supabase.com](https://supabase.com)
2. Run the SQL schema (see Database Schema section below)
3. Copy your project URL and anon key to `.env` files
4. Enable Row Level Security (RLS) policies for production

---

## 📡 API Endpoints

### Orders
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/orders` | Fetch all orders with customer & rider details |
| `POST` | `/api/orders` | Create new order with items |
| `PATCH` | `/api/orders/[id]` | Update order status or assign rider |
| `DELETE` | `/api/orders/[id]` | Cancel/delete order |

### Products
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/products` | Fetch all products (optional `?category=` filter) |
| `GET` | `/api/products/[id]` | Fetch single product details |
| `POST` | `/api/products` | Create new product (admin only) |
| `PATCH` | `/api/products` | Update product stock (increment/decrement) |
| `DELETE` | `/api/products/[id]` | Delete product (admin only) |

### Riders
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/riders` | Fetch all riders with active order count |
| `GET` | `/api/riders/[id]` | Fetch rider details and order history |
| `PATCH` | `/api/riders/[id]` | Update rider status/location |

### Users (Auth)
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/auth/signup` | Register new user |
| `POST` | `/api/auth/login` | Authenticate user |
| `GET` | `/api/auth/me` | Get current user profile |

---

## 🗄️ Database Schema

```
┌─────────────────────────────────────────────────────────────────┐
│                         USERS TABLE                              │
├──────────────┬──────────────┬─────────────────────────────────┤
│ id           │ UUID         │ PRIMARY KEY                      │
│ email        │ VARCHAR      │ UNIQUE, NOT NULL                 │
│ name         │ VARCHAR      │ NOT NULL                         │
│ phone        │ VARCHAR      │                                  │
│ role         │ ENUM         │ admin/store/rider/customer       │
│ created_at   │ TIMESTAMP    │ DEFAULT NOW()                    │
└──────────────┴──────────────┴─────────────────────────────────┘
                              │
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
        ▼                     ▼                     ▼
┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐
│  PRODUCTS TABLE   │  │   ORDERS TABLE    │  │   RIDERS TABLE    │
├─────────┬─────────┤  ├─────────┬─────────┤  ├─────────┬─────────┤
│ id      │ UUID PK │  │ id      │ UUID PK │  │ user_id │ UUID FK │
│ name    │ VARCHAR │  │ customer│ UUID FK │  │ status  │ ENUM    │
│ price   │ DECIMAL │  │ rider   │ UUID FK │  │ lat     │ FLOAT   │
│ stock   │ INTEGER │  │ status  │ ENUM    │  │ lng     │ FLOAT   │
│ category│ VARCHAR │  │ total   │ DECIMAL │  │ vehicle │ VARCHAR │
│ image   │ TEXT    │  │ address │ TEXT    │  └─────────┴─────────┘
└─────────┴─────────┘  └─────────┴─────────┘
                              │
                              │
                              ▼
                    ┌───────────────────┐
                    │ ORDER_ITEMS TABLE │
                    ├─────────┬─────────┤
                    │ id      │ UUID PK │
                    │ order_id│ UUID FK │
                    │ product │ UUID FK │
                    │ quantity│ INTEGER │
                    │ price   │ DECIMAL │
                    └─────────┴─────────┘
```

### Key Relationships
- `orders.customer_id` → `users.id` (Customer who placed order)
- `orders.rider_id` → `users.id` (Rider assigned to delivery)
- `order_items.order_id` → `orders.id` (Items in order)
- `order_items.product_id` → `products.id` (Product reference)

### Enums
- **User Role**: `admin`, `store`, `rider`, `customer`
- **Order Status**: `pending`, `picking`, `dispatched`, `delivered`, `cancelled`
- **Rider Status**: `available`, `busy`, `offline`

---

## 📁 Project Structure

```
QuickDrop/
│
├── quickdrop-api/              # Next.js API Backend
│   ├── app/
│   │   ├── api/
│   │   │   ├── orders/
│   │   │   │   ├── route.ts           # GET, POST orders
│   │   │   │   └── [id]/route.ts      # PATCH, DELETE order
│   │   │   ├── products/route.ts      # Product CRUD
│   │   │   └── riders/route.ts        # Rider management
│   │   └── layout.tsx
│   ├── lib/
│   │   └── supabase.ts         # Supabase client config
│   ├── .env.local              # Environment variables
│   └── package.json
│
├── quickdrop-web/              # React Admin Dashboard
│   ├── src/
│   │   ├── components/
│   │   │   ├── Dashboard.tsx
│   │   │   ├── OrdersTable.tsx
│   │   │   ├── FleetMap.tsx
│   │   │   └── InventoryManager.tsx
│   │   ├── pages/
│   │   │   ├── Login.tsx
│   │   │   ├── Orders.tsx
│   │   │   ├── Products.tsx
│   │   │   └── Riders.tsx
│   │   ├── hooks/
│   │   │   └── useOrders.ts    # React Query hooks
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── .env                    # Environment variables
│   └── package.json
│
└── quickdrop-mobile/           # React Native Mobile App
    ├── src/
    │   ├── screens/
    │   │   ├── customer/
    │   │   │   ├── HomeScreen.tsx
    │   │   │   ├── CartScreen.tsx
    │   │   │   └── OrdersScreen.tsx
    │   │   └── rider/
    │   │       ├── OrdersListScreen.tsx
    │   │       └── DeliveryScreen.tsx
    │   ├── components/
    │   │   ├── ProductCard.tsx
    │   │   └── OrderCard.tsx
    │   ├── context/
    │   │   └── AuthContext.tsx
    │   └── navigation/
    │       └── AppNavigator.tsx
    ├── App.tsx
    ├── .env                    # Environment variables
    └── package.json
```

---

## 🔐 Environment Variables

### API Backend (`.env.local`)
```env
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
```

### Web Dashboard (`.env`)
```env
VITE_API_URL=https://quickdrop-api.vercel.app
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
```

### Mobile App (`.env`)
```env
EXPO_PUBLIC_API_URL=https://quickdrop-api.vercel.app
EXPO_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
EXPO_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
```

---

## 🚢 Deployment

### Vercel (API + Web)
1. Push code to GitHub
2. Import project in Vercel dashboard
3. Add environment variables
4. Deploy automatically on push to `main`

### Expo (Mobile)
```bash
cd quickdrop-mobile
eas build --platform android
eas submit --platform android
```

---

## 🧪 Testing

### API Testing
```bash
cd quickdrop-api
npm run test
```

### Web Testing
```bash
cd quickdrop-web
npm run test
```

### Mobile Testing
- Use Expo Go for development testing
- Use EAS Build for production testing

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Your Name**

- LinkedIn: [Your LinkedIn Profile](https://www.linkedin.com/in/your-profile)
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your.email@example.com

---

## 🙏 Acknowledgments

- [Supabase](https://supabase.com) - Backend infrastructure
- [Vercel](https://vercel.com) - Hosting platform
- [Expo](https://expo.dev) - Mobile development framework
- [Tailwind CSS](https://tailwindcss.com) - Styling framework
- [Lucide Icons](https://lucide.dev) - Icon library

---

## 📊 Project Stats

- **Total Lines of Code**: ~5,000+
- **API Endpoints**: 12+
- **Database Tables**: 5
- **Mobile Screens**: 10+
- **Development Time**: 2 weeks
- **Deployment Cost**: $0 (Free tier)

---

<div align="center">

**⭐ Star this repo if you find it useful!**

Made with ❤️ and ☕ by [Your Name]

</div>

# Bagisto E-Commerce Platform

## Overview

Bagisto is a free and open-source Laravel e-commerce framework built for enterprises. It provides a complete solution for building online stores with features including multi-channel support, product management, customer management, order processing, payment integrations, and shipping methods.

The platform follows a modular architecture where functionality is organized into self-contained packages under the `packages/Webkul/` directory. Each package handles a specific domain (Admin, Shop, Checkout, Products, etc.) and can be independently developed and maintained.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Modular Package System
The application uses a package-based architecture built on Laravel's service provider pattern. Each package in `packages/Webkul/` is a self-contained module with its own:
- Service Provider for Laravel registration
- Routes, controllers, and views
- Database migrations and models
- Assets (CSS/JS) with dedicated Vite configurations

**Core packages include:**
- **Admin** - Backend admin panel with Vue.js components
- **Shop** - Customer-facing storefront with Vue.js components
- **Core** - Shared utilities, channels, locales, currencies
- **Product** - Product types (simple, configurable, virtual, downloadable)
- **Category** - Category management with nested sets
- **Checkout** - Shopping cart and checkout flow
- **Customer** - Customer accounts and authentication
- **Sales** - Orders, invoices, shipments, refunds
- **Inventory** - Stock management across sources
- **Payment/Paypal** - Payment method integrations
- **Shipping** - Shipping method configurations
- **Installer** - Web-based installation wizard

### Frontend Architecture
- **Vue.js 3** for reactive UI components in Admin and Shop packages
- **Tailwind CSS** for styling with custom configurations per package
- **Vite** for asset bundling with Laravel Vite Plugin
- **VeeValidate** for form validation
- Separate build configurations for Admin, Shop, and Installer themes

### Backend Architecture
- **Laravel 11** as the core framework
- **PHP 8.2+** requirement
- **Eloquent ORM** with repository pattern (prettus/l5-repository)
- **Laravel Sanctum** for API authentication
- **Laravel Octane** compatibility for high-performance deployments
- **Konekt Concord** for modular architecture support

### Database Design
- MySQL with `pdo_mysql` extension required
- **Nested Sets** (kalnoy/nestedset) for hierarchical category data
- **Translatable models** (astrotomic/laravel-translatable) for multi-language content
- Separate translation tables for localizable content

### Key Design Patterns
- Repository pattern for data access abstraction
- Service providers for dependency injection and package registration
- Blade components for reusable UI elements
- Event-driven architecture for extensibility
- Queue system for background job processing

## External Dependencies

### Payment Gateways
- **PayPal Checkout SDK** - PayPal payment processing

### Search & Caching
- **Elasticsearch** - Product search and filtering
- **Redis** (via Predis) - Session/cache storage, queues
- **Spatie Response Cache** - Full page caching

### File & Media Processing
- **Intervention Image** - Image manipulation and resizing
- **Bagisto Image Cache** - Cached image transformations
- **DomPDF/mPDF** - PDF generation for invoices

### Third-Party Integrations
- **Laravel Socialite** - OAuth social login (Google, Facebook, etc.)
- **Pusher** - Real-time notifications and broadcasting
- **OpenAI Laravel** - AI-powered features
- **Maatwebsite Excel** - Import/export functionality

### SEO & Analytics
- **Spatie Sitemap** - XML sitemap generation
- **Shetabit Visitor** - Visitor tracking and analytics

### Security & Sanitization
- **Stevebauman Purify** - HTML purification
- **Enshrined SVG Sanitize** - SVG file sanitization

### Internationalization
- **Khaled Alshamaa AR-PHP** - Arabic language text processing
- Multi-locale support with translatable models
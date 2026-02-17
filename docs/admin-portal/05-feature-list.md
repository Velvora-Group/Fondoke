# 4. Feature List

**Document:** Fondoke Admin Portal PRD - Feature List  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

---

## 4.1 Core Platform Features

### 4.1.1 User Management

**Priority: P0 (Must Have)**

- **User Registration**
  - Email/password authentication
  - Social login (Google, Facebook)
  - Multi-step registration process
  - Email verification

- **User Profiles**
  - Personal information (name, email, phone, address)
  - Profile photo upload
  - Payment methods management
  - Booking history
  - Trading history
  - Earnings/spending tracking

- **KYC (Know Your Customer)**
  - Identity verification
  - Address proof upload
  - Document verification
  - Admin approval process

- **User Roles**
  - Regular User: Basic booking access
  - Advanced User: Trading privileges
  - Corporate User: Bulk booking management
  - Admin: Full platform control

- **Account Management**
  - Profile editing
  - Password reset
  - Two-factor authentication
  - Account suspension/deletion
  - Activity history tracking

### 4.1.2 Hotel Search & Booking

**Priority: P0 (Must Have)**

- **AI-Powered Search**
  - Natural language search
  - Destination autocomplete
  - Date range selection
  - Guest count (adults, children)
  - Intelligent recommendations

- **Advanced Filtering**
  - Price range
  - Star rating
  - Amenities (WiFi, Pool, Gym, Parking, etc.)
  - Guest ratings
  - Distance from landmarks
  - Cancellation policy

- **Hotel Details Page**
  - Photo gallery
  - Room types and rates
  - Amenities list
  - Location map
  - Guest reviews
  - Cancellation policy
  - Check-in/check-out times

- **Booking Process**
  - Room selection
  - Guest information
  - Special requests
  - Voucher code application
  - Payment processing
  - Booking confirmation
  - Email notifications

- **Booking Management**
  - View booking details
  - Cancel booking (if allowed)
  - Modify booking (if allowed)
  - Download confirmation
  - Contact support

### 4.1.3 Trading Marketplace

**Priority: P0 (Must Have)**

- **Listing Creation**
  - Select booking to sell
  - Set sale price (with min/max constraints)
  - Add description
  - Set terms and conditions
  - Upload additional photos
  - Publish listing

- **Marketplace Browse**
  - Search by destination, dates, hotel
  - Filter by price, rating, check-in date
  - Sort by price, popularity, newest
  - View listing details
  - Seller reputation display

- **Purchase Process**
  - One-click purchase
  - Escrow payment system
  - Booking verification
  - Transfer process
  - Buyer protection

- **Trading Safety**
  - Verified bookings only
  - Escrow payment protection
  - Dispute resolution system
  - Fraud detection
  - Rating and review system

- **Trade Management**
  - Active listings dashboard
  - Sales history
  - Purchase history
  - Earnings tracking
  - Transaction disputes

### 4.1.4 Contract Management (B2B)

**Priority: P1 (High Priority)**

- **Contract Creation**
  - Hotel information
  - Contract period (start/end dates)
  - Room allocation
  - Pricing structure
  - Commission rates
  - Payment terms
  - Cancellation policy
  - Document upload

- **Inventory Management**
  - Room type management
  - Availability calendar
  - Real-time inventory updates
  - Blackout dates
  - Rate plans
  - Seasonal pricing

- **Contract Monitoring**
  - Contract status dashboard
  - Expiring contracts alerts
  - Performance metrics
  - Booking volume tracking
  - Revenue reporting

- **Contract Operations**
  - Renew contract
  - Terminate contract
  - Modify terms
  - Upload documents
  - Communication logs

### 4.1.5 Voucher System

**Priority: P1 (High Priority)**

- **Voucher Creation**
  - Unique voucher codes
  - Description and purpose
  - Discount type (percentage/fixed amount)
  - Discount value
  - Currency support
  - Validity period
  - Usage limits (total and per user)
  - Minimum booking amount
  - Applicability (all/specific hotels/specific users)
  - Status control

- **Voucher Management**
  - Search and filter vouchers
  - View voucher details
  - Edit voucher settings
  - Deactivate/delete vouchers
  - Export voucher data

- **Usage Tracking**
  - Usage history
  - User-level tracking
  - Booking association
  - Discount amount applied
  - Analytics and reporting

- **Voucher Application**
  - Code entry at checkout
  - Automatic validation
  - Real-time discount calculation
  - Error messaging
  - Usage recording

### 4.1.6 Payment Processing

**Priority: P0 (Must Have)**

- **Payment Methods**
  - Credit/debit cards
  - Digital wallets
  - Bank transfers
  - Saved payment methods

- **Transaction Management**
  - Secure payment gateway integration
  - PCI compliance
  - Multi-currency support (USD, EUR)
  - Real-time conversion rates
  - Transaction history

- **Escrow System**
  - Hold payments for trades
  - Automated release conditions
  - Dispute handling
  - Refund processing

- **Financial Reporting**
  - Transaction reports
  - Commission tracking
  - Settlement reports
  - Tax documentation

### 4.1.7 Admin Dashboard

**Priority: P0 (Must Have)**

- **Overview Tab**
  - Key metrics (users, bookings, trades, revenue)
  - Recent activities
  - Platform health indicators
  - Quick actions

- **User Management Tab**
  - User list with search/filter
  - User details page with tabs:
    - Information
    - Bookings
    - Trades
    - Activity History
  - Approval workflows
  - User actions (approve, suspend, ban)

- **Booking Management Tab**
  - Booking list with search/filter
  - Booking details page with tabs:
    - Information
    - Hotel Details
    - Activity History
  - Cancellation processing
  - Refund management

- **Trading Management Tab**
  - Trade listings
  - Trade details
  - Dispute resolution
  - Fraud monitoring

- **Contract Management Tab**
  - Contract list
  - Contract details with tabs:
    - Information
    - Inventory
    - Availability
    - Performance
  - Contract operations

- **Voucher Management Tab**
  - Voucher list
  - Voucher details with tabs:
    - Details
    - Usage History
    - Analytics
  - Voucher creation/editing

- **Analytics Tab**
  - Revenue analysis
  - User engagement metrics
  - Booking patterns
  - Trading volume
  - Platform performance
  - Support metrics
  - Business intelligence

## 4.2 Technical Features

### 4.2.1 Multi-Currency Support

- USD and EUR support
- Real-time currency conversion
- Price display based on user preference
- Transaction in user's selected currency

### 4.2.2 Internationalization

- Date format: dd/mm/yyyy
- Multi-language support (future)
- Regional settings

### 4.2.3 Notifications

- Email notifications
- In-app notifications
- SMS alerts (optional)
- Push notifications (mobile)

### 4.2.4 Security

- HTTPS/SSL encryption
- Data encryption at rest
- Role-based access control (RBAC)
- API authentication
- Audit logging
- Session management

### 4.2.5 API Integration

- Hotel booking APIs (Booking.com, Expedia, Agoda, Hotels.com)
- Payment gateway APIs
- Email service providers
- SMS providers
- Analytics platforms

---

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

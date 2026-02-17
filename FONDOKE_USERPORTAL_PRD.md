# Fondoke - Lean Product Requirement Document (PRD)

**Version:** 1.0  
**Date:** February 17, 2026  
**Owner:** Product Team  
**Status:** Active Development

---

## 1. Executive Summary

Fondoke is a revolutionary hotel booking and reselling platform that enables users to book hotels from multiple platforms, sell their unused reservations to other users, and trade hotel reservations in a dynamic marketplace. The platform combines traditional booking functionality with a fintech-style trading system, providing flexibility and cost savings for travelers while creating a secondary market for hotel reservations.

---

## 2. Business Goals

### Primary Goals
1. **Reduce Booking Waste**: Enable users to recover value from unused hotel reservations instead of losing money on cancellations
2. **Provide Cost Savings**: Offer discounted hotel reservations through the resale marketplace (targeting 15-40% savings)
3. **Increase Booking Flexibility**: Give travelers the option to sell or trade reservations when plans change
4. **Generate Revenue**: Create sustainable revenue streams through transaction fees, platform commissions, and premium features

### Success Metrics
- **User Acquisition**: 100K registered users in Year 1
- **Transaction Volume**: $50M GMV (Gross Merchandise Value) in Year 1
- **User Retention**: 40% monthly active users
- **Customer Satisfaction**: NPS score > 50
- **Trading Activity**: 30% of bookings listed on trading marketplace
- **Average Savings**: Users save 25% on average through resale marketplace

---

## 3. Target Users

### Primary Personas

#### 1. **Flexible Traveler (Sarah)**
- Age: 28-45
- Behavior: Books hotels in advance, plans change frequently
- Pain Point: Loses money on non-refundable cancellations
- Goal: Recover cost when plans change

#### 2. **Budget-Conscious Traveler (Mike)**
- Age: 22-35
- Behavior: Always looking for deals and discounts
- Pain Point: High hotel costs limit travel frequency
- Goal: Book quality hotels at discounted rates

#### 3. **Business Traveler (Jennifer)**
- Age: 35-50
- Behavior: Books multiple rooms, needs flexibility
- Pain Point: Bulk cancellations result in significant losses
- Goal: Manage corporate bookings efficiently with recovery options

#### 4. **Hotel Investor/Trader (David)**
- Age: 30-55
- Behavior: Monitors hotel price fluctuations
- Pain Point: No marketplace to trade hotel reservations
- Goal: Profit from hotel price arbitrage

---

## 4. User Flows

### 4.1 Core User Journeys

#### Journey 1: New User Booking Flow
```
Landing Page → Sign Up (Magic Link) → Account Creation
→ Browse Hotels (AI Search or Manual)
→ View Hotel Details → Select Room & Dates
→ User Profile Collection (First-time only)
→ Payment → Booking Confirmation
→ Email Notification
```

#### Journey 2: Selling a Reservation
```
Dashboard → My Bookings → Select Booking to Sell
→ Set Price (Platform suggests 5-40% discount)
→ Add Description/Notes
→ List on Trading Marketplace
→ Direct Purchase
→ Transfer Confirmation
→ Receive Earnings
```

#### Journey 3: Buying from Trading Marketplace
```
Trading Page → Browse Available Reservations
→ Filter by Location/Price/Dates
→ View Details & hotel Rating
→ Buy Now
→ Payment → Reservation Transfer
→ Booking Confirmation
→ Check-in at Hotel
```

#### Journey 4: Cancellation with Refund (on some bookings)
```
Dashboard → My Bookings → Select Booking
→ Request Cancellation
→ Choose: Full Cancel (25% refund) or List for Sale
→ Process Refund → Confirmation
```

#### Journey 5: Bulk Booking (Company Admin - Day2)
```
Company Admin Dashboard → Bulk Operations
→ Upload CSV or Manual Entry
→ Review & Confirm Multiple Bookings
→ Payment → Bulk Confirmation
→ Team Notifications
```

### 4.2 Secondary User Flows

#### Hotel Comparison Flow
```
Search Results → Add to Compare (up to 4 hotels)
→ Comparison Bar → View Side-by-Side
→ Compare: Price, Location, Amenities, Reviews
→ Select Hotel → Book
```

#### Favorites Flow
```
Any Hotel Card → Click Heart Icon
→ Added to Favorites Sidebar
→ View Favorites → Click Hotel
→ Auto-populate Dates (Check-in: +3 days, Check-out: +4 days)
→ Proceed to Book
```

#### Price Alert Flow - For Trading only
```
Hotel Details → Trading Tab
→ Set Price Alert (Below/Above/Change %)
→ Configure Notifications (Email)
→ Alert Frequency (Instant/Daily/Weekly)
→ Receive Alerts → Quick Action Button
```

#### Map-Based Search Flow
```
Search Page → Switch to Map View
→ Browse Hotels on Map
→ (Day2) Filter by POI Categories (8 types: Airports, Museums, Restaurants, etc.)
→ (Day2) Adjust Distance Radius
→ View Hotel Markers (Pulsing for Tradable)
→ Click Marker → View Details
```

---

## 5. Feature List

### 5.1 Authentication & User Management

#### Features
- **Magic Link Authentication**: Passwordless login via email
- **Instant Account Creation**: No manual verification required

- **User Roles**: User, Company Admin (Day2), Platform Admin (Fondoke)
- **User Profile Management**:
  - Full name, email, phone, date of birth
  - Address (street, city, state, postal code, country)
  - Passport information (optional - Manually for now when approving Vouchers to avoid missues) We have to find an automated way to do that
  - Collected before first booking

#### Technical Details
- AWS Cognito for authentication
- Session management with JWT tokens
- Email verification for magic links
- Profile completion check before booking

---

### 5.2 Hotel Search & Discovery

#### 5.2.1 AI-Powered Natural Language Search and multiple languages
**Description**: Users can search using natural language queries

**Examples**:
- "Luxury hotel near Times Square for 3 nights next weekend"
- "Budget-friendly hotel with pool in Miami"
- "Pet-friendly beachfront resort in California"

**Features**:
- Natural language processing
- Intent recognition
- Auto-extraction of dates, location, preferences
- Suggested alternative queries
- Search history tracking
- Search with combination of different languages
- supports typing mistakes

#### 5.2.2 Manual Search
**Features**:
- Location autocomplete
- Date picker with 2-month calendar view
- Multi-room selection:
  - Adults count per room (minimum 1)
  - Children count per room (0-17 years)
  - Age input for each child (required)
  - 5 max rooms
  - 4 max adults per room
  - 3 max children per room
- Display format: "X rooms, Y guests"

		
		
#### 5.2.3 Advanced Filtering
**Filter Categories**:
- **Price Range**: $50 - $1000+ (slider)
- **Star Rating**: All, 3★, 4★, 5★
- **Amenities**: WiFi, Pool, Gym, Restaurant, Spa, Parking, Pet-Friendly, Room Service
- **Check-in/Check-out Dates**: Calendar picker
- **POI Distance - Day2**: Adjustable radius (0.5 - 10 miles)
- **Hotel Type**: Booking vs Trading marketplace

**POI Categories - Day2** (50+ locations across major US cities):
1. Airports
2. Museums & Cultural Sites
3. Restaurants & Dining
4. Shopping Centers
5. Entertainment Venues
6. Parks & Recreation
7. Business Districts
8. Transportation Hubs

#### 5.2.4 Search Results Display
**View Options**:
- **List View**: Vertical card layout with images
- **Map View**: Interactive Google Maps with custom markers

**Hotel Card Information**:
- Hotel images (carousel with 5+ photos)
- Hotel name and star rating
- Location with distance from POI (Day2)
- Price per night (original and discounted)
- Discount percentage badge (if tradable)
- Review score and count
- Amenities 
- Tradable indicator (pulsing badge with gradient)
- Favorite heart icon
- Add to Compare button

**Sorting Options**:
- Price: Low to High
- Price: High to Low
- Rating: High to Low
- Popularity

---

### 5.3 Hotel Details Page

#### 5.3.1 Overview Section
- Hotel name with star rating
- Location with Google Maps integration (clickable)
- Price per night with breakdown
- Tradable badge (if applicable)
- Image gallery (5+ high-resolution photos with carousel)
- Quick actions: Favorite, Compare, Share

#### 5.3.2 Search Parameters (Above Hotel Name)
**Layout**: Horizontal card with blue gradient background
- Check-in date picker (2-month calendar)
- Check-out date picker (2-month calendar)
- Rooms & Guests selector:
  - Multiple rooms support
  - Adults count per room
  - Children count with age inputs (0-17 years)
  - Add/Remove room buttons
- "Search" button to update results

#### 5.3.3 Tabbed Content
**Overview Tab**:
- Hotel description
- Room types and availability
- Amenities list
- Hotel policies:
  - Check-in/Check-out times
  - Cancellation policy 
  - Children policy
  - Pet policy
  - Smoking policy
  - Payment methods
  - Additional fees and taxes

**Location Tab**:
- Interactive Google Maps
- Address details
- Nearby POIs with distances (Day2)
- Transportation options

**Reviews Tab**:
- Overall rating score
- Review breakdown by category (Cleanliness, Service, Location, etc.)
- User reviews with ratings
- Verified booking badges
- Helpful votes

**Trading Market Tab** (if tradable):
- Real-time price chart (7D, 30D, 90D, 1Y)
- Price statistics (High, Low, Average)
- Trading volume graph
- Available listings
- Price alert configuration
- Watchlist toggle
- Comparison with other hotels

#### 5.3.4 FAQ Section
- Collapsible accordions
- Common questions about booking, cancellation, policies
- Platform-specific FAQs about trading and reselling

#### 5.3.5 Actions
- "Book Now" button (primary CTA)
- Add to Favorites
- Add to Comparison (max 4 hotels)
- Set Price Alert (Only for Trading)
- Share hotel 

---

### 5.4 Booking & Payment

#### 5.4.1 User Information Collection
**Trigger**: First-time booking only
**Modal Form Fields**:
- Full name
- Email (pre-filled)
- Phone number
- Date of birth
- Address (street, city, state, postal code, country)

**Validation**:
- All fields required except passport
- Phone number format validation
- Email format validation
- Age verification (18+ required)

#### 5.4.2 Booking Flow
**Step 1: Guest Information**
- Pre-filled from user profile
- Edit option available
- Special requests textarea (Day2)

**Step 2: Payment Method Selection**
- Credit/Debit Card (Stripe)
- Apple Pay (mobile)
- Google Pay (mobile)

**Step 3: Payment Details**
- Card number
- Expiry date (MM/YY)
- CVV
- Cardholder name
- Billing address
- ZIP/Postal code

**Step 4: Review & Confirm**
- Booking summary
- Hotel details
- Dates and nights count
- Room type and guest count
- Price breakdown:
  - Room rate per night (itemized by date)
  - Weekend/weekday pricing differences
  - Total nights
  - Taxes and fees
  - Service charges
  - **Total amount**
- Cancellation policy reminder
- Terms & Conditions checkbox

#### 5.4.3 Price Breakdown Details
**Nightly Rate Breakdown**:
- Display each night separately (dd/mm/yyyy format)
- Different pricing for weekends vs weekdays (This is based on Prices from Travellanda - Below might not be accurate):
  - Saturday: +15% premium
  - Friday: +10% premium
  - Weekdays: -5% discount
- Dynamic total calculation

**Additional Charges**:
- City tax (percentage + fixed amount)
- Resort fees
- Service charges
- Cleaning fees

**Discounts Applied**:
- Trading marketplace discount (if applicable)
- Vouchers codes
- Loyalty rewards

#### 5.4.4 Booking Confirmation
**Confirmation Page Elements**:
- Success animation
- Booking confirmation number (unique ID)
- QR code for check-in (Day3)
- Hotel details recap
- Check-in/Check-out dates
- Guest information
- Total paid amount
- Cancellation policy
- Options available:
  - List for Sale (if tradable)

**Email Notification**:
- Subject: "Your Fondoke Booking Confirmation - [Hotel Name]"
- Booking details
- Cancellation policy
- Check-in instructions
- Hotel contact information
- Fondoke support contact
- Add to Calendar link (Day2)

---

### 5.5 Trading Marketplace

#### 5.5.1 Listing Creation
**Seller Flow**:
1. Navigate to "My Bookings"
2. Select booking to sell
3. Platform suggests discount range (5-40% off original)
4. Set listing price
5. Add description/notes (optional)
6. Publish listing

**Listing Information**:
- Original booking details
- Discount percentage
- Time remaining until check-in
- Seller rating and reviews

#### 5.5.2 Trading Page Features
**Visual Elements**:
- Dark mode fintech aesthetic
- Real-time ticker bar at bottom showing live price movements
- Scrolling ticker with:
  - Hotel name
  - Current price
  - Price change (% and $)
  - Up/down indicators with colors (green/red)

**Filtering & Sorting**:
- All standard search filters apply
- Additional filters (Day2):
  - Discount range (5-40%)
  - Time remaining (24hrs, 1 week, 1 month)

**Hotel Cards on Trading Page**:
- Prominent tradable badge (gradient with pulsing animation)
- Original price (strikethrough)
- Discounted price (highlighted)
- Discount percentage badge
- Time remaining countdown (Day2)

#### 5.5.3 Purchase Process
**Buyer Options**:
- **Buy Now**: Instant purchase at listed price

**Transaction Flow**:
1. Select "Buy Now"
2. Review booking details
3. Payment processing
4. Reservation transfer initiated
5. Both parties receive confirmation
6. Original platform notified of name change
7. New booking confirmation sent to buyer
8. Seller receives earnings (minus platform fee)

#### 5.5.4 Pricing Intelligence
**Dynamic Pricing Suggestions**:
- Algorithm considers:
  - Days until check-in
  - Hotel demand in area
  - Historical trading data
  - Seasonal trends
  - Competition from similar listings

**Pricing Tiers**:
- **Quick Sale** (30-40% off): High urgency, check-in < 7 days
- **Standard** (20-30% off): Moderate urgency, check-in 7-30 days
- **Premium** (5-15% off): Low urgency, check-in > 30 days

#### 5.5.5 Real-Time Price Charts
**Chart Features**:
- Time ranges: 7D, 30D, 90D, 1Y
- Candlestick or line chart options
- Price range indicators (High/Low/Average)
- Trading volume overlay
- Toggle price vs volume display
- Zoom and pan functionality
- Hover tooltips with exact values

**Price Statistics**:
- Current price
- 24hr change (% and $)
- 7-day high/low
- 30-day average
- Trading volume (# of transactions)
- Liquidity indicator

---

### 5.6 Watchlist & Price Alerts

#### 5.6.1 Watchlist Features
**Add to Watchlist**:
- Toggle switch on hotel details page
- Quick add from trading marketplace
- Accessible from watchlist sidebar

**Watchlist Display**:
- Dedicated sidebar (similar to favorites)
- Hotel thumbnail
- Current price
- Price change indicator
- Quick actions: View, Remove, Set Alert

**Watchlist Page**:
- Grid view of all watched hotels
- Price movement graphs
- Sort by: Recently Added, Price Change, Alert Status
- Bulk actions: Remove Selected, Set Alerts

#### 5.6.2 Price Alert Configuration
**Alert Types**:
1. **Price Drops Below**: Alert when price < specified amount
2. **Price Rises Above**: Alert when price > specified amount
3. **Price Change**: Alert when price changes by X%

**Alert Setup**:
- Choose alert type
- Set target price or percentage
- Select notification channels:
  - Email notifications (toggle)
  - Push notifications (toggle)
  - In-app notifications (toggle)
- Set alert frequency:
  - Instant
  - Daily digest
  - Weekly summary
- Alert duration:
  - 7 days
  - 30 days
  - 90 days
  - Indefinite

**Alert Management**:
- Active alerts dashboard
- Alert status: Active, Triggered, Expired
- Edit or delete alerts
- Alert history
- Performance tracking (how many savings achieved)

---

### 5.7 Hotel Comparison

#### 5.7.1 Comparison Bar
**Location**: Bottom of screen (sticky)
**Capacity**: Maximum 4 hotels
**Display**:
- Hotel thumbnails
- Hotel names
- Prices
- Remove button (X)
- "Compare" button
- "Clear All" button

#### 5.7.2 Comparison Page
**Side-by-Side Layout**:
- Hotel images at top
- Hotel names and star ratings

**Comparison Categories**:
1. **Price Comparison**:
   - Price per night
   - Total price for selected dates
   - Discount (if tradable)
   - Price per night difference
   - Best value indicator

2. **Location**:
   - Address
   - Distance from POIs
   - Neighborhood
   - Transportation access
   - Map view with all hotels

3. **Amenities**:
   - Checkmark/X for each amenity
   - Unique amenities highlighted
   - Amenity count

4. **Room Features**:
   - Room types available
   - Bed types
   - Room size
   - Max occupancy
   - View type

5. **Reviews & Ratings**:
   - Overall score
   - Category breakdowns
   - Review count
   - Recent review highlights

6. **Policies**:
   - Check-in/out times
   - Cancellation policy
   - Pet policy
   - Children policy

**Actions**:
- Book buttons for each hotel
- Add/Remove from favorites
- View full details
- Share comparison

---

### 5.8 Favorites System

#### 5.8.1 Favorites Sidebar
**Location**: Right side of screen (overlay)
**Trigger**: Heart icon in header (shows count badge)

**Display Features**:
- Vertical scrolling list
- Hotel cards showing:
  - Hotel image
  - Hotel name
  - Location
  - Star rating
  - Review score
  - Source badge (Booking/Trading)
  - Discount badge (if applicable)
- Actions per hotel:
  - "View Details" button
  - Remove from favorites (trash icon)

**Special Behavior**:
- Clicking hotel from favorites:
  - Navigates to hotel details page
  - **Auto-fills dates**: Check-in = Today +3 days, Check-out = Today +4 days
  - Pre-populates search fields
  - Closes favorites sidebar

#### 5.8.2 Favorites Management
- Add/Remove via heart icon (anywhere in app)
- Persistent across sessions
- Sync across devices (user account)
- Empty state message with CTA
- Footer tip: "Click on any hotel to view full details"

---

### 5.9 Map Integration

#### 5.9.1 Interactive Google Maps
**Features**:
- Full-screen map view toggle
- Custom hotel markers:
  - Standard hotels: Blue pin
  - Tradable hotels: Emerald lightning bolt with pulsing ring
- Marker clustering for dense areas
- Auto-zoom to fit all hotels with 2cm padding
- Click marker to view hotel details

#### 5.9.2 POI Filtering on Map
**8 POI Categories (Day2)**:
1. Airports
2. Museums & Cultural Sites
3. Restaurants & Dining
4. Shopping Centers
5. Entertainment Venues
6. Parks & Recreation
7. Business Districts
8. Transportation Hubs

**Filtering Features (Day2)**:
- Multi-select POI categories (Day2)
- Distance radius slider (0.5 - 10 miles) (Day2)
- Show/hide POI markers (Day2)
- POI marker colors by category (Day2)
- Distance indicator from hotel to selected POI (Day2)

#### 5.9.3 Search as You Move Map (Day2)
**Feature**: "Search this area" button appears when panning map
**Behavior**:
- Automatically trigger search when user stops panning
- Update results based on visible map bounds
- Maintain current filters
- Show loading indicator during search

---

### 5.10 Dashboard & User Management

#### 5.10.1 User Dashboard
**Overview Section**:
- Welcome message with user name
- Account status indicator
- Quick stats:
  - Total bookings
  - Active bookings
  - Completed bookings
  - Total spent
  - Total earned (from sales)

**My Bookings Section**:
- Filter tabs:
  - All Bookings
  - Upcoming
  - Past
  - Cancelled
  - Listed for Sale

**Booking Card Details**:
- Hotel thumbnail
- Hotel name and location
- Booking confirmation number
- Check-in/Check-out dates
- Number of nights
- Guest count
- Total paid
- Booking source (Original/Trading)
- Status badge (Confirmed/Pending/Cancelled/Completed)

**Actions per Booking**:
- View Details
- Cancel Booking
- List for Sale (If tradable)
- Download Invoice
- Email Confirmation
- Share (Whatsapp or Email)
- Contact Support

#### 5.10.2 My Listings (Seller Dashboard)
**Metrics**:
- Total listings
- Active listings
- Sold listings
- Total earnings
- Pending transfers
- Average sale time

**Listing Management**:
- Edit price
- Update description
- Pause/Unpause listing
- Delete listing
- View offers received

**Earnings Overview**:
- Total revenue
- Pending payouts
- Transaction history
- Withdrawal requests
- Platform fee breakdown

#### 5.10.3 My Purchases (Buyer Dashboard)
**Purchased Reservations**:
- Show bookings bought from trading marketplace
- Original seller information
- Discount received
- Transaction date
- Transfer status
- Hotel confirmation status

---

### 5.11 Company Admin Panel (Day2 - not applicable in First Release)

**Access**: Special credentials (admin/admin in demo)

#### 5.11.1 Bulk Booking Operations
**Upload Methods**:
- CSV file upload
- Manual entry form
- API integration

**CSV Format**:
- Hotel name or ID
- Check-in date (dd/mm/yyyy)
- Check-out date (dd/mm/yyyy)
- Number of rooms
- Adults per room
- Children per room (with ages)
- Employee name
- Employee email
- Special requests
- Cost center code

**Processing**:
- Validation of all rows
- Error highlighting
- Preview before confirmation
- Batch payment processing
- Individual confirmation emails
- Summary report

#### 5.11.2 Team Management
**Features**:
- Add/Remove team members
- Assign roles and permissions
- Set spending limits per user
- View team booking history
- Manage approval workflows
- Cost center allocation

#### 5.11.3 Reporting & Analytics
**Reports Available**:
- Booking summary by date range
- Cost analysis by department
- User activity reports
- Average booking value
- Cancellation rates
- Savings achieved through trading marketplace
- Export to CSV/PDF

#### 5.11.4 Policy Configuration
**Company Policies**:
- Approval requirements
- Spending limits
- Preferred vendors
- Booking windows
- Cancellation rules
- Payment methods allowed

---

### 5.12 Account Settings

#### 5.12.1 Profile Settings
**Editable Fields**:
- Full name
- Email (requires verification)
- Phone number
- Date of birth
- Address (full address fields)

#### 5.12.2 Preferences
**Notification Settings**:
- Email notifications (toggle)
- Marketing emails (toggle)
- Price alerts (toggle)

**Notification Types**:
- Booking confirmations (Mandatory can not be disabled)
- Listing activity (Mandatory can not be disabled)
- Price alerts
- Offer updates
- Payment receipts (Mandatory can not be disabled)
- Account updates 

**Display Settings**:
- Default currency (USD)
- Language (English - No other languages supported for now)
- Theme (Light/Dark/Auto)

#### 5.12.3 Payment Methods (This point is not accurate until we finish the Stripe Integration)
**Saved Payment Methods**:
- Add/Remove credit/debit cards
- Add/Remove PayPal account
- Set default payment method
- View transaction history
- Download receipts

#### 5.12.4 Security
**Features**:
- Two-factor authentication setup
- Login history

#### 5.12.5 Privacy
**Controls**:
- Email preferences
- Data download request (GDPR)
- Account deletion request

---

### 5.13 Cancellation & Refunds

#### 5.13.1 Cancellation Options
**Standard Cancellation**:
- Free cancellation period (varies by hotel/booking)
- Hotel-specific cancellation policies apply
- Platform cancellation fee: 0% (After agreement with Business team)

**Fondoke Advantage**:
- Alternative: List for sale instead of cancelling (applies only for tradable bookings)
- Comparison calculator showing best option

#### 5.13.2 Cancellation Flow
1. Navigate to booking details
2. Click "Cancel Booking"
3. Review cancellation policy
4. Choose:
   - Cancel 
   - List for sale (potentially recover more - applies only for tradable bookings)
   - Keep booking
5. Confirm cancellation
6. Process refund (5-7 business days)
7. Email confirmation

#### 5.13.3 Refund Processing
**Timeline**:
- Refund request initiated immediately
- Original payment method credited
- Processing time: 5-7 business days
- Email notification when complete

**Refund Amount Calculation**:
- Original booking amount
- Minus hotel cancellation fee (if applicable)
- Equals final refund amount

---

### 5.14 Customer Support

#### 5.14.1 Help Center
**Categories**:
- Getting Started
- Booking Hotels
- Selling Reservations
- Trading Marketplace
- Payment & Refunds
- Account Management
- Technical Issues
- Company Admin

**Content Types**:
- Step-by-step guides
- Video tutorials
- FAQs
- Troubleshooting tips
- Policy documents

#### 5.14.2 Contact Options
**Support Channels**:
- **Live Chat**: 24/7 support 
- **Email**: support@fondoke.com (24hr response)
- **Phone**: +1-800-FONDOKE (business hours)
- **Contact Form**: Structured form with category selection

**Contact Form Fields**:
- Name
- Email
- Subject
- Category dropdown
- Booking reference (optional)
- Description
- File attachments (screenshots, documents)
- Priority level

**Response Time SLAs**:
- Critical issues: 1 hour
- High priority: 4 hours
- Medium priority: 24 hours
- Low priority: 48 hours

---

### 5.15 Email Notifications

#### 5.15.1 Transactional Emails

**Booking Confirmation**:
- Booking ID and confirmation number
- Hotel details with image
- Check-in/check-out dates
- Guest information
- Price breakdown
- Cancellation policy
- Check-in instructions
- Add to calendar link
- View booking online button

**Booking Modification (Not Applicable - Maybe in future)**:
- Original vs new booking details
- What changed (dates, rooms, guests)
- Updated price
- New confirmation number

**Booking Cancellation**:
- Cancellation confirmation
- Refund amount and timeline
- Reason for cancellation
- Alternative suggestions

**Trading Marketplace Notifications**:
- Listing published
- Offer received
- Offer accepted/rejected
- Sale completed
- Earnings deposited

**Payment Receipts**:
- Transaction date and ID
- Itemized charges
- Payment method used
- Download PDF receipt

#### 5.15.2 Marketing Emails (Opt-in)
- Weekly deals and discounts
- Personalized recommendations
- Price drop alerts
- New features announcements
- Travel tips and guides

---

## 6. Business Rules

### 6.1 Booking Rules

#### 6.1.1 General Booking Rules
- **Minimum Age**: Users must be 18+ to create bookings
- **Advance Booking**: Maximum 365 days in advance
- **Same-day Booking**: Allowed until hotel check-in time
- **Multiple Rooms**: Maximum 5 rooms per booking
- **Guest Count**: Maximum 4 adults per room, 3 children per room
- **Children Age Range**: 0-17 years (18+ are adults)
- **Minimum Stay**: 1 night
- **Maximum Stay**: 90 consecutive nights

#### 6.1.2 Date Validation
- Check-out date must be after check-in date
- Dates must use dd/mm/yyyy format consistently
- Cannot book dates in the past
- Must respect hotel-specific blackout dates
- Weekend pricing applies to Friday/Saturday nights

#### 6.1.3 Payment Rules
- Full payment required at booking
- Accepted currencies: AED, USD, EUR, GBP, QAR, SAR, BHD, OMR, KWD
- Payment must clear before confirmation
- Authorization hold for 24 hours on credit cards

### 6.2 Trading Marketplace Rules

#### 6.2.1 Listing Eligibility
**Can Be Listed**:
- Confirmed bookings only
- At least 24 hours before check-in
- Not already partially used (multi-night stays)
- Original platform allows name changes (Day2)

**Cannot Be Listed**:
- Check-in within 24 hours
- Already checked in
- Already cancelled
- Disputed or flagged bookings
- Third-party bookings without transfer rights

#### 6.2.2 Pricing Rules (Not Applicable)
- **Minimum Discount**: 5% off original price
- **Maximum Discount**: 40% off original price
- **Price Changes**: Maximum 3 price changes per listing
- **Price Floor**: Cannot list below hotel's current direct price
- **Dynamic Pricing**: Platform can suggest optimal pricing
- **Last-Minute Surge**: Prices can increase if high demand

#### 6.2.3 Transaction Rules (Not Applicable until Fondoke Business Approves)
- **Platform Fee**: x USD of sale price (charged to seller)
- **Buyer Fee**: X USD service fee on purchase
- **Instant Purchase**: No negotiation, immediate transfer

### 6.3 Cancellation Rules

#### 6.3.1 Standard Cancellations
- **Free Cancellation**: Varies by booking and hotels cancellation policies(24-48 hours before check-in, or other rules may apply)
- **Non-Refundable Bookings**: No refund through Fondoke
- **Partial Stay**: No refund for unused nights after check-in
- **No-Show**: No refund, booking marked as completed
- **Force Majeure**: Full refund (natural disasters, pandemics, etc.) Question: Does Fondoke has Insurance? or customer should buy insurance through Fondoke or Insurance company

#### 6.3.2 Refund Processing
- **Refund Timeline**: 5-7 business days
- **Refund Method**: Original payment method only
- **Partial Refunds**: Prorated by night
- **Service Fees**: Non-refundable (except force majeure)
- **Currency Exchange**: Refund in original currency paid

### 6.4 User Account Rules

#### 6.4.1 Account Creation
- **Magic Link Expiry**: 15 minutes
- **Profile Completion**: Required before first booking
- **Duplicate Accounts**: Prohibited (detected by email/phone)
- **Account Types**: Individual - Company (Day2) (cannot change type)

#### 6.4.2 Account Status
**Status Levels**:
1. **Pending**: New account, Awaiting first login. Magic Ling sent
2. **Suspended**: Temporary restriction, can view only
4. **Active**: Can access platform and use all features

**Status Triggers**:
- **Suspension**: Payment issues, seller disputes, policy violations

#### 6.4.3 Account Security
- **Magic Link is sent once**: each 15 minute upon request
- **Suspicious Activity**: Automatic flagging and verification required

### 6.5 Review & Rating Rules (Not Applicable - maybe in Day3)

#### 6.5.1 Review Eligibility
- Must have completed stay
- Review window: 30 days after check-out
- One review per booking
- Cannot review own listings
- Must have verified booking

#### 6.5.2 Review Content Rules
- Minimum 50 characters
- Maximum 1000 characters
- No personal information (phone, email, address)
- No profanity or hate speech
- No promotional content
- Must be relevant to stay
- Cannot include external links

#### 6.5.3 Rating System
**Rating Categories** (1-5 stars):
- Overall rating
- Cleanliness
- Service
- Location
- Value for money
- Amenities

**Seller Ratings** (Trading Marketplace):
- Communication
- Accuracy of listing
- Transfer smoothness
- Overall experience

#### 6.5.4 Review Moderation
- Auto-moderation for flagged words
- Manual review for disputed content
- Users can report inappropriate reviews
- Platform can remove violating reviews
- Sellers can respond to reviews (one time)

### 6.6 Currency & Pricing Rules

#### 6.6.1 Supported Currencies
- **Primary**: USD ($)
- **Secondary**: AED, USD, EUR, GBP, QAR, SAR, BHD, OMR, KWD
- **Exchange Rates**: Updated daily at 12:00 AM UTC
- **Rate Source**: European Central Bank rates
- **Display**: Always show customers chosen currancy

#### 6.6.2 Price Display Rules
- All prices include applicable taxes (where required)
- Additional fees shown separately
- Final price highlighted clearly
- Original price shown with strikethrough if discounted
- Savings percentage displayed prominently
- "Price includes" tooltip available

#### 6.6.3 Dynamic Pricing (Not applicable - pricing is based only on Travellanda partner)
**Factors**:
- Time until check-in (urgency)
- Historical demand for hotel
- Seasonal trends
- Day of week
- Local events
- Competitor pricing

**Price Adjustments**:
- Weekend surcharge: +10-15%
- Peak season: +20-50%
- Last-minute: +/-30% depending on demand
- Long-term stay discount: -10% for 7+ nights

### 6.7 Data & Privacy Rules

#### 6.7.1 Data Collection
**Collected Data**:
- Personal information (name, email, phone, address)
- Payment information (encrypted)
- Booking history
- Search history
- Device information
- Location data (with permission)
- Usage analytics

**Data Usage**:
- Personalized recommendations
- Fraud prevention
- Service improvement
- Marketing (with opt-in)
- Legal compliance

#### 6.7.2 Data Protection
- **Encryption**: All sensitive data encrypted at rest and in transit
- **PCI Compliance**: Level 1 PCI DSS certified
- **GDPR Compliance**: Full compliance for EU users
- **Data Retention**: 7 years for financial records, 2 years for analytics
- **Right to Deletion**: Users can request account and data deletion
- **Data Export**: Users can download their data (GDPR requirement)

#### 6.7.3 Third-Party Sharing
**Shared With**:
- Hotels (booking information only)
- Payment processors (payment data only)
- Law enforcement (when legally required)

**Not Shared With**:
- Marketing companies (without explicit consent)
- Other users (except seller/buyer in transactions)
- Social media platforms

### 6.8 Dispute Resolution

#### 6.8.1 Dispute Categories
1. **Booking Disputes**: Wrong dates, rooms, pricing errors
2. **Trading Disputes**: Seller didn't transfer, buyer didn't pay
3. **Quality Disputes**: Hotel not as described
4. **Payment Disputes**: Unauthorized charges, refund issues
5. **Account Disputes**: Suspended/banned accounts

#### 6.8.2 Dispute Process
**Step 1**: User submits dispute with evidence
**Step 2**: System auto-mediates simple disputes
**Step 3**: Customer service reviews within 24 hours
**Step 4**: Investigation with both parties (3-5 days)
**Step 5**: Resolution and compensation (if applicable)
**Step 6**: Appeal option (within 7 days of decision)

#### 6.8.3 Dispute Outcomes
- **Full Refund**: Complete reversal of transaction
- **Partial Refund**: Prorated compensation
- **Credit**: Fondoke credit for future bookings
- **No Action**: Dispute not substantiated
- **Account Penalty**: Warning, suspension, or ban

### 6.9 Company Admin Rules (Not applicable - Maybe in Day3)

#### 6.9.1 Access Control
- **Authentication**: Separate admin credentials required
- **Permissions**: Role-based access control (RBAC)
- **Activity Logging**: All actions logged and auditable
- **IP Restrictions**: Admin access from approved IPs only
- **2FA Required**: Two-factor authentication mandatory

#### 6.9.2 Bulk Operations
- **Maximum Batch Size**: 500 bookings per upload
- **Validation Required**: All entries validated before processing
- **Failure Handling**: Partial success allowed, errors reported
- **Approval Workflow**: Bookings over $10K require supervisor approval
- **Budget Limits**: Cannot exceed allocated budget per department

#### 6.9.3 Team Management
- **User Limits**: Up to 1000 team members
- **Role Types**: Admin, Manager, User, Viewer
- **Spending Limits**: Set per user or role
- **Approval Chains**: Up to 3 levels of approval
- **Audit Trail**: Complete history of all team actions

---

## 7. Acceptance Criteria

### 7.1 Authentication & User Management

#### AC-AUTH-001: Magic Link Login
**GIVEN** a user enters a valid email address  
**WHEN** they click "Send Magic Link"  
**THEN**:
- ✅ An email is sent within 45 seconds
- ✅ Email contains clickable magic link
- ✅ Link expires after 15 minutes
- ✅ Clicking link logs user in automatically
- ✅ User is redirected to home page or intended destination
- ✅ Success message displayed
- ✅ Token is initiated with expiry date of 30 days.
- ✅ After 30 days, user has to request new Magic link

#### AC-AUTH-002: Account Creation
**GIVEN** a new user clicks "Sign Up"  
**WHEN** they provide valid email and accept terms  
**THEN**:
- ✅ Account created instantly
- ✅ Status set to "Pending" initially
- ✅ User can access platform and status changes to "Active"

#### AC-AUTH-003: Profile Completion Before Booking
**GIVEN** a user attempts first booking  
**WHEN** profile is incomplete  
**THEN**:
- ✅ Modal form appears blocking booking flow
- ✅ Form displays all required fields
- ✅ Validation errors shown inline
- ✅ Cannot proceed until all required fields filled
- ✅ Can save and continue later
- ✅ Once completed, proceeds to booking immediately

### 7.2 Search & Discovery

#### AC-SEARCH-001: AI Natural Language Search
**GIVEN** a user enters natural language query  
**WHEN** they click search  
**THEN**:
- ✅ Query parsed and interpreted correctly
- ✅ Location extracted and validated
- ✅ Dates extracted (if mentioned)
- ✅ Guest preferences identified
- ✅ Relevant results displayed within 5 seconds
- ✅ Alternative suggestions shown if no exact match
- ✅ Search saved to history (last 3 searches)

#### AC-SEARCH-002: Manual Search with Multiple Rooms
**GIVEN** a user manually enters search criteria  
**WHEN** they configure multiple rooms with children  
**THEN**:
- ✅ Can add up to 5 rooms
- ✅ Each room shows adults count (min 1, max 4)
- ✅ Each room shows children count (0-3)
- ✅ Age input appears for each child (0-17 range)
- ✅ Children Age inputs required before search
- ✅ Total guest count calculated correctly
- ✅ Display format: "X rooms, Y guests"

#### AC-SEARCH-003: Advanced Filtering
**GIVEN** results are displayed  
**WHEN** user applies filters  
**THEN**:
- ✅ Results update in real-time
- ✅ Filter count badge shows active filters
- ✅ Can clear individual filters
- ✅ Can clear all filters at once
- ✅ Filter state persists during session
- ✅ POI distance filter updates map view (Day2)
- ✅ No results state shown when applicable - We should ALWAYS return suggestions

#### AC-SEARCH-004: Map View
**GIVEN** user switches to map view  
**WHEN** results are displayed  
**THEN**:
- ✅ All hotels shown as custom markers
- ✅ Tradable hotels show pulsing emerald lightning bolt
- ✅ Map auto-zooms to fit all hotels with padding
- ✅ Clicking marker shows hotel preview
- ✅ Can switch between list and map view seamlessly
- ✅ Filters apply to map view
- ✅ "Search as I move map" button appears when panning

### 7.3 Hotel Details & Booking

#### AC-HOTEL-001: Hotel Details Display
**GIVEN** a user clicks on a hotel  
**WHEN** details page loads  
**THEN**:
- ✅ All hotel information displayed
- ✅ Image carousel functional (min 5 images)
- ✅ Search parameters shown above hotel name
- ✅ Can modify search dates without leaving page
- ✅ Tabs load without full page refresh
- ✅ Map is interactive and clickable
- ✅ FAQ accordion expands/collapses smoothly
- ✅ Price breakdown tooltip shows detailed costs

#### AC-HOTEL-002: Booking from Hotel Details
**GIVEN** user clicks "Book Now"  
**WHEN** proceeding to booking  
**THEN**:
- ✅ Profile check performed
- ✅ Modal shown if profile incomplete
- ✅ Booking page pre-filled with hotel and dates
- ✅ Guest count matches search parameters
- ✅ Price matches hotel details page
- ✅ Can modify details before payment

#### AC-HOTEL-003: Favorites Integration
**GIVEN** user clicks hotel from favorites  
**WHEN** hotel details page loads  
**THEN**:
- ✅ Check-in date auto-set to today +3 days
- ✅ Check-out date auto-set to today +4 days
- ✅ Dates displayed in search parameters
- ✅ Can modify dates normally
- ✅ Favorites sidebar closes automatically

### 7.4 Trading Marketplace

#### AC-TRADING-001: Listing Creation
**GIVEN** a user has a confirmed booking  
**WHEN** they list it for sale  
**THEN**:
- ✅ Can set custom price within allowed range
- ✅ Cannot set price below minimum or above maximum
- ✅ Listing published immediately after confirmation
- ✅ Appears in trading marketplace within 1 minute
- ✅ Email confirmation sent to seller
- ✅ Original booking status updated to "Listed"

#### AC-TRADING-002: Trading Page Display
**GIVEN** user navigates to trading page  
**WHEN** page loads  
**THEN**:
- ✅ Real-time ticker bar visible at bottom
- ✅ Ticker shows live price movements
- ✅ Price changes update every 5 seconds
- ✅ Tradable badges clearly visible on cards
- ✅ Discount percentages prominently displayed
- ✅ Can filter by discount range
- ✅ Can sort by price, discount, time remaining

#### AC-TRADING-003: Purchase from Marketplace
**GIVEN** a buyer clicks "Buy Now"  
**WHEN** completing purchase  
**THEN**:
- ✅ Payment processed immediately
- ✅ Reservation transfer initiated automatically
- ✅ Both seller and buyer receive confirmation emails
- ✅ Seller receives earnings minus platform fee
- ✅ Original platform notified of name change
- ✅ New booking confirmation sent to buyer
- ✅ Listing removed from marketplace

#### AC-TRADING-004: Price Charts
**GIVEN** user views trading tab on hotel details  
**WHEN** chart loads  
**THEN**:
- ✅ Real-time price data displayed
- ✅ Can switch between time ranges (7D, 30D, 90D, 1Y)
- ✅ Hover tooltip shows exact price and date
- ✅ Volume data overlaid if enabled
- ✅ Chart updates every 30 seconds
- ✅ High/Low/Average statistics visible
- ✅ Can toggle between price and volume

### 7.5 Watchlist & Alerts

#### AC-WATCH-001: Add to Watchlist
**GIVEN** user toggles watchlist on hotel  
**WHEN** action completes  
**THEN**:
- ✅ Hotel added to watchlist immediately
- ✅ Success notification displayed
- ✅ Watchlist icon changes state (filled)
- ✅ Hotel appears in watchlist sidebar
- ✅ Can remove from watchlist easily
- ✅ Watchlist persists across sessions

#### AC-WATCH-002: Price Alert Configuration
**GIVEN** user sets up price alert  
**WHEN** alert is saved  
**THEN**:
- ✅ Alert stored with all parameters
- ✅ Notification channels configured correctly
- ✅ Alert appears in active alerts list
- ✅ Can edit alert after creation
- ✅ Can delete alert
- ✅ Alert duration countdown shown

#### AC-WATCH-003: Alert Triggering
**GIVEN** price meets alert condition  
**WHEN** system checks prices (every 5 minutes)  
**THEN**:
- ✅ Alert triggered within 5 minutes
- ✅ Notifications sent via selected channels
- ✅ Email notification formatted correctly
- ✅ Push notification delivered (if enabled)
- ✅ In-app notification badge updated
- ✅ Alert marked as "Triggered" in dashboard
- ✅ Can quick-action from notification (view/book)

### 7.6 Comparison

#### AC-COMPARE-001: Add to Comparison
**GIVEN** user clicks "Add to Compare"  
**WHEN** hotel added  
**THEN**:
- ✅ Hotel added to comparison bar
- ✅ Comparison bar appears at bottom
- ✅ Hotel thumbnail and name displayed
- ✅ Cannot add more than 4 hotels
- ✅ Warning shown if attempting to add 5th
- ✅ Can remove hotels from bar
- ✅ "Compare" button enabled with 2+ hotels

#### AC-COMPARE-002: Comparison Page
**GIVEN** user clicks "Compare" with 2+ hotels  
**WHEN** comparison page loads  
**THEN**:
- ✅ All hotels displayed side-by-side
- ✅ All comparison categories shown
- ✅ Differences highlighted
- ✅ Best value indicator shown
- ✅ Can scroll horizontally if needed (mobile)
- ✅ Can remove hotels from comparison
- ✅ Can book directly from comparison
- ✅ Can share comparison via link

### 7.7 Payment & Checkout

#### AC-PAYMENT-001: Booking Flow
**GIVEN** user proceeds through booking  
**WHEN** reaching payment step  
**THEN**:
- ✅ All payment methods displayed
- ✅ Can select preferred method
- ✅ Payment form validates all fields
- ✅ Shows clear error messages for invalid input
- ✅ Price breakdown visible throughout
- ✅ Can review all details before final payment
- ✅ Terms & conditions must be accepted
- ✅ User should be able to use vouchers if applicable

#### AC-PAYMENT-002: Payment Processing
**GIVEN** user submits payment  
**WHEN** processing  
**THEN**:
- ✅ Loading indicator shown
- ✅ Cannot double-submit
- ✅ Payment processed within 10 seconds
- ✅ Success confirmation displayed
- ✅ Redirect to confirmation page
- ✅ Confirmation email sent immediately
- ✅ Booking appears in dashboard

#### AC-PAYMENT-003: Price Breakdown
**GIVEN** user views price breakdown  
**WHEN** tooltip/modal opens  
**THEN**:
- ✅ Each night itemized separately
- ✅ Weekend vs weekday pricing shown
- ✅ All taxes and fees listed
- ✅ Service charges shown
- ✅ Discounts applied and highlighted
- ✅ Total calculated correctly
- ✅ Currency displayed consistently

### 7.8 Dashboard & User Management

#### AC-DASH-001: Dashboard Overview
**GIVEN** user navigates to dashboard  
**WHEN** page loads  
**THEN**:
- ✅ All statistics calculated correctly
- ✅ Bookings displayed in correct categories
- ✅ Can filter bookings by status
- ✅ Can search bookings
- ✅ Actions available for each booking
- ✅ Earnings and savings highlighted
- ✅ Quick links to key actions

#### AC-DASH-002: Booking Management
**GIVEN** user clicks booking action  
**WHEN** action executes  
**THEN**:
- ✅ List for sale redirects to listing creation (if tradable)
- ✅ Download invoice generates PDF
- ✅ Email confirmation resends successfully
- ✅ Contact support opens support form with booking details pre-filled

### 7.9 Cancellation & Refunds

#### AC-CANCEL-001: Cancellation Process
**GIVEN** user requests cancellation  
**WHEN** completing cancellation  
**THEN**:
- ✅ Shows refund amount clearly (if refundable)
- ✅ Shows alternative option (list for sale if tradable)
- ✅ Calculator compares both options
- ✅ Requires confirmation before processing
- ✅ Processes immediately after confirmation
- ✅ Email confirmation sent
- ✅ Refund initiated within 24 hours (in case of refund)

#### AC-CANCEL-002: Refund Processing
**GIVEN** cancellation processed  
**WHEN** refund initiated  
**THEN**:
- ✅ Refund shows in dashboard as "Processing"
- ✅ Estimated completion date displayed
- ✅ Refund completed within 5-7 business days
- ✅ User notified when refund complete
- ✅ Refund appears in original payment method
- ✅ Transaction history updated

### 7.10 Company Admin (Not applicable - Maybe Day3)

#### AC-ADMIN-001: Bulk Upload
**GIVEN** admin uploads CSV file  
**WHEN** file processed  
**THEN**:
- ✅ All rows validated
- ✅ Errors highlighted with specific messages
- ✅ Can fix errors inline
- ✅ Preview shown before confirmation
- ✅ Can proceed with valid rows only
- ✅ Batch payment processed
- ✅ Individual confirmations sent to employees
- ✅ Summary report generated

#### AC-ADMIN-002: Team Management
**GIVEN** admin manages team  
**WHEN** adding/removing users  
**THEN**:
- ✅ Can add users with email
- ✅ Invitation email sent automatically
- ✅ Can set role and permissions
- ✅ Can set spending limits
- ✅ Can view user activity
- ✅ Can revoke access immediately
- ✅ Changes take effect within 1 minute

### 7.11 Email Notifications

#### AC-EMAIL-001: Booking Confirmation Email
**GIVEN** booking completed  
**WHEN** confirmation email sent  
**THEN**:
- ✅ Sent within 1 minute of booking
- ✅ Contains all booking details
- ✅ Shows price breakdown
- ✅ Contains cancellation policy
- ✅ Hotel contact information included
- ✅ Fondoke support contact visible

#### AC-EMAIL-002: Price Alert Email
**GIVEN** price alert triggered  
**WHEN** notification email sent  
**THEN**:
- ✅ Subject line clearly states price drop/rise
- ✅ Shows old vs new price
- ✅ Includes percentage change
- ✅ Direct link to hotel details
- ✅ "Book Now" button included
- ✅ Unsubscribe option available
- ✅ Mobile-responsive design

### 7.12 Performance & Reliability

#### AC-PERF-001: Page Load Times
**GIVEN** user navigates to any page  
**WHEN** page loads  
**THEN**:
- ✅ Initial load < 2 seconds
- ✅ Search results < 3 seconds
- ✅ Map view loads < 4 seconds
- ✅ Hotel details < 2 seconds
- ✅ Images lazy-load progressively
- ✅ Smooth transitions between pages

#### AC-PERF-002: Real-time Updates
**GIVEN** user viewing trading page  
**WHEN** prices change  
**THEN**:
- ✅ Ticker updates every 5 seconds
- ✅ Price charts update every 30 seconds
- ✅ No page refresh required
- ✅ Updates don't interrupt user interaction
- ✅ WebSocket connection maintained
- ✅ Fallback to polling if WebSocket fails

#### AC-PERF-003: Mobile Responsiveness
**GIVEN** user on mobile device  
**WHEN** accessing any page  
**THEN**:
- ✅ Layout adapts to screen size
- ✅ Touch targets at least 44x44px
- ✅ Text readable without zooming
- ✅ Images optimized for mobile
- ✅ Forms usable on mobile keyboard
- ✅ Maps work with touch gestures
- ✅ Performance maintained on mobile networks

### 7.13 Security & Privacy

#### AC-SEC-001: Data Encryption
**GIVEN** any data transmission  
**WHEN** data sent to/from server  
**THEN**:
- ✅ All connections use HTTPS/TLS 1.3
- ✅ Payment data encrypted end-to-end
- ✅ PCI DSS Level 1 compliant
- ✅ Personal data encrypted at rest
- ✅ Encryption keys rotated regularly
- ✅ No sensitive data in logs

#### AC-SEC-002: Authentication Security
**GIVEN** user authentication attempt  
**WHEN** authenticating  
**THEN**:
- ✅ Magic links expire after 15 minutes
- ✅ Session timeout after 30 minutes inactivity (Refresh required)
- ✅ IP logging for audit trail

#### AC-SEC-003: Privacy Compliance
**GIVEN** user requests data  
**WHEN** GDPR request made  
**THEN**:
- ✅ Data export available within 48 hours
- ✅ All personal data included in export
- ✅ Data in machine-readable format (JSON)
- ✅ Account deletion processed directly
- ✅ Data deletion confirmed via email
- ✅ Right to be forgotten respected
- ✅ Third-party processors notified

---

## 8. Technical Architecture Overview

### 8.1 Backend Stack (This to be reviewed by Roman)
**Platform**: AWS Serverless Architecture
- **Database**: Amazon DynamoDB (NoSQL)
- **Compute**: AWS Lambda (Python)
- **API**: Amazon API Gateway (REST + WebSocket)
- **Authentication**: AWS Cognito
- **Storage**: Amazon S3 (images, documents)
- **Email**: Amazon SES
- **Notifications**: Amazon SNS
- **Search**: Amazon CloudSearch / Elasticsearch
- **Cache**: Amazon ElastiCache (Redis)

### 8.2 Frontend Stack (This to be reviewed by Nedim)
- **Framework**: React 18+ with TypeScript
- **UI Library**: Material-UI (MUI)
- **State Management**: React Context API + Hooks
- **Routing**: React Router v6 (Data mode)
- **Styling**: Tailwind CSS v4
- **Maps**: Google Maps JavaScript API
- **Charts**: Recharts
- **Icons**: Lucide React
- **Animations**: Motion (Framer Motion)
- **Forms**: React Hook Form
- **Date Handling**: date-fns
- **HTTP Client**: Fetch API with custom hooks

### 8.3 Third-Party Integrations (This to be reviewed by Roman)
- **Payment Processing**: Stripe
- **Email Delivery**: SendGrid (transactional)
- **SMS Notifications**: Twilio (Day2)
- **Analytics**: Google Analytics 4, Mixpanel
- **Error Tracking**: Sentry
- **Monitoring**: AWS CloudWatch, DataDog
- **CDN**: CloudFront
- **Hotel Data APIs**: Travellanda

---

## 9. Success Criteria

### 9.1 Launch Readiness
**Must Have** (MVP):
- ✅ User authentication (magic link)
- ✅ Hotel search (AI + manual)
- ✅ Hotel booking flow
- ✅ Payment processing
- ✅ Trading marketplace
- ✅ Basic dashboard
- ✅ Email notifications
- ✅ Responsive design

**Nice to Have** (Post-MVP):
- Price alerts
- Advanced analytics
- Mobile apps (iOS/Android) (Day2)
- Multiple languages (Day2)
- Social sharing
- Referral program
- Loyalty program (Day2)

### 9.2 Quality Metrics
- **Uptime**: 99.9% availability
- **Performance**: < 2s page load, < 3s search results
- **Error Rate**: < 0.1% of requests
- **Conversion Rate**: > 5% of searches to bookings
- **User Satisfaction**: NPS > 50
- **Security**: Zero critical security issues
- **Accessibility**: WCAG 2.1 AA compliant

### 9.3 Business Metrics (Year 1)
- **User Acquisition**: 100,000 registered users
- **Active Users**: 40,000 monthly active users
- **Bookings**: 50,000 total bookings
- **Trading Volume**: 15,000 traded reservations
- **GMV**: $50 million
- **Revenue**: $5 million (10% of GMV)
- **Customer Retention**: 60% return within 6 months
- **Average Booking Value**: $500
- **Customer Acquisition Cost**: < $50
- **Lifetime Value**: > $500

---

## 10. Risk Assessment

### 10.1 Technical Risks
| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| Hotel API downtime | High | Medium | Implement caching, fallback to manual entry |
| Payment processor issues | Critical | Low | Multi-processor setup, queue failed payments |
| Scalability bottlenecks | High | Medium | Auto-scaling, load testing, CDN |
| Security breach | Critical | Low | Penetration testing, bug bounty, insurance |
| Data loss | Critical | Very Low | Daily backups, multi-region replication |

### 10.2 Business Risks
| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| Hotel platforms blocking resales | Critical | Medium | Legal compliance, platform partnerships |
| Low user adoption | High | Medium | Marketing campaigns, referral incentives |
| Fraudulent transactions | High | Medium | Verification system, escrow, insurance |
| Regulatory changes | High | Low | Legal counsel, compliance monitoring |
| Competition from OTAs | Medium | High | Unique value proposition, better pricing |

### 10.3 Legal Risks
| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| Terms violation with booking platforms | Critical | Medium | Clear terms, platform partnerships |
| Consumer protection laws | High | Low | Compliance team, clear policies |
| Tax compliance issues | High | Low | Tax automation, accounting firm |
| Data privacy violations (GDPR) | Critical | Low | Privacy by design, regular audits |
| Liability for cancelled bookings | Medium | Medium | Clear disclaimers, insurance |

---

## 11. Future Roadmap

### Phase 1: MVP Launch (Months 1-3)
- Core booking functionality
- Basic trading marketplace
- Essential user features
- Payment processing
- Email notifications

### Phase 2: Enhancement (Months 4-6)
- Mobile apps (iOS/Android)
- Advanced search filters
- Price alerts and watchlist
- Enhanced analytics dashboard

### Phase 3: Growth (Months 7-12)
- International expansion
- Multiple currencies beyond USD/EUR
- Loyalty program
- Bulk booking for companies
- Referral program
- API for third-party integrations
- White-label solutions for travel agencies

### Phase 4: Innovation (Year 2+)
- AI-powered price prediction
- Blockchain-based booking verification
- Smart contracts for automated transfers
- Virtual reality hotel previews
- Group booking coordination
- Dynamic packaging (flights + hotels)
- Car rental integration
- Experience marketplace (tours, activities)

---

## 12. Glossary

**Terms & Definitions**:

- **Travellanda**: Third-party online B2B travel agencies where original reservations are made
- **Tradable Hotel**: A hotel reservation that is available for resale on Fondoke's trading marketplace
- **GMV (Gross Merchandise Value)**: Total value of all transactions on the platform
- **Magic Link**: Passwordless authentication method using email links
- **POI (Point of Interest)**: Notable locations like airports, museums, restaurants
- **Non-refundable Booking**: Hotel reservation that normally doesn't allow cancellation with refund
- **Nightly Rate Breakdown**: Itemized pricing showing cost per night with date-specific variations
- **Company Admin**: Business user with privileges to manage team bookings and operations
- **Watchlist**: User's list of hotels being monitored for price changes
- **Price Alert**: Automated notification when hotel price meets specified condition
- **Trading Marketplace**: Secondary market where users buy/sell existing hotel reservations
- **Bulk Booking**: Ability to create multiple reservations simultaneously (typically for businesses)
- **Child Age Collection**: Required input of exact ages for children (0-17 years) in booking
- **Favorites**: User's saved list of preferred hotels for quick access
- **Comparison**: Feature allowing side-by-side evaluation of up to 4 hotels
- **Real-time Ticker**: Live-updating price movement display at bottom of trading page
- **Map View**: Geographic display of hotels with interactive markers on Google Maps
- **List View**: Traditional vertical card layout of hotel search results

---

## 13. Appendix

### A. Wire frame References
*(Would normally include actual wireframes/mockups here)*
- Landing page
- Search results (list & map views)
- Hotel details page
- Booking flow
- Trading marketplace
- Dashboard
- Fondoke admin panel

### B. API Endpoints Overview
*(High-level list - detailed in separate API documentation)*
- User login through Magic Link
- Hotel Search
- Booking Operations
- Trading Marketplace
- Payment Processing
- Notifications
- Analytics

### C. Database Schema Overview
*(High-level entities - detailed in separate database documentation)*
- Users
- Bookings
- Listings
- Transactions
- Hotels
- Reviews
- Alerts
- Notifications

### D. Compliance & Certifications Required
- PCI DSS Level 1
- GDPR Compliance
- SOC 2 Type II
- ISO 27001
- CCPA Compliance
- Travel Industry Designator Service (TIDS) certification

### E. Contact Information
- **Product Owner**: jn@ennero.com
- **Technical Lead**: anm@velvoragroup.com
- **Frontend Lead**: nb@velvoragroup.com
- **Backend Lead**: rv@velvoragroup.com
- **Business Stakeholder**: Amir.Gharizadeh@travellanda.com, ahmad.alkatib@travellanda.com, Ali Taheri <ataheri1@gmail.com>
- **Support**: support@fondoke.com
- **Website**: www.fondoke.com

---

**Document Version History**:
- v1.0 - Initial Release - February 17, 2026
- *(Future versions to be added here)*

**Approval Signatures**:
- Product Owner: _________________ Date: _______
- Engineering Lead: _________________ Date: _______
- Business Owner: _________________ Date: _______

---

**END OF DOCUMENT**

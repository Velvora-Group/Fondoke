# 5. Feature List

**Document:** Fondoke PRD - Feature List  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_USERPORTAL_PRD.md)

---

## 5.1 Authentication & User Management

### Features

- **Magic Link Authentication**: Passwordless login via email
- **Instant Account Creation**: No manual verification required

- **User Roles**: User, Company Admin (Day2), Platform Admin (Fondoke)
- **User Profile Management**:
  - Full name, email, phone, date of birth
  - Address (street, city, state, postal code, country)
  - Passport information (optional - Manually for now when approving Vouchers to avoid missues) We have to find an automated way to do that
  - Collected before first booking

### Technical Details

- AWS Cognito for authentication
- Session management with JWT tokens
- Email verification for magic links
- Profile completion check before booking

---

## 5.2 Hotel Search & Discovery

### 5.2.1 AI-Powered Natural Language Search and multiple languages

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

### 5.2.2 Manual Search

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

### 5.2.3 Advanced Filtering

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

### 5.2.4 Search Results Display

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

## 5.3 Hotel Details Page

### 5.3.1 Overview Section

- Hotel name with star rating
- Location with Google Maps integration (clickable)
- Price per night with breakdown
- Tradable badge (if applicable)
- Image gallery (5+ high-resolution photos with carousel)
- Quick actions: Favorite, Compare, Share

### 5.3.2 Search Parameters (Above Hotel Name)

**Layout**: Horizontal card with blue gradient background

- Check-in date picker (2-month calendar)
- Check-out date picker (2-month calendar)
- Rooms & Guests selector:
  - Multiple rooms support
  - Adults count per room
  - Children count with age inputs (0-17 years)
  - Add/Remove room buttons
- "Search" button to update results

### 5.3.3 Tabbed Content

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

### 5.3.4 FAQ Section

- Collapsible accordions
- Common questions about booking, cancellation, policies
- Platform-specific FAQs about trading and reselling

### 5.3.5 Actions

- "Book Now" button (primary CTA)
- Add to Favorites
- Add to Comparison (max 4 hotels)
- Set Price Alert (Only for Trading)
- Share hotel

---

## 5.4 Booking & Payment

### 5.4.1 User Information Collection

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

### 5.4.2 Booking Flow

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

### 5.4.3 Price Breakdown Details

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

### 5.4.4 Booking Confirmation

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

## 5.5 Trading Marketplace

### 5.5.1 Listing Creation

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

### 5.5.2 Trading Page Features

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

### 5.5.3 Purchase Process

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

### 5.5.4 Pricing Intelligence

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

### 5.5.5 Real-Time Price Charts

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

## 5.6 Watchlist & Price Alerts

### 5.6.1 Watchlist Features

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

### 5.6.2 Price Alert Configuration

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

## 5.7 Hotel Comparison

### 5.7.1 Comparison Bar

**Location**: Bottom of screen (sticky)
**Capacity**: Maximum 4 hotels
**Display**:

- Hotel thumbnails
- Hotel names
- Prices
- Remove button (X)
- "Compare" button
- "Clear All" button

### 5.7.2 Comparison Page

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

## 5.8 Favorites System

### 5.8.1 Favorites Sidebar

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

### 5.8.2 Favorites Management

- Add/Remove via heart icon (anywhere in app)
- Persistent across sessions
- Sync across devices (user account)
- Empty state message with CTA
- Footer tip: "Click on any hotel to view full details"

---

## 5.9 Map Integration

### 5.9.1 Interactive Google Maps

**Features**:

- Full-screen map view toggle
- Custom hotel markers:
  - Standard hotels: Blue pin
  - Tradable hotels: Emerald lightning bolt with pulsing ring
- Marker clustering for dense areas
- Auto-zoom to fit all hotels with 2cm padding
- Click marker to view hotel details

### 5.9.2 POI Filtering on Map

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

### 5.9.3 Search as You Move Map (Day2)

**Feature**: "Search this area" button appears when panning map
**Behavior**:

- Automatically trigger search when user stops panning
- Update results based on visible map bounds
- Maintain current filters
- Show loading indicator during search

---

## 5.10 Dashboard & User Management

### 5.10.1 User Dashboard

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

### 5.10.2 My Listings (Seller Dashboard)

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

### 5.10.3 My Purchases (Buyer Dashboard)

**Purchased Reservations**:

- Show bookings bought from trading marketplace
- Original seller information
- Discount received
- Transaction date
- Transfer status
- Hotel confirmation status

---

## 5.11 Company Admin Panel (Day2 - not applicable in First Release)

**Access**: Special credentials (admin/admin in demo)

### 5.11.1 Bulk Booking Operations

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

### 5.11.2 Team Management

**Features**:

- Add/Remove team members
- Assign roles and permissions
- Set spending limits per user
- View team booking history
- Manage approval workflows
- Cost center allocation

### 5.11.3 Reporting & Analytics

**Reports Available**:

- Booking summary by date range
- Cost analysis by department
- User activity reports
- Average booking value
- Cancellation rates
- Savings achieved through trading marketplace
- Export to CSV/PDF

### 5.11.4 Policy Configuration

**Company Policies**:

- Approval requirements
- Spending limits
- Preferred vendors
- Booking windows
- Cancellation rules
- Payment methods allowed

---

## 5.12 Account Settings

### 5.12.1 Profile Settings

**Editable Fields**:

- Full name
- Email (requires verification)
- Phone number
- Date of birth
- Address (full address fields)

### 5.12.2 Preferences

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

### 5.12.3 Payment Methods (This point is not accurate until we finish the Stripe Integration)

**Saved Payment Methods**:

- Add/Remove credit/debit cards
- Add/Remove PayPal account
- Set default payment method
- View transaction history
- Download receipts

### 5.12.4 Security

**Features**:

- Two-factor authentication setup
- Login history

### 5.12.5 Privacy

**Controls**:

- Email preferences
- Data download request (GDPR)
- Account deletion request

---

## 5.13 Cancellation & Refunds

### 5.13.1 Cancellation Options

**Standard Cancellation**:

- Free cancellation period (varies by hotel/booking)
- Hotel-specific cancellation policies apply
- Platform cancellation fee: 0% (After agreement with Business team)

**Fondoke Advantage**:

- Alternative: List for sale instead of cancelling (applies only for tradable bookings)
- Comparison calculator showing best option

### 5.13.2 Cancellation Flow

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

### 5.13.3 Refund Processing

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

## 5.14 Customer Support

### 5.14.1 Help Center

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

### 5.14.2 Contact Options

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

## 5.15 Email Notifications

### 5.15.1 Transactional Emails

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

### 5.15.2 Marketing Emails (Opt-in)

- Weekly deals and discounts
- Personalized recommendations
- Price drop alerts
- New features announcements
- Travel tips and guides

---

[← Back to Main Document](../../FONDOKE_USERPORTAL_PRD.md)

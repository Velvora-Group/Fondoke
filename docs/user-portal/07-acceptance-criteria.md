# 7. Acceptance Criteria

**Document:** Fondoke PRD - Acceptance Criteria  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_USERPORTAL_PRD.md)

---

## 7.1 Authentication & User Management

### AC-AUTH-001: Magic Link Login

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

### AC-AUTH-002: Account Creation

**GIVEN** a new user clicks "Sign Up"  
**WHEN** they provide valid email and accept terms  
**THEN**:

- ✅ Account created instantly
- ✅ Status set to "Pending" initially
- ✅ User can access platform and status changes to "Active"

### AC-AUTH-003: Profile Completion Before Booking

**GIVEN** a user attempts first booking  
**WHEN** profile is incomplete  
**THEN**:

- ✅ Modal form appears blocking booking flow
- ✅ Form displays all required fields
- ✅ Validation errors shown inline
- ✅ Cannot proceed until all required fields filled
- ✅ Can save and continue later
- ✅ Once completed, proceeds to booking immediately

## 7.2 Search & Discovery

### AC-SEARCH-001: AI Natural Language Search

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

### AC-SEARCH-002: Manual Search with Multiple Rooms

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

### AC-SEARCH-003: Advanced Filtering

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

### AC-SEARCH-004: Map View

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

## 7.3 Hotel Details & Booking

### AC-HOTEL-001: Hotel Details Display

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

### AC-HOTEL-002: Booking from Hotel Details

**GIVEN** user clicks "Book Now"  
**WHEN** proceeding to booking  
**THEN**:

- ✅ Profile check performed
- ✅ Modal shown if profile incomplete
- ✅ Booking page pre-filled with hotel and dates
- ✅ Guest count matches search parameters
- ✅ Price matches hotel details page
- ✅ Can modify details before payment

### AC-HOTEL-003: Favorites Integration

**GIVEN** user clicks hotel from favorites  
**WHEN** hotel details page loads  
**THEN**:

- ✅ Check-in date auto-set to today +3 days
- ✅ Check-out date auto-set to today +4 days
- ✅ Dates displayed in search parameters
- ✅ Can modify dates normally
- ✅ Favorites sidebar closes automatically

## 7.4 Trading Marketplace

### AC-TRADING-001: Listing Creation

**GIVEN** a user has a confirmed booking  
**WHEN** they list it for sale  
**THEN**:

- ✅ Can set custom price within allowed range
- ✅ Cannot set price below minimum or above maximum
- ✅ Listing published immediately after confirmation
- ✅ Appears in trading marketplace within 1 minute
- ✅ Email confirmation sent to seller
- ✅ Original booking status updated to "Listed"

### AC-TRADING-002: Trading Page Display

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

### AC-TRADING-003: Purchase from Marketplace

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

### AC-TRADING-004: Price Charts

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

## 7.5 Watchlist & Alerts

### AC-WATCH-001: Add to Watchlist

**GIVEN** user toggles watchlist on hotel  
**WHEN** action completes  
**THEN**:

- ✅ Hotel added to watchlist immediately
- ✅ Success notification displayed
- ✅ Watchlist icon changes state (filled)
- ✅ Hotel appears in watchlist sidebar
- ✅ Can remove from watchlist easily
- ✅ Watchlist persists across sessions

### AC-WATCH-002: Price Alert Configuration

**GIVEN** user sets up price alert  
**WHEN** alert is saved  
**THEN**:

- ✅ Alert stored with all parameters
- ✅ Notification channels configured correctly
- ✅ Alert appears in active alerts list
- ✅ Can edit alert after creation
- ✅ Can delete alert
- ✅ Alert duration countdown shown

### AC-WATCH-003: Alert Triggering

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

## 7.6 Comparison

### AC-COMPARE-001: Add to Comparison

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

### AC-COMPARE-002: Comparison Page

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

## 7.7 Payment & Checkout

### AC-PAYMENT-001: Booking Flow

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

### AC-PAYMENT-002: Payment Processing

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

### AC-PAYMENT-003: Price Breakdown

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

## 7.8 Dashboard & User Management

### AC-DASH-001: Dashboard Overview

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

### AC-DASH-002: Booking Management

**GIVEN** user clicks booking action  
**WHEN** action executes  
**THEN**:

- ✅ List for sale redirects to listing creation (if tradable)
- ✅ Download invoice generates PDF
- ✅ Email confirmation resends successfully
- ✅ Contact support opens support form with booking details pre-filled

## 7.9 Cancellation & Refunds

### AC-CANCEL-001: Cancellation Process

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

### AC-CANCEL-002: Refund Processing

**GIVEN** cancellation processed  
**WHEN** refund initiated  
**THEN**:

- ✅ Refund shows in dashboard as "Processing"
- ✅ Estimated completion date displayed
- ✅ Refund completed within 5-7 business days
- ✅ User notified when refund complete
- ✅ Refund appears in original payment method
- ✅ Transaction history updated

## 7.10 Company Admin (Not applicable - Maybe Day3)

### AC-ADMIN-001: Bulk Upload

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

### AC-ADMIN-002: Team Management

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

## 7.11 Email Notifications

### AC-EMAIL-001: Booking Confirmation Email

**GIVEN** booking completed  
**WHEN** confirmation email sent  
**THEN**:

- ✅ Sent within 1 minute of booking
- ✅ Contains all booking details
- ✅ Shows price breakdown
- ✅ Contains cancellation policy
- ✅ Hotel contact information included
- ✅ Fondoke support contact visible

### AC-EMAIL-002: Price Alert Email

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

## 7.12 Performance & Reliability

### AC-PERF-001: Page Load Times

**GIVEN** user navigates to any page  
**WHEN** page loads  
**THEN**:

- ✅ Initial load < 2 seconds
- ✅ Search results < 3 seconds
- ✅ Map view loads < 4 seconds
- ✅ Hotel details < 2 seconds
- ✅ Images lazy-load progressively
- ✅ Smooth transitions between pages

### AC-PERF-002: Real-time Updates

**GIVEN** user viewing trading page  
**WHEN** prices change  
**THEN**:

- ✅ Ticker updates every 5 seconds
- ✅ Price charts update every 30 seconds
- ✅ No page refresh required
- ✅ Updates don't interrupt user interaction
- ✅ WebSocket connection maintained
- ✅ Fallback to polling if WebSocket fails

### AC-PERF-003: Mobile Responsiveness

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

## 7.13 Security & Privacy

### AC-SEC-001: Data Encryption

**GIVEN** any data transmission  
**WHEN** data sent to/from server  
**THEN**:

- ✅ All connections use HTTPS/TLS 1.3
- ✅ Payment data encrypted end-to-end
- ✅ PCI DSS Level 1 compliant
- ✅ Personal data encrypted at rest
- ✅ Encryption keys rotated regularly
- ✅ No sensitive data in logs

### AC-SEC-002: Authentication Security

**GIVEN** user authentication attempt  
**WHEN** authenticating  
**THEN**:

- ✅ Magic links expire after 15 minutes
- ✅ Session timeout after 30 minutes inactivity (Refresh required)
- ✅ IP logging for audit trail

### AC-SEC-003: Privacy Compliance

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

[← Back to Main Document](../../FONDOKE_USERPORTAL_PRD.md)

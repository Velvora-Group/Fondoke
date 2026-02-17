# 6. Acceptance Criteria

**Document:** Fondoke Admin Portal PRD - Acceptance Criteria  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

---

## 6.1 User Management

**AC-UM-001: User Registration**

```
GIVEN a new user on the registration page
WHEN they complete the form with valid information
THEN:
  ✓ Account is created in "pending" status
  ✓ Verification email is sent
  ✓ User is redirected to email verification page
  ✓ System displays success message
```

**AC-UM-002: KYC Submission**

```
GIVEN a registered user with no KYC verification
WHEN they upload required documents (ID, address proof)
THEN:
  ✓ Documents are securely stored
  ✓ Admin receives notification for review
  ✓ User status changes to "pending approval"
  ✓ User can track KYC status
```

**AC-UM-003: Admin User Approval**

```
GIVEN an admin reviewing a pending user
WHEN admin approves the user
THEN:
  ✓ User status changes to "active"
  ✓ User receives approval email
  ✓ User gains access to approved features
  ✓ Approval timestamp and admin recorded
```

## 6.2 Hotel Booking

**AC-HB-001: Hotel Search**

```
GIVEN a user on the search page
WHEN they enter "Paris" as destination and select dates
THEN:
  ✓ System displays available hotels in Paris
  ✓ Results show price in user's selected currency
  ✓ Hotels can be filtered by amenities, price, rating
  ✓ Results load within 3 seconds
```

**AC-HB-002: Booking Creation**

```
GIVEN a user has selected a hotel and room
WHEN they complete booking with valid payment
THEN:
  ✓ Payment is processed successfully
  ✓ Booking is created with "confirmed" status
  ✓ Confirmation email sent with booking details
  ✓ Booking appears in user's booking history
  ✓ Hotel inventory is reduced by 1
```

**AC-HB-003: Voucher Application**

```
GIVEN a user at checkout with voucher code "SUMMER2026"
WHEN they apply the valid voucher code
THEN:
  ✓ System validates voucher is active and not expired
  ✓ Discount is calculated correctly (20% for percentage)
  ✓ Final price is updated with discount applied
  ✓ Voucher usage counter increments
  ✓ Voucher code shown in booking confirmation
```

**AC-HB-004: Booking Cancellation**

```
GIVEN a user with a confirmed booking
WHEN admin processes cancellation request
THEN:
  ✓ Booking status changes to "cancelled"
  ✓ Refund calculated per cancellation policy
  ✓ Refund processed to original payment method
  ✓ Cancellation email sent to user
  ✓ Hotel inventory restored
  ✓ Activity logged in booking history
```

## 6.3 Trading Marketplace

**AC-TM-001: List Booking for Sale**

```
GIVEN a user with a confirmed booking (check-in 48+ hours away)
WHEN they create a listing with price and description
THEN:
  ✓ Listing is created and published to marketplace
  ✓ Listing displays booking details accurately
  ✓ Price is within allowed range (±20% to +50%)
  ✓ Original booking cannot be cancelled
  ✓ Listing appears in seller's active listings
```

**AC-TM-002: Purchase from Marketplace**

```
GIVEN a buyer viewing a marketplace listing
WHEN they click "Purchase" and complete payment
THEN:
  ✓ Payment is held in escrow
  ✓ Booking transfer initiated
  ✓ Seller receives sale notification
  ✓ Buyer receives purchase confirmation
  ✓ Listing status changes to "sold"
  ✓ Listing removed from marketplace
```

**AC-TM-003: Booking Transfer**

```
GIVEN a completed trade purchase
WHEN booking transfer is processed (24-48 hours)
THEN:
  ✓ Booking ownership transfers to buyer
  ✓ Booking appears in buyer's bookings
  ✓ Booking removed from seller's bookings
  ✓ Payment released from escrow to seller
  ✓ Platform fee (5%) deducted
  ✓ Both parties receive confirmation emails
```

**AC-TM-004: Trade Dispute**

```
GIVEN a buyer with dispute about transferred booking
WHEN buyer raises dispute within 24 hours
THEN:
  ✓ Payment remains in escrow
  ✓ Admin receives dispute notification
  ✓ Both parties can submit evidence
  ✓ Dispute status tracked
  ✓ Admin can resolve and release/refund payment
```

## 6.4 Contract Management

**AC-CM-001: Create Contract**

```
GIVEN an admin creating a new hotel contract
WHEN they complete the contract form with all required fields
THEN:
  ✓ Contract is created with unique ID
  ✓ Contract status is "active"
  ✓ Inventory can be uploaded
  ✓ Contract appears in contracts list
  ✓ Hotel partner receives notification
```

**AC-CM-002: Availability Calendar**

```
GIVEN an active contract with inventory
WHEN admin views availability calendar
THEN:
  ✓ Calendar displays 365 days
  ✓ Available dates shown in green
  ✓ Partially booked in yellow
  ✓ Fully booked in red
  ✓ Blackout dates in gray
  ✓ Admin can add/remove blackout dates
```

**AC-CM-003: Contract Booking**

```
GIVEN a user booking a hotel with active contract
WHEN booking is confirmed
THEN:
  ✓ Inventory is deducted from contract
  ✓ Contract booking counter increases
  ✓ Booking marked as "contract booking"
  ✓ Special commission rate applied
  ✓ Contract performance metrics updated
```

**AC-CM-004: Contract Termination**

```
GIVEN an admin terminating a contract
WHEN termination is submitted with reason
THEN:
  ✓ Contract status changes to "terminated"
  ✓ New bookings blocked
  ✓ Existing bookings remain valid
  ✓ Termination details recorded
  ✓ Hotel partner notified
  ✓ Final settlement report generated
```

## 6.5 Voucher System

**AC-VS-001: Create Voucher**

```
GIVEN an admin creating a new voucher
WHEN they complete the form with code "WELCOME50"
THEN:
  ✓ Voucher is created with unique code
  ✓ Discount settings saved (type, value, currency)
  ✓ Validity period configured (start/end dates)
  ✓ Usage limits set (max uses, per user)
  ✓ Voucher status is "active"
  ✓ Voucher appears in vouchers list
```

**AC-VS-002: Voucher Validation (Success)**

```
GIVEN a user with booking amount $250
WHEN they apply voucher "WELCOME50" ($50 off, min $200)
THEN:
  ✓ Voucher validates successfully
  ✓ $50 discount applied
  ✓ Final price becomes $200
  ✓ Success message displayed
  ✓ Discount shown in price breakdown
```

**AC-VS-003: Voucher Validation (Failure)**

```
GIVEN a user with booking amount $150
WHEN they apply voucher "WELCOME50" (min $200)
THEN:
  ✓ Validation fails
  ✓ Error message: "Minimum booking amount $200 required"
  ✓ No discount applied
  ✓ Original price remains unchanged
```

**AC-VS-004: Voucher Usage Tracking**

```
GIVEN a voucher with max 100 uses, currently at 99
WHEN 2 users simultaneously apply the voucher
THEN:
  ✓ First user's application succeeds
  ✓ Second user's application fails
  ✓ Error: "Voucher limit reached"
  ✓ Usage counter shows 100/100
  ✓ Voucher auto-marked as exhausted
```

**AC-VS-005: Voucher Analytics**

```
GIVEN an admin viewing voucher details
WHEN they navigate to Analytics tab
THEN:
  ✓ Total uses displayed
  ✓ Total discount given calculated
  ✓ Average discount per use shown
  ✓ Usage progress bar displayed
  ✓ Redemption rate percentage shown
```

## 6.6 Admin Dashboard

**AC-AD-001: User Management**

```
GIVEN an admin on Users tab
WHEN they search for user "sarah.j@email.com"
THEN:
  ✓ Search results display matching user
  ✓ User details accessible via click
  ✓ User tabs (Info, Bookings, Trades, History) functional
  ✓ Actions menu (Approve, Suspend, Ban) available
  ✓ All actions require confirmation
```

**AC-AD-002: Booking Management**

```
GIVEN an admin viewing booking "BK-123"
WHEN they click to view details
THEN:
  ✓ Booking information displayed completely
  ✓ Hotel details shown with photos
  ✓ Guest information visible
  ✓ Payment details accessible
  ✓ Activity history tab shows all events
  ✓ Actions (Cancel, Refund) available with proper rules
```

**AC-AD-003: Analytics Dashboard**

```
GIVEN an admin on Analytics tab
WHEN they select "Financial" sub-tab
THEN:
  ✓ Revenue chart displays correctly
  ✓ Data aggregated by day/week/month
  ✓ Multiple metrics available (bookings, trades, refunds)
  ✓ Export functionality available
  ✓ Charts are interactive
  ✓ Real-time data updates
```

**AC-AD-004: Activity History**

```
GIVEN an admin viewing booking activity history
WHEN activity history tab is selected
THEN:
  ✓ All API calls logged with timestamps
  ✓ Source, Action, Duration, Status columns displayed
  ✓ Request/Response JSON viewable via OPEN buttons
  ✓ Email activities show formatted body with line breaks
  ✓ Activities sorted by most recent first
  ✓ Pagination for large datasets
```

## 6.7 Multi-Currency

**AC-MC-001: Currency Selection**

```
GIVEN a user on the platform
WHEN they select EUR as preferred currency
THEN:
  ✓ All prices displayed in EUR (€)
  ✓ Conversion applied at current exchange rate
  ✓ Preference saved to user profile
  ✓ Currency symbol updated throughout UI
  ✓ Historical bookings show original currency
```

**AC-MC-002: Currency Conversion**

```
GIVEN a hotel priced at $1000 USD
WHEN user's currency is EUR (rate: 0.85)
THEN:
  ✓ Displayed price: €850
  ✓ Conversion rate shown
  ✓ Final payment processed in user's currency
  ✓ Both USD and EUR amounts recorded
```

## 6.8 Performance & Security

**AC-PS-001: Page Load Performance**

```
GIVEN any page on the platform
WHEN page is accessed
THEN:
  ✓ Initial page load < 3 seconds
  ✓ Search results display < 3 seconds
  ✓ Images optimized and lazy-loaded
  ✓ API responses < 1 second
```

**AC-PS-002: Data Security**

```
GIVEN sensitive user data
WHEN stored or transmitted
THEN:
  ✓ All connections use HTTPS/SSL
  ✓ Passwords hashed with bcrypt
  ✓ Payment data PCI compliant
  ✓ Personal data encrypted at rest
  ✓ Session tokens expire after inactivity
```

**AC-PS-003: Access Control**

```
GIVEN different user roles
WHEN accessing platform features
THEN:
  ✓ Regular Users: Booking only
  ✓ Advanced Users: Booking + Trading
  ✓ Admins: Full dashboard access
  ✓ Unauthorized access blocked with 403
  ✓ Authentication required for protected routes
```

---

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

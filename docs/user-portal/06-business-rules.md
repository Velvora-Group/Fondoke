# 6. Business Rules

**Document:** Fondoke PRD - Business Rules  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_USERPORTAL_PRD.md)

---

## 6.1 Booking Rules

### 6.1.1 General Booking Rules

- **Minimum Age**: Users must be 18+ to create bookings
- **Advance Booking**: Maximum 365 days in advance
- **Same-day Booking**: Allowed until hotel check-in time
- **Multiple Rooms**: Maximum 5 rooms per booking
- **Guest Count**: Maximum 4 adults per room, 3 children per room
- **Children Age Range**: 0-17 years (18+ are adults)
- **Minimum Stay**: 1 night
- **Maximum Stay**: 90 consecutive nights

### 6.1.2 Date Validation

- Check-out date must be after check-in date
- Dates must use dd/mm/yyyy format consistently
- Cannot book dates in the past
- Must respect hotel-specific blackout dates
- Weekend pricing applies to Friday/Saturday nights

### 6.1.3 Payment Rules

- Full payment required at booking
- Accepted currencies: AED, USD, EUR, GBP, QAR, SAR, BHD, OMR, KWD
- Payment must clear before confirmation
- Authorization hold for 24 hours on credit cards

## 6.2 Trading Marketplace Rules

### 6.2.1 Listing Eligibility

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

### 6.2.2 Pricing Rules (Not Applicable)

- **Minimum Discount**: 5% off original price
- **Maximum Discount**: 40% off original price
- **Price Changes**: Maximum 3 price changes per listing
- **Price Floor**: Cannot list below hotel's current direct price
- **Dynamic Pricing**: Platform can suggest optimal pricing
- **Last-Minute Surge**: Prices can increase if high demand

### 6.2.3 Transaction Rules (Not Applicable until Fondoke Business Approves)

- **Platform Fee**: x USD of sale price (charged to seller)
- **Buyer Fee**: X USD service fee on purchase
- **Instant Purchase**: No negotiation, immediate transfer

## 6.3 Cancellation Rules

### 6.3.1 Standard Cancellations

- **Free Cancellation**: Varies by booking and hotels cancellation policies(24-48 hours before check-in, or other rules may apply)
- **Non-Refundable Bookings**: No refund through Fondoke
- **Partial Stay**: No refund for unused nights after check-in
- **No-Show**: No refund, booking marked as completed
- **Force Majeure**: Full refund (natural disasters, pandemics, etc.) Question: Does Fondoke has Insurance? or customer should buy insurance through Fondoke or Insurance company

### 6.3.2 Refund Processing

- **Refund Timeline**: 5-7 business days
- **Refund Method**: Original payment method only
- **Partial Refunds**: Prorated by night
- **Service Fees**: Non-refundable (except force majeure)
- **Currency Exchange**: Refund in original currency paid

## 6.4 User Account Rules

### 6.4.1 Account Creation

- **Magic Link Expiry**: 15 minutes
- **Profile Completion**: Required before first booking
- **Duplicate Accounts**: Prohibited (detected by email/phone)
- **Account Types**: Individual - Company (Day2) (cannot change type)

### 6.4.2 Account Status

**Status Levels**:

1. **Pending**: New account, Awaiting first login. Magic Ling sent
2. **Suspended**: Temporary restriction, can view only
3. **Active**: Can access platform and use all features

**Status Triggers**:

- **Suspension**: Payment issues, seller disputes, policy violations

### 6.4.3 Account Security

- **Magic Link is sent once**: each 15 minute upon request
- **Suspicious Activity**: Automatic flagging and verification required

## 6.5 Review & Rating Rules (Not Applicable - maybe in Day3)

### 6.5.1 Review Eligibility

- Must have completed stay
- Review window: 30 days after check-out
- One review per booking
- Cannot review own listings
- Must have verified booking

### 6.5.2 Review Content Rules

- Minimum 50 characters
- Maximum 1000 characters
- No personal information (phone, email, address)
- No profanity or hate speech
- No promotional content
- Must be relevant to stay
- Cannot include external links

### 6.5.3 Rating System

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

### 6.5.4 Review Moderation

- Auto-moderation for flagged words
- Manual review for disputed content
- Users can report inappropriate reviews
- Platform can remove violating reviews
- Sellers can respond to reviews (one time)

## 6.6 Currency & Pricing Rules

### 6.6.1 Supported Currencies

- **Primary**: USD ($)
- **Secondary**: AED, USD, EUR, GBP, QAR, SAR, BHD, OMR, KWD
- **Exchange Rates**: Updated daily at 12:00 AM UTC
- **Rate Source**: European Central Bank rates
- **Display**: Always show customers chosen currancy

### 6.6.2 Price Display Rules

- All prices include applicable taxes (where required)
- Additional fees shown separately
- Final price highlighted clearly
- Original price shown with strikethrough if discounted
- Savings percentage displayed prominently
- "Price includes" tooltip available

### 6.6.3 Dynamic Pricing (Not applicable - pricing is based only on Travellanda partner)

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

## 6.7 Data & Privacy Rules

### 6.7.1 Data Collection

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

### 6.7.2 Data Protection

- **Encryption**: All sensitive data encrypted at rest and in transit
- **PCI Compliance**: Level 1 PCI DSS certified
- **GDPR Compliance**: Full compliance for EU users
- **Data Retention**: 7 years for financial records, 2 years for analytics
- **Right to Deletion**: Users can request account and data deletion
- **Data Export**: Users can download their data (GDPR requirement)

### 6.7.3 Third-Party Sharing

**Shared With**:

- Hotels (booking information only)
- Payment processors (payment data only)
- Law enforcement (when legally required)

**Not Shared With**:

- Marketing companies (without explicit consent)
- Other users (except seller/buyer in transactions)
- Social media platforms

## 6.8 Dispute Resolution

### 6.8.1 Dispute Categories

1. **Booking Disputes**: Wrong dates, rooms, pricing errors
2. **Trading Disputes**: Seller didn't transfer, buyer didn't pay
3. **Quality Disputes**: Hotel not as described
4. **Payment Disputes**: Unauthorized charges, refund issues
5. **Account Disputes**: Suspended/banned accounts

### 6.8.2 Dispute Process

**Step 1**: User submits dispute with evidence
**Step 2**: System auto-mediates simple disputes
**Step 3**: Customer service reviews within 24 hours
**Step 4**: Investigation with both parties (3-5 days)
**Step 5**: Resolution and compensation (if applicable)
**Step 6**: Appeal option (within 7 days of decision)

### 6.8.3 Dispute Outcomes

- **Full Refund**: Complete reversal of transaction
- **Partial Refund**: Prorated compensation
- **Credit**: Fondoke credit for future bookings
- **No Action**: Dispute not substantiated
- **Account Penalty**: Warning, suspension, or ban

## 6.9 Company Admin Rules (Not applicable - Maybe in Day3)

### 6.9.1 Access Control

- **Authentication**: Separate admin credentials required
- **Permissions**: Role-based access control (RBAC)
- **Activity Logging**: All actions logged and auditable
- **IP Restrictions**: Admin access from approved IPs only
- **2FA Required**: Two-factor authentication mandatory

### 6.9.2 Bulk Operations

- **Maximum Batch Size**: 500 bookings per upload
- **Validation Required**: All entries validated before processing
- **Failure Handling**: Partial success allowed, errors reported
- **Approval Workflow**: Bookings over $10K require supervisor approval
- **Budget Limits**: Cannot exceed allocated budget per department

### 6.9.3 Team Management

- **User Limits**: Up to 1000 team members
- **Role Types**: Admin, Manager, User, Viewer
- **Spending Limits**: Set per user or role
- **Approval Chains**: Up to 3 levels of approval
- **Audit Trail**: Complete history of all team actions

---

[← Back to Main Document](../../FONDOKE_USERPORTAL_PRD.md)

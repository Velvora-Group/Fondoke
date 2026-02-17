# 5. Business Rules

**Document:** Fondoke Admin Portal PRD - Business Rules  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

---

## 5.1 User Management Rules

**UR-001: User Registration**

- Email must be unique in the system
- Password must be minimum 8 characters with uppercase, lowercase, and number
- Email verification required before account activation
- Users start as "Regular User" role by default

**UR-002: KYC Verification**

- Advanced features (trading) require KYC completion
- Admin must approve KYC documents within 24-48 hours
- Rejected KYC must include reason
- Users can resubmit KYC documents

**UR-003: User Roles**

- Regular User: Can book hotels only
- Advanced User: Can book hotels + trade bookings
- Corporate User: Can manage company bookings
- Admin: Full platform access

**UR-004: Account Status**

- Active: Full access to platform
- Pending: Registration incomplete or awaiting approval
- Suspended: Temporary restriction (can be reactivated)
- Rejected: Account rejected (cannot access platform)
- Banned: Permanent restriction

## 5.2 Booking Rules

**BR-001: Booking Creation**

- User must be logged in to make a booking
- Check-in date must be in the future
- Check-out date must be after check-in date
- Minimum 1 guest required
- Payment must be successful before booking confirmation

**BR-002: Booking Cancellation**

- Cancellation allowed only if hotel policy permits
- Refund amount based on cancellation policy
- Cancellation must be processed by admin
- Cancellation reason required

**BR-003: Booking Modification**

- Modifications subject to hotel availability
- Price difference must be paid/refunded
- Modification must be within hotel policy

**BR-004: Booking Status**

- Pending: Payment processing
- Confirmed: Booking successful
- Checked-In: Guest has checked in
- Checked-Out: Guest has checked out
- Cancelled: Booking cancelled
- No-Show: Guest did not arrive

## 5.3 Trading Rules

**TR-001: Listing Creation**

- Only confirmed bookings can be listed for sale
- Check-in date must be at least 48 hours away
- Listing must include complete booking details
- Seller cannot cancel original booking while listed

**TR-002: Pricing Constraints**

- Minimum sale price: Original price - 20%
- Maximum sale price: Original price + 50%
- Pricing must be in same currency as original booking
- No hidden fees allowed

**TR-003: Trade Execution**

- Payment held in escrow for 24-48 hours
- Booking transfer initiated after payment confirmation
- Seller receives payment after successful transfer
- Buyer has 24 hours to dispute

**TR-004: Trading Eligibility**

- Only KYC-verified users can trade
- Account must be in good standing (no active disputes)
- Advanced User role required
- Minimum account age: 30 days (configurable)

**TR-005: Trade Status**

- Listed: Available for purchase
- Sold: Purchase completed
- Transferred: Booking transferred to buyer
- Cancelled: Listing cancelled by seller
- Disputed: Under dispute resolution

## 5.4 Contract Rules

**CR-001: Contract Creation**

- Only admins can create contracts
- Contract must have valid hotel information
- Contract period minimum: 30 days
- Room allocation must be specified
- Commission rate must be between 5-20%

**CR-002: Contract Status**

- Active: Contract is operational
- Expiring: Less than 30 days until end date
- Expired: Contract period ended
- Terminated: Contract terminated early

**CR-003: Inventory Management**

- Inventory must be updated daily
- Blackout dates override availability
- Overbooking not allowed
- Real-time inventory sync required

**CR-004: Contract Termination**

- Termination reason required
- Notice period: Minimum 30 days (unless breach)
- Termination types: Mutual, Breach, Expiry
- Outstanding bookings must be honored

## 5.5 Voucher Rules

**VR-001: Voucher Creation**

- Voucher code must be unique (3-20 characters)
- Valid from date cannot be in the past
- Valid to date must be after valid from date
- Percentage discount: 1-100%
- Fixed discount: Minimum $1 or €1

**VR-002: Voucher Applicability**

- All: Apply to any booking
- Specific Hotels: Apply to selected hotels only
- Specific Users: Apply to selected user groups only

**VR-003: Usage Limits**

- Maximum uses: Total times voucher can be used (platform-wide)
- Uses per user: Max times a single user can use it
- Cannot exceed maximum uses

**VR-004: Voucher Validation**

- Code must exist and be active
- Current date must be within validity period
- User must not have exceeded per-user limit
- Total usage must not exceed maximum uses
- Booking amount must meet minimum requirement
- User must be eligible (if restricted)

**VR-005: Voucher Status**

- Active: Can be used
- Expired: Validity period ended
- Disabled: Manually deactivated by admin

## 5.6 Payment Rules

**PR-001: Payment Processing**

- All payments must be processed through secure gateway
- Payment confirmation required before booking confirmation
- Failed payments result in booking cancellation
- Retry allowed up to 3 times

**PR-002: Refund Processing**

- Refunds processed within 5-7 business days
- Refund amount based on cancellation policy
- Partial refunds allowed
- Refund to original payment method

**PR-003: Escrow Rules**

- Trade payments held for 24-48 hours
- Released only after successful booking transfer
- Disputes extend escrow hold
- Platform fee deducted before release

**PR-004: Currency Rules**

- User can select preferred currency (USD/EUR)
- Conversion rate applied at booking time
- Historical rates stored for reporting
- Platform displays both original and converted amounts

## 5.7 Commission & Fee Rules

**FR-001: Booking Commission**

- Standard bookings: 10-15% commission
- Contract bookings: Negotiated commission (5-20%)
- Commission calculated on gross booking amount

**FR-002: Trading Fees**

- Seller fee: 5% of sale price
- Buyer fee: None
- Platform retains trading fee
- Fee deducted from seller payment

**FR-003: Cancellation Fees**

- Cancellation fee based on hotel policy
- No-show: 100% charge
- Late cancellation: Per hotel policy
- Free cancellation: No fee

---

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

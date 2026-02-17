# 4. User Flows

**Document:** Fondoke Admin Portal PRD - User Flows  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

---

## 4.1 User Registration & Onboarding

```
START → Landing Page
  ↓
User clicks "Sign Up"
  ↓
Registration Form (Email, Password, Basic Info)
  ↓
Email Verification
  ↓
KYC Process (for trading access)
  ↓
Profile Setup (Address, Payment Methods)
  ↓
Admin Approval (for advanced features)
  ↓
Account Active → Dashboard
```

## 4.2 Hotel Booking Flow

```
User Login → Search Hotels
  ↓
Enter Destination, Dates, Guests
  ↓
[AI-Powered Search] Apply Filters & Preferences
  ↓
View Search Results (Hotels List)
  ↓
Select Hotel → View Details
  ↓
Choose Room Type & Rate Plan
  ↓
Apply Voucher Code (optional)
  ↓
Review Booking Summary
  ↓
Payment Processing
  ↓
Booking Confirmation
  ↓
Email Confirmation & Booking Details
```

## 4.3 Trading Marketplace Flow

### 4.3.1 Selling a Booking

```
User Dashboard → My Bookings
  ↓
Select Booking to Sell
  ↓
Click "List for Sale"
  ↓
Set Sale Price (min: original price - 20%, max: original + 50%)
  ↓
Add Description & Terms
  ↓
Submit Listing
  ↓
Admin Review (if flagged)
  ↓
Listing Published on Marketplace
  ↓
Buyer Purchases
  ↓
Payment Processing & Escrow
  ↓
Transfer Booking to Buyer
  ↓
Release Payment to Seller
```

### 4.3.2 Buying from Marketplace

```
Browse Marketplace
  ↓
Filter by Destination, Date, Price
  ↓
View Listing Details
  ↓
Verify Booking Authenticity
  ↓
Click "Purchase"
  ↓
Payment Processing
  ↓
Escrow Hold (24-48 hours)
  ↓
Booking Transfer Initiated
  ↓
Booking Transferred to Buyer Account
  ↓
Payment Released to Seller
  ↓
Confirmation & Receipt
```

## 4.4 Contract Management Flow (B2B)

```
Hotel Partner → Submit Contract Proposal
  ↓
Admin Review → Contract Negotiation
  ↓
Contract Terms Agreement
  - Room Allocation
  - Pricing Structure
  - Commission Rates
  - Validity Period
  ↓
Digital Contract Signing
  ↓
Inventory Upload
  ↓
Availability Calendar Management
  ↓
Bookings from Contract Inventory
  ↓
Automated Settlement Reports
  ↓
Contract Renewal / Termination
```

## 4.5 Voucher Usage Flow

```
User has Voucher Code
  ↓
During Booking Checkout
  ↓
Enter Voucher Code
  ↓
System Validation:
  - Code Exists
  - Not Expired
  - Usage Limit Not Exceeded
  - Minimum Booking Amount Met
  - User Eligible
  ↓
Apply Discount
  ↓
Update Final Price
  ↓
Complete Payment
  ↓
Record Voucher Usage
```

## 4.6 Admin Operations Flow

```
Admin Login → Dashboard
  ↓
Monitor Activities:
  - New User Registrations (Approve/Reject)
  - Pending Bookings
  - Active Trades
  - Contract Status
  - Platform Analytics
  ↓
User Management:
  - View User Details
  - Approve KYC
  - Suspend/Ban Accounts
  - View Activity History
  ↓
Booking Management:
  - View Booking Details
  - Process Cancellations
  - Handle Refunds
  - Resolve Disputes
  ↓
Trading Management:
  - Monitor Listings
  - Review Flagged Trades
  - Manage Escrow
  - Handle Disputes
  ↓
Contract Management:
  - Add New Contracts
  - Update Terms
  - Manage Availability
  - Generate Reports
  ↓
Voucher Management:
  - Create Vouchers
  - Monitor Usage
  - View Analytics
  - Deactivate Vouchers
  ↓
Analytics & Reporting
```

---

[← Back to Main Document](../../FONDOKE_ADMINPORTAL_PRD.md)

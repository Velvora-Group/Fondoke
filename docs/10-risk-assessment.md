# 10. Risk Assessment

**Document:** Fondoke PRD - Risk Assessment  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../FONDOKE_USERPORTAL_PRD.md)

---

## 10.1 Technical Risks

| Risk                     | Impact   | Probability | Mitigation                                   |
| ------------------------ | -------- | ----------- | -------------------------------------------- |
| Hotel API downtime       | High     | Medium      | Implement caching, fallback to manual entry  |
| Payment processor issues | Critical | Low         | Multi-processor setup, queue failed payments |
| Scalability bottlenecks  | High     | Medium      | Auto-scaling, load testing, CDN              |
| Security breach          | Critical | Low         | Penetration testing, bug bounty, insurance   |
| Data loss                | Critical | Very Low    | Daily backups, multi-region replication      |

## 10.2 Business Risks

| Risk                             | Impact   | Probability | Mitigation                               |
| -------------------------------- | -------- | ----------- | ---------------------------------------- |
| Hotel platforms blocking resales | Critical | Medium      | Legal compliance, platform partnerships  |
| Low user adoption                | High     | Medium      | Marketing campaigns, referral incentives |
| Fraudulent transactions          | High     | Medium      | Verification system, escrow, insurance   |
| Regulatory changes               | High     | Low         | Legal counsel, compliance monitoring     |
| Competition from OTAs            | Medium   | High        | Unique value proposition, better pricing |

## 10.3 Legal Risks

| Risk                                   | Impact   | Probability | Mitigation                         |
| -------------------------------------- | -------- | ----------- | ---------------------------------- |
| Terms violation with booking platforms | Critical | Medium      | Clear terms, platform partnerships |
| Consumer protection laws               | High     | Low         | Compliance team, clear policies    |
| Tax compliance issues                  | High     | Low         | Tax automation, accounting firm    |
| Data privacy violations (GDPR)         | Critical | Low         | Privacy by design, regular audits  |
| Liability for cancelled bookings       | Medium   | Medium      | Clear disclaimers, insurance       |

---

[← Back to Main Document](../FONDOKE_USERPORTAL_PRD.md)

# 8. Technical Architecture Overview

**Document:** Fondoke PRD - Technical Architecture  
**Version:** 1.0  
**Last Updated:** February 17, 2026

[← Back to Main Document](../FONDOKE_USERPORTAL_PRD.md)

---

## 8.1 Backend Stack (This to be reviewed by Roman)

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

## 8.2 Frontend Stack (This to be reviewed by Nedim)

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

## 8.3 Third-Party Integrations (This to be reviewed by Roman)

- **Payment Processing**: Stripe
- **Email Delivery**: SendGrid (transactional)
- **SMS Notifications**: Twilio (Day2)
- **Analytics**: Google Analytics 4, Mixpanel
- **Error Tracking**: Sentry
- **Monitoring**: AWS CloudWatch, DataDog
- **CDN**: CloudFront
- **Hotel Data APIs**: Travellanda

---

[← Back to Main Document](../FONDOKE_USERPORTAL_PRD.md)

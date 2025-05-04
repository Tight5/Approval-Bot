# Approval Bot 2.0

A sophisticated content approval workflow application that leverages advanced Slack integration for seamless multi-stage review processes.

![Approval Bot Screenshot](attached_assets/image_1746286448731.png)

## 🌟 Features

- **Multi-stage Approval Workflow**: Content flows through Marketing, StratCom, and CEO approval stages
- **Advanced Slack Integration**: Real-time notifications with proper user tagging
- **Rich Notification Format**: Block-based Slack messages with visual status indicators
- **Email Notifications**: Optional email alerts via SendGrid
- **Visual Progress Tracking**: Animated progress indicator shows submission status
- **Parallel Approvals**: Marketing and StratCom can approve simultaneously
- **PostgreSQL Database**: Secure and reliable data storage
- **Modern React Frontend**: Clean, responsive UI built with React and Tailwind CSS

## 🛠️ Technology Stack

- **Frontend**: React, Tailwind CSS, shadcn/ui components
- **Backend**: Node.js, Express
- **Database**: PostgreSQL with Drizzle ORM
- **Notifications**: Slack Web API/Webhooks, SendGrid Email API
- **Deployment**: Replit (can be deployed to any Node.js hosting platform)

## 📋 Setup Instructions

### Prerequisites

- Node.js (v18+)
- PostgreSQL database
- Slack workspace with webhook URL
- SendGrid account (optional)

### Environment Variables

Create a `.env` file in the root directory with the following variables:

```
# Database Connection
DATABASE_URL=postgresql://username:password@host:port/database

# Slack Configuration
SLACK_WEBHOOK_URL=https://hooks.slack.com/services/xxx/yyy/zzz
SLACK_CHANNEL_ID=your-channel-id
SLACK_USER_MARKETING=marketing-user-id
SLACK_USER_STRATCOM=stratcom-user-id
SLACK_USER_CEO=ceo-user-id

# Email Configuration (Optional)
SENDGRID_API_KEY=your-sendgrid-api-key
SENDGRID_VERIFIED_SENDER=your-verified-email@example.com
```

### Installation Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/Tight5/Approval-Bot.git
   cd Approval-Bot
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up the database:
   ```bash
   npm run db:push
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

5. Access the application at http://localhost:5000

## 🔄 Approval Workflow

1. **Content Submission**: Users submit content requests with title, description, links, etc.
2. **Initial Review**: Marketing and StratCom receive Slack notifications and can review in parallel
3. **CEO Review**: After both Marketing and StratCom approve, CEO receives notification for final approval
4. **Completion**: Upon CEO approval, content is marked as fully approved and all parties are notified

## 🔔 Notification System

### Slack Notifications

The application sends detailed Slack notifications at each stage of the process:
- New submissions (tags Marketing and StratCom)
- Approvals (includes who approved and current status)
- Rejections (includes rejection reason if provided)
- CEO review requests (tags CEO when their review is needed)

### Email Notifications (Optional)

If configured, the application can also send email notifications using SendGrid:
- Submission confirmations
- Approval notifications
- Rejection notifications

## 🧩 Project Structure

```
/client             # Frontend React application
  /src
    /components     # UI components
    /hooks          # Custom React hooks
    /lib            # Utility functions
    /pages          # Application pages
/server             # Backend Express server
  /routes.ts        # API routes
  /storage.ts       # Database operations
  /slack.ts         # Slack notification logic
  /email.ts         # Email notification logic
/shared             # Shared code between frontend and backend
  /schema.ts        # Database schema and types
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Created By

Developed for NEC Communications Department to streamline the content approval process.

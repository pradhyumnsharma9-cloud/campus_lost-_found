# Campus Lost and Found — Outcome Checklist

## 1. Responsive Campus Lost and Found experience
- The application is named Campus Lost and Found.
- The interface is simple, focused, and suitable for a Web Development minor-project demonstration.
- The interface works on desktop and mobile layouts.
- Browse, report, dashboard, and moderation states have clear empty, loading, success, and error feedback.

## 2. Authentication and roles
- Students can sign in and sign out using the supplied real authentication flow.
- Authenticated users can access report creation and ownership-based actions.
- Administrator-only actions are protected by server-side role checks.

## 3. Lost and found reports
- Authenticated users can report lost or found items.
- A report captures item name, category, date, campus location, description, optional photo URL, and contact details.
- A report can upload an optional JPG, PNG, or WebP item photo up to 5 MB, preview it before submission, and persist it through managed storage.
- Reports display LOST or FOUND labels and Open or Returned status indicators.
- Input values are validated and clear errors are shown.

## 4. Browse, search, and filtering
- Visitors can browse reports.
- Reports can be searched by keyword.
- Reports can be filtered by type, category, status, date, or location.
- A detailed report view exposes the item information, photo when available, contact details, and current status.

## 5. Ownership-based management
- Report owners can edit their own submissions.
- Report owners can delete their own submissions.
- Report owners can mark an open report as returned.
- The server rejects unauthorized edits, deletes, and status changes.

## 6. Basic administrator moderation
- Administrators can review reports.
- Administrators can edit, delete, and update report status.
- The admin view includes useful summary counts.

## 7. Persistence and delivery readiness
- Accounts and reports persist in the managed MySQL database.
- The project has a route manifest and a working development server.
- The project passes type checking and production build checks before delivery.

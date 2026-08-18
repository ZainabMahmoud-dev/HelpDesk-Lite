# 🎫 HelpDesk Lite

> Internal Support Ticketing Workspace

HelpDesk Lite is an internal support ticketing solution designed to centralize employee support requests, establish clear ownership, and provide a transparent workflow for tracking and resolving issues.

---

## 📌 Overview

Organizations often receive internal support requests through multiple communication channels. This can lead to:

- Unclear ticket ownership
- Delayed follow-up
- Repeated clarification
- Difficulty tracking open and delayed requests
- Limited visibility for managers

**HelpDesk Lite** addresses these challenges through a centralized ticketing workspace.

---

## ✨ Core Features

### 📊 Dashboard
- Open Tickets
- Unassigned Tickets
- Resolved Tickets
- Average First Response Time
- Tickets Created vs Resolved
- Tickets by First Reply Time
- Tickets by Channel
- Satisfaction metrics
- Recent activity

### 🎫 Ticket Management
- Ticket creation
- Ticket assignment
- Ownership tracking
- Status management
- Priority management
- Conversation history
- Internal notes
- Ticket filtering

### 📥 Inbox
- Incoming ticket messages
- Read / unread states
- Priority indicators
- Message previews
- Reply panel

### 🔔 Notifications
- Ticket assignments
- Status changes
- New comments
- SLA breach warnings
- Mark all as read

### 📚 Knowledge Base
- Categories
- Article search
- Article listing
- Article metadata
- Shared knowledge resources

---

## 🔐 Authentication & Authorization

Authentication is designed around **Supabase Auth**.

### Roles

| Role | Access |
|------|--------|
| Admin | Full ticket, user, reporting and analytics access |
| Employee | Own tickets + shared Knowledge Base |

Row Level Security is used to protect ticket and user data according to the authenticated user's role.

---

## 🎨 Design System

The interface follows a centralized design system defined in:

[`DESIGN_1_.md`](./DESIGN.md)

### Main Design Principles

- Plus Jakarta Sans typography
- Indigo primary interface
- Emerald success states
- Light application background
- White content cards
- Consistent spacing system
- Rounded cards and controls
- Accessible focus states
- Responsive layouts
- Reduced-motion support

Reference design:

[`design.jpg`](./helpDesk.jpg)

---

## 🧠 Engineering Approach

```text
Business Problem
       ↓
Requirements Analysis
       ↓
Product Requirements
       ↓
Engineering Plan
       ↓
Jira Backlog
       ↓
Implementation
       ↓
Testing & Debugging
       ↓
Review & Verification
       ↓
Reliable Delivery

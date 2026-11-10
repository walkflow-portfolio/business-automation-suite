# Business Automation Suite

**Two automations that turn website enquiries into organised, followed-up customers, without anyone having to remember to do it.**

![n8n](https://img.shields.io/badge/n8n-automation-EA4B71) ![Gmail](https://img.shields.io/badge/Gmail-emails-EA4335) ![Google Calendar](https://img.shields.io/badge/Google_Calendar-bookings-4285F4) ![Supabase](https://img.shields.io/badge/Supabase-database-3ECF8E) ![Telegram](https://img.shields.io/badge/Telegram-alerts-26A5E4)

---

## The problem

Most enquiries are lost for ordinary reasons: the message sits unread, nobody follows up, a call gets double-booked, or something quietly fails and nobody notices. Each lost enquiry is lost revenue.

## Who it's for

Service businesses that take enquiries through a website and want every one handled quickly and consistently, from the first message to a booked call or viewing.

## The two automations

### 1. Enquiry, booking and follow-up automation

A new enquiry is captured, acknowledged, followed up automatically, and turned into a booked call, with a safety net if anything goes wrong.

- **Saved first:** the enquiry is stored before anything else happens, so an email problem can never lose it
- **Automatic follow-ups:** emails go out on a schedule and stop on their own when the customer replies, books, or the deal is won or lost
- **Smart booking:** customers pick from times that are genuinely free, based on working hours and the calendar
- **No double-booking:** a time that is taken can't be booked twice, even if two people try at once
- **Self-service changes:** customers can cancel or reschedule from a secure link, with no account needed
- **Recovery and alerts:** failed emails are retried, stuck bookings are released, and you get one clear alert (email, with Telegram as a backup) if something needs you

```mermaid
flowchart LR
    A[Website enquiry] --> B[Check and save the enquiry]
    B --> C[Reply: enquiry received]
    B --> D[Follow-up emails on a schedule]
    D --> E{Customer replies or books?}
    E -- Yes --> F[Follow-ups stop automatically]
    E -- No --> D
    C --> G[Customer picks a free time]
    G --> H[Booking confirmed in the calendar]
    D -. if something fails .-> I[Retry, recover and alert you]
```

### 2. Real-estate lead-to-viewing automation

Built for a real-estate agency: a property enquiry comes in and is matched to the right property and agent, with follow-up tasks created and the right people notified.

- **Instant handling:** every enquiry is checked and recorded as soon as it arrives
- **Right agent, right property:** enquiries are matched against current properties and agents
- **Follow-up tasks:** a follow-up task is created so no lead is forgotten
- **Everyone informed:** the client, the agent and the office all get an email
- **Safe against duplicates and failures:** repeat submissions are recognised, and any failure sends an alert instead of being lost

```mermaid
flowchart LR
    A[Property enquiry] --> B[Check the request]
    B --> C[Look at properties, agents and viewings]
    C --> D[Decide the best match]
    D --> E[Save the enquiry, match and follow-up task]
    E --> F[Email client, agent and office]
    B -. if something fails .-> G[Error handler alerts the admin]
```

## Screenshots

*The automations as built in n8n. Private details have been removed from the images.*

**Enquiry, booking and follow-up workflow**

![Enquiry, booking and follow-up workflow](docs/images/enquiry-booking-workflow.png)

**Safety net: error alerts and recovery**

![Error alerts and recovery workflow](docs/images/error-recovery-workflow.png)

**Real-estate lead-to-viewing workflow**

![Real-estate workflow](docs/images/real-estate-workflow.png)

**Real-estate error handler**

![Real-estate error handler](docs/images/real-estate-error-handler.png)

## Results

- The enquiry, booking and follow-up automation is a workflow of **80+ steps** with built-in safeguards, including saving enquiries first and preventing double-booking
- The automated test suites pass in full: **164 of 164** checks for the enquiry and booking logic, and **91 of 91** checks for the real-estate workflow

*Business results (response times, bookings, time saved) will be added here once confirmed.*

## Built with

`n8n` · `Gmail` · `Google Calendar` · `Google Sheets` · `Supabase` · `Telegram Bot`

## Want something like this?

I build automations like this for businesses: lead capture, follow-ups, and alerts. Get in touch at [walkflow.tech](https://walkflow.tech) or on [LinkedIn](https://linkedin.com/in/walkflow).

---

<sub>This repository is a showcase. A live demo is available on request — contact me via walkflow.tech or LinkedIn.</sub>

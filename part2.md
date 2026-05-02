# Part 2 — Form Submission, Google Calendar Integration & Email Automation

## Overview

In this section, the workflow is expanded beyond simple WhatsApp messaging. The AI agent now becomes a complete appointment management system by adding:

- Form submission handling
- Patient data collection
- Google Calendar appointment scheduling
- Gmail confirmation emails
- Workflow branching using Switch nodes
- WhatsApp appointment confirmations

This transforms the automation into a fully functional healthcare booking assistant.

---

# 1. Adding the Form Submission Node

## Purpose of the Form

After a patient receives the WhatsApp response, they are asked to complete a form.

The form collects important appointment details such as:
- Patient contact information
- Preferred appointment time
- Doctor selection
- Additional healthcare details

---

## Setting Up the Node

### Steps
1. Add a new node
2. Search:
   - `On Form Submission`
3. Select the built-in N8N form submission trigger

---

## Form Configuration

The presenter copies:
- Form title
- Description
- Instructions

directly from the provided **Healthcare Agent PDF**.

This simplifies setup and avoids manual writing.

---

## Form Workflow Process

### Flow
1. User sends WhatsApp message
2. AI replies with form link
3. User fills form
4. Form submission triggers next automation steps

---

## Example Form Data

The form may include:
- Full name
- Phone number
- Appointment timing
- Doctor name
- Medical concern

The form structure is customizable depending on the healthcare business.

---

# 2. Testing the Form Submission

## Workflow Execution

After the form node is configured:
1. Execute the workflow
2. Open the WhatsApp form link
3. Submit sample appointment data

---

## Result

Once submitted:
- The workflow automatically continues
- Appointment data becomes available inside N8N
- Other integrations can now use the submitted information

This confirms the form submission system is functioning correctly.

---

# 3. Integrating Google Calendar

## Purpose of Calendar Automation

The next step is automating appointment scheduling.

Instead of manually creating bookings:
- Appointments are automatically added to Google Calendar
- Doctors receive scheduling visibility instantly

---

# 4. Adding the Google Calendar Node

## Setup Process

### Steps
1. Add a new node
2. Search:
   - `Google Calendar`
3. Select:
   - Calendar Event node

---

## Creating Google Credentials

To connect Google Calendar:
1. Click:
   - `Create Credentials`
2. Sign into Google
3. Authorize calendar access

This connects N8N with Google services.

---

# 5. Configuring Calendar Events

## Event Resource Settings

Inside the Google Calendar node:

### Configuration
- Resource:
  - `Event`
- Operation:
  - `Create`

---

## Dynamic Appointment Mapping

The workflow maps:
- Appointment start time
- Appointment end time
- Patient details
- Doctor information

directly from form submission data.

---

## Calendar Automation Result

When the workflow executes:
- A calendar event is created automatically
- The doctor receives the scheduled booking
- Appointment details are stored securely

This removes the need for manual scheduling.

---

# 6. Adding a Switch Node

## Purpose of the Switch Node

The tutorial next introduces a:
- `Switch` node

This node helps manage:
- Workflow branching
- Conditional automation
- Multi-step logic handling

---

## Configuration Notes

The presenter mentions:
- No special modifications are required
- Default settings are enough

The node acts as a workflow organizer.

---

# 7. Gmail Integration

## Purpose of Email Automation

After appointment booking:
- Confirmation emails are automatically sent to patients

This improves:
- Professionalism
- Communication
- Appointment reliability

---

# 8. Adding the Gmail Node

## Setup Steps

1. Add a new node
2. Search:
   - `Gmail`
3. Select:
   - Send Email node

---

## Gmail Credential Setup

### Authentication Process
1. Create Gmail credentials
2. Sign into Google
3. Allow Gmail permissions

This connects Gmail with N8N automation.

---

# 9. Configuring Appointment Emails

## Dynamic Email Fields

The following fields are dynamically populated:
- Recipient email address
- Patient name
- Appointment timing
- Doctor details

---

## Email Subject Example

The presenter uses:
- `Medicine Reminder for [Customer Name]`

This subject line is dynamically generated.

---

## Email Body

The email body contains:
- Appointment confirmation
- Booking details
- Doctor information
- Timing reminders

The email template is available in the PDF guide.

---

## Email Format

The format is set to:
- `Text`

This ensures:
- Better deliverability
- Clean formatting
- Simple readability

---

# 10. Fixing Dynamic Data Errors

## Error Handling

The presenter explains that:
- Red error lines may appear
- These are caused by incorrect field linking

---

## Solution

Dynamic fields must be properly connected using:
- Form submission data
- Variable mapping

Example:
- Customer name field should reference the form data correctly

Once fixed:
- Errors disappear
- Emails work properly

---

# 11. Removing the N8N Watermark

## Professional Workflow Output

The presenter shows how to remove N8N branding.

### Steps
1. Open:
   - `Add Option`
2. Select:
   - `Abandon N8`

This improves presentation quality for client delivery.

---

# 12. Email Delivery Testing

## Final Test

After configuration:
1. Execute the workflow
2. Submit a form
3. Check Gmail inbox

---

## Result

The patient receives:
- Properly formatted appointment confirmation
- Dynamic booking details
- Automated reminder content

This confirms Gmail integration is successful.

---

# 13. WhatsApp Appointment Confirmation

## Adding Another WhatsApp Node

Using the Switch node:
1. Add another WhatsApp Send Message node
2. Configure appointment confirmation messaging

---

## Credential Reuse

Instead of creating new credentials:
- Existing WhatsApp credentials are duplicated

This speeds up setup.

---

## Dynamic Confirmation Messages

The confirmation message includes:
- Appointment timing
- Doctor information
- Booking confirmation
- Additional instructions

All fields are dynamically populated from form data.

---

# 14. Final WhatsApp Confirmation Testing

## Workflow Execution

After configuration:
1. Execute workflow
2. Submit appointment form
3. Observe WhatsApp reply

---

## Result

The patient receives:
- Instant appointment confirmation
- Booking details on WhatsApp
- Automated communication without manual effort

The workflow now operates end-to-end successfully.

---

# Complete Workflow Architecture

## Full Automation Flow

```text
WhatsApp Message
        ↓
JavaScript Automation
        ↓
Form Link Sent
        ↓
Form Submission
        ↓
Google Calendar Event
        ↓
Switch Node
       ↙ ↘
 Gmail    WhatsApp Confirmation

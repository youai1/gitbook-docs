---
description: Automated Scheduling Platform
---

# Calendly

## What is Calendly?

**Calendly** is a scheduling automation platform that helps individuals and teams easily book meetings without the back-and-forth of emails.

Calendly lets you share your availability via a booking link or embed it on your website. Others can pick a time that works for them, and Calendly automatically syncs it with your connected calendar (e.g., Google Calendar, Outlook, iCloud, or Office 365).

#### How It Works

1. **Set your availability** — define your working hours and meeting durations.
2. **Share your link** — send it via email, message, or embed it online.
3. **Guests pick a slot** — Calendly handles time zones and avoids double-booking.
4. **Calendar syncs automatically** — all participants receive calendar invites and reminders.

## Calendly Connector Blocks Reference

<details>

<summary>Cancel Event</summary>

This connector allows you to cancel a scheduled event in Calendly.

### How to use this connector

1. **Event UUID** - Enter the UUID of the scheduled event you want to cancel.
   * This is a unique identifier for the event
   * You can find this in the event URL (e.g., `https://calendly.com/username/meeting/01234567-89ab-cdef-0123-456789abcdef`)
   * Or retrieve it via the List Events API
2. **Cancellation Reason** (Optional) - Provide a reason for canceling the event.
   * This will be included in the cancellation notification
   * You can leave this blank if no reason is needed
3. **Output Variable** - Enter a name for the variable that will store the result of the cancellation operation.
   * This variable will contain an object with:
     * `success`: boolean indicating if the cancellation was successful
     * `message`: a descriptive message about the operation result

### Example Response

```
{
  "success": true,
  "message": "Event successfully canceled"
}
```

### Troubleshooting

* **Event Not Found (404)**: Verify the Event UUID is correct and the event exists
* **Permission Issues (403)**: Ensure your Calendly connection has permission to cancel events
* **Already Canceled**: If the event was already canceled, the connector will return a success message

</details>

<details>

<summary>Create Event Invitee</summary>

This connector creates a new event invitee in Calendly, allowing you to programmatically schedule events. When you use this connector, it will trigger standard Calendly notifications, calendar invites, and workflows as if the event was booked through the Calendly UI.

### Prerequisites

* You must have a Calendly account on a paid plan (Standard or above). Users on the Free plan will receive an error.
* Your Calendly account must be connected to MindStudio.

### Configuration

#### Event Details

* **Event Type URI**: The unique identifier for the event type you want to schedule. You can find this in your Calendly event type URL or through the Calendly API.
  * Example: `https://api.calendly.com/event_types/AAAAAAAAAAAAAAAA`
* **Start Time**: The start time of the scheduled event in UTC (ISO 8601 format).
  * Example: `2023-08-07T06:05:04Z`

#### Invitee Information

* **Name**: The full name of the person being scheduled for the event.
  * Example: `John Smith`
* **Email**: The email address of the invitee. This is where Calendly will send confirmation emails.
  * Example: `john@example.com`
* **Timezone**: The timezone of the invitee. Must be a valid IANA timezone string.
  * Example: `America/New_York`
* **Text Reminder Number** (Optional): Phone number for SMS reminders. Must be in international format.
  * Example: `+14155551234`

#### Location (Optional)

* **Location Type**: Currently supports physical locations.
* **Location Details**: The specific physical location details for the meeting.
  * Example: `123 Main St, Suite 100, New York, NY`

#### Guest Information (Optional)

* **Guest Emails**: A comma-separated list of email addresses for additional guests (maximum 10).
  * Example: `guest1@example.com, guest2@example.com`

### Output

The connector will return comprehensive information about the created event invitee, including:

* Invitee URI
* Event details
* Cancellation and rescheduling links
* Status information

This information will be stored in the variable you specify in the "Output Variable Name" field.

### Limitations

* You can add a maximum of 10 guest emails.
* This connector requires a paid Calendly plan (Standard or above).

</details>

<details>

<summary>Create Event Type</summary>

## Create Event Type

This connector creates a new event type in your Calendly account. Event types are the different meeting options that you offer to attendees (like "30 Min Meeting", "Discovery Call", etc.).

### Prerequisites

* You must have a Calendly account connected to MindStudio
* You need your Calendly Profile ID (see below for how to find it)

### Configuration

#### Event Type Details

* **Event Type Name**: The name that will be displayed to your attendees (e.g., "Discovery Call", "30-Minute Consultation")
* **Description**: Optional details about what the meeting is for
* **Color**: Optional hex color code for the event (e.g., #0088cc for blue)
* **Duration**: Length of the meeting in minutes (e.g., 15, 30, 60)

#### Scheduling Options

* **Custom URL Slug**: Optional custom part of the URL for this event type (e.g., "discovery-call")
* **Event Kind**:
  * One-on-One: Standard 1:1 meeting
  * Group: Multiple attendees can book the same slot
  * Collective: Multiple hosts attend the same meeting
  * Round Robin: Distribute meetings among team members
* **Pooling Type**: For Round Robin events, choose how to assign hosts
* **Profile ID**: Your Calendly profile ID (required)

#### Finding Your Profile ID

Your Profile ID is needed to associate the event type with your account. To find it:

1. Go to your Calendly dashboard
2. Open your browser's developer tools (F12 or right-click → Inspect)
3. Go to the Network tab
4. Refresh the page and look for requests to the Calendly API
5. Find a request that includes your profile information
6. Look for a URI like `https://api.calendly.com/profiles/XXXX` where XXXX is your profile ID

Alternatively, you can create an event type manually in Calendly, then use the Calendly API to list your event types, which will include your profile ID.

### Output

The connector will store the complete details of the created event type in your specified output variable, including the scheduling URL that you can share with attendees.

</details>

<details>

<summary>Create Invitee No Show</summary>

## Create Invitee No Show

This connector allows you to mark an invitee as a "no-show" for a scheduled Calendly event. This is useful for tracking attendance and maintaining accurate records of your meetings.

### Prerequisites

* A Calendly account with OAuth authentication set up
* The UUID of the invitee who didn't show up for the meeting

### Configuration

#### Invitee UUID

Enter the UUID of the invitee who didn't show up for the scheduled event. This is a unique identifier for the specific invitee booking.

Example format: `12345678-1234-1234-1234-123456789abc`

You can find the invitee UUID in the URL of the invitee page or from the Calendly API when listing invitees for an event.

#### Output Variable

Specify a variable name to store the result of the operation. This will contain the full response from Calendly, including confirmation that the invitee was marked as a no-show.

### What happens when this connector runs?

When executed, this connector will:

1. Send a request to the Calendly API to mark the specified invitee as a no-show
2. Return the API response with details about the created no-show record
3. Store the result in your specified output variable for use in subsequent steps

### Troubleshooting

If you encounter errors:

* Verify that the invitee UUID is correct and belongs to an actual scheduled event
* Ensure your Calendly OAuth connection is properly authenticated
* Check that the invitee hasn't already been marked as a no-show

</details>

<details>

<summary>Create One-Off Event Type</summary>

## Create One-Off Event Type

This connector creates a temporary event type in Calendly that doesn't appear in your regular event types list. One-off event types are ideal for special or limited-time meetings.

### Configuration

#### Event Type Details

* **Event Name**: The name of your event (e.g., "Sales Call", "Interview", "Product Demo")
* **Description**: Optional details about the meeting that will be shown to invitees
* **Color**: Optional hex color code for your event (e.g., `#FF0000` for red)
* **Duration**: Length of the meeting in minutes (e.g., `30` for a 30-minute meeting)

#### Scheduling Options

* **Custom URL Slug**: Optional custom URL path (letters, numbers, and hyphens only)
* **Event Kind**: Choose the meeting format:
  * One-on-One: For meetings with a single attendee
  * Group: For meetings with multiple attendees
  * Collective: For team-based scheduling
* **Location Type**: How the meeting will take place
* **Custom Location**: Required if you select "Custom Link" or "In Person" as the location type
  * For custom links: Enter the URL (e.g., `https://mycompany.com/meeting-room`)
  * For physical locations: Enter the address or meeting details

#### Availability

* **Scheduling Page ID**: The UUID of your Calendly scheduling page
  * This can be found in your Calendly URL: `https://calendly.com/your-username/event-name` (your-username is your scheduling page ID)
  * Or use a full UUID format like `ABCDEFGHIJKLMNO`

#### Output

* **Output Variable**: Name of the variable that will store the created event type details, including the scheduling URL

### Example Response

The connector will return a response that includes the event type details and scheduling URL:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/event_types/ABCDEFGHIJKLMNO",
    "name": "Sales Call",
    "scheduling_url": "https://calendly.com/your-username/sales-call-123",
    "duration": 30,
    "kind": "solo",
    "slug": "sales-call-123",
    "description": "Discuss our product offerings",
    "color": "#FF0000"
  }
}
```

You can access the scheduling URL from the output variable to share with invitees.

</details>

<details>

<summary>Create Share Link</summary>

## Create Share Link for Calendly

This connector creates a customized sharing link for a Calendly event type that you can use to schedule meetings.

### Configuration

#### Event Type Link

Enter the full URL of your Calendly event type. This is the link that you would normally share with someone to book time on your calendar.

**Example:** `https://calendly.com/johndoe/30min`

#### Max Event Count

Optionally specify the maximum number of events that can be scheduled using this share link. This is useful for limiting how many times a link can be used.

* Leave empty for unlimited bookings
* Enter a positive number (e.g., `5`) to limit the number of bookings

#### Output Variable

Specify a variable name to store the generated share link. You can use this variable in subsequent steps of your workflow.

### How It Works

1. The connector extracts the event type UUID from your Calendly event link
2. It creates a new share link with your specified parameters
3. The generated share link is stored in your specified output variable

### Example Use Cases

* Create limited-use booking links for specific clients
* Generate tracking links for marketing campaigns
* Create temporary booking links for special events

</details>

<details>

<summary>Create Single-Use Scheduling Link</summary>

## Create Single-Use Scheduling Link

This connector creates a single-use scheduling link in Calendly that can only be used once, making it ideal for one-time appointments or meetings.

### Configuration

#### Event Details

* **Event Type URL**: Enter the full URL of your Calendly event type. This is the URL you would normally share with someone to book time with you.
  * Example: `https://calendly.com/yourname/30min`
  * You can find this by going to your Calendly dashboard, selecting an event type, and copying the link.
* **Max Event Count**: The maximum number of times this link can be used.
  * Default is `1` for a true single-use link
  * You can set a higher number if you want to allow multiple bookings
* **Owner Email** (optional): The email address of the Calendly user who owns this event type.
  * Only needed if you're creating a link for someone else's calendar
  * Leave blank to use the authenticated user's calendar

#### Link Options

* **Link Expiration** (optional): Number of days until this link expires.
  * Leave empty for no expiration
  * Example: `30` for a link that expires in 30 days

#### Output

* **Output Variable**: The name of the variable where the single-use scheduling link will be stored.
  * This variable will contain the URL that you can share with someone to book a meeting

### How It Works

When this connector runs, it:

1. Creates a single-use scheduling link for the specified event type
2. Returns the unique booking URL that can only be used once
3. Stores this URL in your specified output variable

### Common Use Cases

* Sending personalized booking links to prospects
* Creating one-time consultation slots
* Generating unique meeting links for specific clients
* Automating appointment scheduling in your workflows

</details>

<details>

<summary>Create Webhook Subscription</summary>

## Create Webhook Subscription

This connector creates a new webhook subscription in Calendly. Webhooks allow you to receive real-time notifications when specific events occur in your Calendly account.

### Configuration

#### Webhook Configuration

* **Callback URL**: Enter the HTTPS URL where you want to receive webhook notifications. This must be a publicly accessible endpoint that can receive POST requests.
  * Example: `https://example.com/webhooks/calendly`
* **Events**: Enter a comma-separated list of Calendly events you want to subscribe to.
  * Common events include:
    * `invitee.created` - When someone schedules a meeting
    * `invitee.canceled` - When someone cancels a meeting
    * `routing_form.submission.created` - When a routing form is submitted
  * Example: `invitee.created,invitee.canceled`
* **Scope**: Select the scope for your webhook subscription:
  * **User**: Only receive events related to the authenticated user
  * **Organization**: Receive events for the entire organization

#### Advanced Options

* **Signing Key** (Optional): If provided, Calendly will use this key to sign the webhook payload, allowing you to verify that requests are coming from Calendly. Must be at least 16 characters.
  * Example: `your-secret-signing-key-1234`

#### Output

* **Output Variable**: Name of the variable that will store the webhook subscription details, including the subscription ID, which you'll need if you want to manage this webhook later.

### Notes

* Your callback URL must be publicly accessible and support HTTPS
* You can create multiple webhook subscriptions for different purposes
* To delete a webhook subscription, use the "Delete Webhook Subscription" connector with the webhook ID

</details>

<details>

<summary>Delete Invitee Data</summary>

## Delete Invitee Data

This connector allows you to delete an invitee's data from a scheduled event in Calendly. This is particularly useful for compliance with data privacy regulations like GDPR.

### When to use this connector

* When you need to remove a participant's data from a Calendly event
* For privacy compliance and data management
* When automating user data deletion workflows

### Required information

#### Event UUID

The unique identifier for the scheduled event. You can find this in the URL of your Calendly event or through the Calendly API.

Example: `123e4567-e89b-12d3-a456-426614174000`

#### Invitee UUID

The unique identifier for the invitee whose data you want to delete. This can be obtained from the Calendly API when listing invitees for an event.

Example: `987e6543-e21b-34d5-c678-426614174999`

### Output

When successful, the connector will output a success object to your specified variable:

```json
{
  "success": true,
  "message": "Invitee data successfully deleted"
}
```

### Notes

* This operation permanently deletes the invitee's data and cannot be undone
* You must have appropriate permissions in Calendly to delete invitee data
* The connector uses the Calendly API v2

</details>

<details>

<summary>Delete Invitee No-Show</summary>

## Delete Invitee No-Show

This connector allows you to remove the "no-show" status for an invitee in Calendly, marking them as having attended the meeting.

### When to use this connector

Use this connector when you need to:

* Mark an invitee as having attended a meeting
* Remove the "no-show" status from an invitee's record
* Update attendance records in Calendly

### Configuration

#### Invitee Information

**Invitee No-Show UUID**

* This is the unique identifier for the no-show record you want to delete
* You can find this UUID in the URL when viewing the no-show record in Calendly
* Format example: `12345678-1234-1234-1234-123456789012`

#### Response

**Success Message Variable**

* Choose a name for the variable that will store the success message
* This variable will contain confirmation when the no-show status is successfully removed

### Example Usage

This connector is useful in workflows where you need to:

* Update attendance records after confirming someone attended
* Correct mistakenly marked no-shows
* Automate attendance tracking processes

### Notes

* This action requires a valid Calendly OAuth connection
* A successful deletion returns a 204 No Content response
* If the UUID doesn't exist, you'll receive an error message

</details>

<details>

<summary>Delete Scheduled Event</summary>

## Delete Scheduled Event

This connector allows you to delete a scheduled event in Calendly.

### How to use this connector

1. Enter the **Event UUID** of the scheduled event you want to delete. This is the unique identifier for the event in Calendly.
   * Example: `01234567-89ab-cdef-0123-456789abcdef`
   * You can find the UUID in the URL of the event or from the Calendly API
2. Optionally, provide a **Reason for Cancellation** to explain why the event is being deleted.
   * This information may be shared with the invitee depending on your Calendly settings
3. Specify an **Output Variable** name to store the result of the operation.
   * The output will contain information about whether the deletion was successful

### Output format

The connector returns an object with the following structure:

```json
{
  "success": true,
  "message": "Event successfully deleted"
}
```

If an error occurs, the output will include error details:

```json
{
  "success": false,
  "message": "Error deleting event: Event not found",
  "error": {
    "status": 404,
    "details": "..."
  }
}
```

### Notes

* This connector uses the Calendly V2 API
* Deleting an event will cancel it for all invitees
* You must have permission to delete the event in your Calendly account

</details>

<details>

<summary>Delete Webhook Subscription</summary>

## Delete Webhook Subscription

This action allows you to delete an existing webhook subscription in Calendly.

### When to use this action

Use this action when you need to:

* Remove a webhook that is no longer needed
* Clean up webhook subscriptions
* Update your integration by removing old webhooks before creating new ones

### Required information

#### Webhook UUID

Enter the UUID of the webhook subscription you want to delete. This is a unique identifier for the webhook in the format:

```
00000000-0000-0000-0000-000000000000
```

You can find your webhook UUIDs by using the "List Webhook Subscriptions" action or from the Calendly developer dashboard.

#### Success Variable

Specify a variable name to store the result of the deletion operation. This variable will be set to `true` when the webhook is successfully deleted.

### What happens

When this action runs:

1. It sends a request to Calendly to delete the specified webhook subscription
2. If successful, the webhook will be permanently removed from your Calendly account
3. The success variable will be set to `true`

### Notes

* This action requires a valid Calendly OAuth connection
* Once deleted, webhooks cannot be recovered - you'll need to create a new webhook if needed
* If the webhook UUID doesn't exist, the action will return an error

</details>

<details>

<summary>Get Current User</summary>

## Get Current User

This action retrieves information about the currently authenticated Calendly user associated with your OAuth token.

### What This Action Does

When executed, this action will:

1. Make a request to the Calendly API to fetch details about the current user
2. Return comprehensive user information including name, email, timezone, and scheduling URL
3. Store the complete user profile in your specified output variable

### Configuration

#### Output Variable

Enter a name for the variable that will store the user information. You'll be able to use this variable in subsequent steps of your workflow.

### Output Data Structure

The output variable will contain a JSON object with the following structure:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST",
    "name": "John Doe",
    "slug": "john-doe",
    "email": "john.doe@example.com",
    "scheduling_url": "https://calendly.com/john-doe",
    "timezone": "America/New_York",
    "avatar_url": "https://calendly-cdn.com/uploads/user/avatar/ABCDEFGHIJKLMNOPQRST/avatar.png",
    "created_at": "2020-01-01T00:00:00.000000Z",
    "updated_at": "2023-01-01T00:00:00.000000Z"
  }
}
```

### Common Use Cases

* Retrieve user details before performing other Calendly operations
* Get the user's timezone for scheduling-related workflows
* Access the user's scheduling URL to share with others
* Verify account information as part of an authentication flow

### Requirements

* A valid Calendly OAuth connection must be established before using this action

</details>

<details>

<summary>Get Event</summary>

## Get Event - Calendly

This connector retrieves detailed information about a specific Calendly event using the Calendly API v2.

### Prerequisites

* A Calendly account with OAuth access configured
* The UUID of the Calendly event you want to retrieve

### Configuration

#### Event Configuration

* **Event UUID**: Enter the unique identifier for the Calendly event you want to retrieve. This is a required field.
  * Example: `01234567-89ab-cdef-0123-456789abcdef`
  * You can find the UUID in the URL of your Calendly event or from the Calendly dashboard

#### Output Configuration

* **Output Variable**: Specify a name for the variable that will store the event details. This variable will contain all the information about the event returned by the Calendly API.

### Output Data

The connector returns comprehensive event details including:

* Event name and description
* Start and end times
* Event location information
* Invitee details
* Event status
* Custom questions and answers
* Other event metadata

### Example Use Cases

* Retrieve event details to display in your application
* Check event status before sending reminders
* Access event information for reporting or analytics
* Integrate Calendly event data with other systems

### Troubleshooting

If you encounter errors:

* Verify the Event UUID is correct and properly formatted
* Ensure your Calendly OAuth connection is active and has the necessary permissions
* Check that the event exists and is accessible with your credentials

</details>

<details>

<summary>Get Event Invitee</summary>

## Get Event Invitee

This connector retrieves detailed information about a specific invitee for a Calendly event. It allows you to access comprehensive data about someone who has scheduled a meeting, including their contact information, responses to questions, and event details.

### Configuration

#### Event UUID

Enter the UUID of the scheduled event you want to retrieve invitee information from. This is typically found in the event URL or in previous API responses.

Example: `123e4567-e89b-12d3-a456-426614174000`

#### Invitee UUID

Enter the UUID of the specific invitee you want to retrieve information for. This identifies the particular person who scheduled the meeting.

Example: `987e6543-e21b-12d3-a456-426614174999`

#### Output Variable

Specify a variable name to store the invitee information returned by the API. This will contain all the details about the invitee, including:

* Name and email
* Status of the booking
* Scheduled time
* Responses to any custom questions
* Tracking and rescheduling information

### Usage Tips

* You can find UUIDs in Calendly URLs. For example, in the URL `https://calendly.com/username/meeting/confirmation?event_uuid=123e4567-e89b-12d3-a456-426614174000&invitee_uuid=987e6543-e21b-12d3-a456-426614174999`, the event UUID is `123e4567-e89b-12d3-a456-426614174000` and the invitee UUID is `987e6543-e21b-12d3-a456-426614174999`.
* The output can be used in subsequent steps to personalize messages or update records in other systems.

</details>

<details>

<summary>Get Event Type</summary>

## Get Event Type - Calendly

This connector retrieves detailed information about a specific Calendly event type using the Calendly API.

### Configuration

#### Event Type UUID

Enter the UUID of the event type you want to retrieve. This is a unique identifier for your Calendly event type.

**Where to find it:**

* In the URL of your event type page (e.g., `https://calendly.com/your-name/event-name` - the UUID is in the backend)
* Via the List Event Types endpoint in Calendly API
* In your Calendly dashboard under the event type settings

Example UUID format: `01234567-89ab-cdef-0123-456789abcdef`

#### Output Variable

Enter a name for the variable that will store the event type details. This variable will contain all the information about your event type, including:

* Name and description
* Duration
* Scheduling URL
* Active status
* Color and branding
* Custom questions
* Scheduling settings
* And more

### Example Response

The output will be a JSON object with detailed information about the event type:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/event_types/01234567-89ab-cdef-0123-456789abcdef",
    "name": "15 Minute Meeting",
    "description": "A brief introduction call",
    "duration": 15,
    "kind": "solo",
    "slug": "15min",
    "color": "#0088ff",
    "active": true,
    "scheduling_url": "https://calendly.com/username/15min",
    "created_at": "2023-01-01T00:00:00.000000Z",
    "updated_at": "2023-01-01T00:00:00.000000Z"
    // Additional fields will be included
  }
}
```

### Notes

* This connector uses the Calendly V2 API
* Authentication is handled automatically through your connected Calendly account

</details>

<details>

<summary>Get Group</summary>

## Get Group - Calendly

This connector retrieves detailed information about a specific Calendly group.

### Configuration

#### Group Information

* **Group UUID**: Enter the unique identifier for the Calendly group you want to retrieve information about.
  * This can be found in the URL when viewing a group in Calendly (e.g., `123e4567-e89b-12d3-a456-426614174000`)
  * Example URL format: `https://calendly.com/organizations/org_name/teams/team_id/groups/your_group_uuid`

#### Output

* **Output Variable**: Specify a name for the variable that will store the group details. This variable will contain all information returned by Calendly about the group, including:
  * Group UUID
  * Name
  * Members
  * Created and updated timestamps
  * Other group metadata

### Example Response

The output variable will contain a JSON object similar to:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/groups/ABCDE12345",
    "name": "Sales Team",
    "created_at": "2023-01-15T09:30:00.000000Z",
    "updated_at": "2023-06-20T14:45:00.000000Z"
  }
}
```

### Notes

* You must have proper permissions to access group information in your Calendly account
* If the group doesn't exist or you don't have access to it, the connector will return an appropriate error message

</details>

<details>

<summary>Get Group Relationship</summary>

## Get Group Relationship

This connector retrieves information about the relationship between a Calendly group and its members.

### What You'll Need

* **Group UUID**: The unique identifier for the Calendly group you want to retrieve relationship information for. This can be found in the URL when viewing a group in Calendly or through the Calendly API.

### Configuration

#### Group UUID

Enter the UUID of the group you want to retrieve information about. The UUID should be in the format:

```
123e4567-e89b-12d3-a456-426614174000
```

#### Output Variable

Specify a name for the variable that will store the group relationship information. This variable will contain details about the group membership, including information about users who are members of the specified group.

### Example Response

The connector will return data similar to this:

```json
{
  "collection": [
    {
      "resource": {
        "uri": "https://api.calendly.com/group_memberships/12345",
        "group": "https://api.calendly.com/organizations/ABCDE/groups/12345",
        "user": "https://api.calendly.com/users/FGHIJ",
        "role": "member",
        "created_at": "2023-01-01T00:00:00.000000Z",
        "updated_at": "2023-01-01T00:00:00.000000Z"
      }
    }
  ],
  "pagination": {
    "count": 1,
    "next_page": null,
    "previous_page": null,
    "next_page_token": null,
    "previous_page_token": null
  }
}
```

### Troubleshooting

* Make sure the Group UUID is valid and correctly formatted
* Verify that your Calendly account has access to the specified group
* Check that your Calendly integration has the necessary permissions to access group information

</details>

<details>

<summary>Get Invitee No-Show</summary>

## Get Invitee No-Show

This connector retrieves information about an invitee who did not show up for a scheduled Calendly event.

### When to use this connector

Use this connector when you need to:

* Check if an invitee was marked as a no-show
* Get details about a missed appointment
* Access no-show data for reporting or follow-up workflows

### Required inputs

#### Invitee UUID

The unique identifier for the invitee who did not show up for the scheduled event. This is a UUID format string that identifies the specific invitee record in Calendly.

Example: `12345678-1234-1234-1234-123456789012`

You can find the Invitee UUID in the Calendly dashboard or from the response of other Calendly API calls like "List Invitees".

#### Output Variable

The name of the variable where you want to store the no-show information. This variable will contain all the details returned by the Calendly API about the no-show record.

### Output

The connector will return a JSON object containing details about the invitee no-show, including:

* No-show UUID
* Invitee information
* Event information
* Created/updated timestamps
* Status information

Example output:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/invitee_no_shows/12345678-1234-1234-1234-123456789012",
    "invitee": "https://api.calendly.com/scheduled_events/ABCDEF123456/invitees/12345678-1234-1234-1234-123456789012",
    "created_at": "2023-01-01T12:00:00.000000Z",
    "updated_at": "2023-01-01T12:00:00.000000Z"
  }
}
```

### Authentication

This connector uses your Calendly OAuth token which is managed by the platform. No additional authentication steps are required.

</details>

<details>

<summary>Get Organization</summary>

## Get Organization

This connector retrieves detailed information about a Calendly organization using the Calendly API V2.

### Configuration

#### Organization UUID

Enter the UUID of the organization you want to retrieve information about. This is a unique identifier for your Calendly organization.

You can find your organization UUID:

* In your Calendly account settings
* From other Calendly API responses
* In the URL of your Calendly organization page (format: `1a2b3c4d-5e6f-7g8h-9i0j-1k2l3m4n5o6p`)

#### Output Variable

Specify a name for the variable where the organization details will be stored. This variable will contain all the information returned by the Calendly API about your organization, including:

* Organization name
* Organization slug
* Creation date
* Last update date
* Organization URI
* Other organization metadata

### Authentication

This connector uses OAuth authentication which is managed by the platform. You need to have connected your Calendly account to use this connector.

### Example Response

```json
{
  "resource": {
    "uri": "https://api.calendly.com/organizations/ABCDEFGHIJKL",
    "name": "My Organization",
    "slug": "my-organization",
    "created_at": "2020-01-01T00:00:00.000000Z",
    "updated_at": "2021-01-01T00:00:00.000000Z"
  }
}
```

</details>

<details>

<summary>Get Organization Invitation</summary>

## Get Organization Invitation

This connector retrieves detailed information about a specific organization invitation in Calendly.

### Prerequisites

* You must have a Calendly account with organization admin permissions
* The Calendly integration must be connected in MindStudio

### Configuration

#### Invitation Details

* **Invitation UUID**: Enter the unique identifier for the invitation you want to retrieve
  * This is the UUID portion of the invitation URL or can be found in the Calendly dashboard
  * Example: `0e8b4bda-25a0-4df6-a420-526dd7cffcf2`

#### Output

* **Output Variable**: Enter a name for the variable that will store the invitation details
  * Example: `invitationDetails`

### Output Format

The connector will return a JSON object containing the invitation details with the following structure:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/organization_invitations/0e8b4bda-25a0-4df6-a420-526dd7cffcf2",
    "created_at": "2023-01-01T12:00:00.000000Z",
    "email": "user@example.com",
    "organization": "https://api.calendly.com/organizations/ABCDEF",
    "status": "pending",
    "updated_at": "2023-01-01T12:00:00.000000Z",
    "user": null
  }
}
```

The `status` field will show whether the invitation is `pending`, `accepted`, or `declined`.

### Common Issues

* **404 Error**: This usually means the invitation UUID doesn't exist or has been deleted
* **401/403 Error**: Check that your Calendly integration is properly connected with the right permissions

</details>

<details>

<summary>Get Organization Membership</summary>

## Get Organization Membership

This connector retrieves detailed information about a user's membership in a Calendly organization.

### When to use this connector

Use this connector when you need to:

* Verify a user's membership status in your Calendly organization
* Check a user's role within your organization
* Retrieve details about a specific organization membership

### Required information

#### Organization Membership UUID

This is the unique identifier for the organization membership you want to retrieve. You can find this UUID:

* In the URL when viewing a user in your Calendly organization dashboard
* From the response of other Calendly API calls that list organization memberships

The UUID follows this format: `12345678-1234-1234-1234-123456789012`

#### Output Variable

Specify a name for the variable that will store the organization membership details. This variable will contain a JSON object with information such as:

* User details (name, email, etc.)
* Organization details
* User's role in the organization
* Status of the membership

### Example response

The output variable will contain data similar to this:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/organization_memberships/12345678-1234-1234-1234-123456789012",
    "role": "owner",
    "user": {
      "uri": "https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST",
      "name": "John Doe",
      "email": "john.doe@example.com"
    },
    "organization": {
      "uri": "https://api.calendly.com/organizations/ABCDEFGHIJKLMNOPQRST"
    },
    "updated_at": "2023-01-01T12:00:00.000000Z",
    "created_at": "2022-01-01T12:00:00.000000Z"
  }
}
```

### Notes

* This connector uses Calendly's V2 API
* Authentication is handled automatically through your connected Calendly account

</details>

<details>

<summary>Get Routing Form</summary>

## Get Routing Form

This connector retrieves detailed information about a specific Calendly routing form. Routing forms are questionnaires that help direct invitees to the appropriate scheduling page based on their responses.

### Configuration

#### Routing Form UUID

Enter the UUID of the routing form you want to retrieve. This is the unique identifier for the form.

The UUID is the last part of the routing form URL. For example, if your routing form URL is:

```
https://calendly.com/routing_forms/1234abcd-1234-abcd-1234-1234abcd1234
```

Then the UUID would be:

```
1234abcd-1234-abcd-1234-1234abcd1234
```

#### Output Variable

Specify a name for the variable that will store the routing form details. This variable will contain all information about the routing form including:

* Name
* Status
* Created/updated timestamps
* Questions and their options
* Routing logic
* Other metadata

### Example Response

The output will be a JSON object similar to:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/routing_forms/1234abcd-1234-abcd-1234-1234abcd1234",
    "name": "Customer Intake Form",
    "status": "active",
    "organization": "https://api.calendly.com/organizations/ABCDEFG",
    "created_at": "2023-01-01T12:00:00.000000Z",
    "updated_at": "2023-01-15T14:30:00.000000Z",
    "questions": [
      {
        "name": "What service are you interested in?",
        "type": "multi",
        "options": [
          {"value": "consulting", "label": "Consulting"},
          {"value": "training", "label": "Training"},
          {"value": "support", "label": "Technical Support"}
        ]
      }
    ]
  }
}
```

### Authentication

This connector uses your Calendly OAuth connection, which is automatically managed by MindStudio.

</details>

<details>

<summary>Get Routing Form Submission</summary>

## Get Routing Form Submission

This connector retrieves detailed information about a specific routing form submission from Calendly.

### Prerequisites

* You need to have connected your Calendly account to MindStudio
* You need to have the UUID of a routing form submission you want to retrieve

### Configuration

#### Submission UUID

Enter the unique identifier (UUID) of the routing form submission you want to retrieve. This is a string that looks like:

```
0b50d439-5855-4a91-9553-f9e301f5b56a
```

You can find this UUID in the URL when viewing a submission in Calendly, or from the response of other Calendly API calls that list submissions.

#### Output Variable

Specify a variable name to store the routing form submission details. The response will include:

* Submission ID
* Routing form ID
* Answers to questions
* Submission status
* Timestamps
* Associated resource information

### Example Usage

After configuring this connector, you can use the output variable in subsequent steps of your workflow to access the submission details. For example, if your output variable is named `submissionData`, you can access properties like:

* `submissionData.resource.id` - The submission ID
* `submissionData.resource.status` - The submission status
* `submissionData.resource.questions_and_answers` - The form responses

### Troubleshooting

If you encounter errors:

* Verify the submission UUID is correct
* Ensure your Calendly account has access to the specified submission
* Check that your Calendly OAuth connection is valid and not expired

</details>

<details>

<summary>Get Sample Webhook Data</summary>

## Get Sample Webhook Data

This connector retrieves sample webhook data from Calendly, which is useful for testing and development purposes without having to wait for actual events to occur.

### Configuration

#### Webhook Configuration

* **Webhook Event**: Choose the type of webhook event you want to see sample data for:
  * **Invitee Created**: Sample data for when someone schedules an event
  * **Invitee Canceled**: Sample data for when someone cancels a scheduled event
  * **Routing Form Submission Created**: Sample data for when someone submits a routing form

#### Output

* **Output Variable**: Enter a name for the variable that will store the sample webhook data. You can reference this variable in subsequent actions using the format `{{variableName}}`.

### What This Connector Does

This connector makes a request to Calendly's API to retrieve sample webhook data for the selected event type. The data is structured exactly as it would be in a real webhook payload, allowing you to test your integrations without waiting for actual events.

### Authentication

This connector uses OAuth authentication which is managed by the platform. Make sure you've connected your Calendly account in the Connections section before using this connector.

### Example Use Cases

* Testing webhook handlers during development
* Understanding the structure of Calendly webhook payloads
* Building and testing integrations that process Calendly events

### Note

This connector only provides sample data and does not create or modify any actual events in your Calendly account.

</details>

<details>

<summary>Get User</summary>

## Get User

This action retrieves information about the current authenticated Calendly user.

### What it does

This connector makes a request to the Calendly API to fetch details about the user associated with your connected Calendly account. The returned information includes:

* User name
* Email address
* Scheduling URL
* Timezone
* Account creation date
* Last update date
* And other account details

### Configuration

#### Output Variable

Enter a name for the variable that will store the user information. This variable will contain all the user data returned from Calendly and can be used in subsequent steps of your workflow.

### Example Response

The output variable will contain a response similar to this:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST",
    "name": "John Doe",
    "slug": "john-doe",
    "email": "john.doe@example.com",
    "scheduling_url": "https://calendly.com/john-doe",
    "timezone": "America/New_York",
    "created_at": "2020-01-01T00:00:00.000000Z",
    "updated_at": "2023-01-01T00:00:00.000000Z"
  }
}
```

### Authentication

This connector uses OAuth authentication that you've already set up when connecting your Calendly account to MindStudio.

</details>

<details>

<summary>Get User Availability Schedule</summary>

## Get User Availability Schedule

This connector retrieves a user's availability schedule from Calendly, providing details about when a specific Calendly user is available for meetings.

### Configuration

#### Schedule ID

Enter the unique identifier for the availability schedule you want to retrieve. This is typically found in the URL when viewing a schedule in Calendly or can be obtained from the Calendly API.

Example: `ABCDEFGHIJKLM`

#### Output Variable

Specify a name for the variable where the availability schedule details will be stored. This variable will contain the complete response from Calendly, including:

* Schedule resource details
* User information
* Availability rules
* Default availability rule
* Timezone information

### Usage Notes

* This connector requires a valid Calendly OAuth connection
* The schedule ID must belong to a user in your Calendly organization
* If you receive an error, verify that the schedule ID is correct and that your Calendly account has permission to view the requested schedule

### Example Response

```json
{
  "resource": {
    "uri": "https://api.calendly.com/user_availability_schedules/ABCDEFGHIJKLM",
    "name": "Working Hours",
    "user": "https://api.calendly.com/users/USERID",
    "default": true,
    "timezone": "America/New_York",
    "rules": [
      {
        "type": "wday",
        "wday": "monday",
        "intervals": [
          {
            "from": "09:00",
            "to": "17:00"
          }
        ]
      }
    ]
  }
}
```

</details>

<details>

<summary>Get Webhook Subscription</summary>

## Get Webhook Subscription

This connector retrieves detailed information about a specific webhook subscription from your Calendly account.

### Prerequisites

* You must have a Calendly account with API access
* You need to have already created webhook subscriptions in your Calendly account
* You need to know the UUID of the webhook subscription you want to retrieve

### Configuration

#### Webhook Subscription UUID

Enter the UUID of the webhook subscription you want to retrieve. This is a unique identifier in the format `00000000-0000-0000-0000-000000000000`.

Example: `123e4567-e89b-12d3-a456-426614174000`

#### Output Variable

Enter a name for the variable that will store the webhook subscription details. You can reference this variable in subsequent steps of your workflow.

Example: `webhookDetails`

### Output

The connector will return detailed information about the webhook subscription, including:

* URI
* Creation and update timestamps
* Callback URL
* Creator information
* Subscribed events
* Organization details
* Scope
* State
* User information

Example output:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/webhook_subscriptions/1234abcd-5678-efgh-9012-ijklmnopqrst",
    "created_at": "2023-01-15T09:30:00.000000Z",
    "updated_at": "2023-01-15T09:30:00.000000Z",
    "callback_url": "https://example.com/webhooks/calendly",
    "creator": "https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST",
    "events": ["invitee.created", "invitee.canceled"],
    "organization": "https://api.calendly.com/organizations/ABCDEFGHIJKLMNOPQRST",
    "scope": "https://api.calendly.com/organizations/ABCDEFGHIJKLMNOPQRST",
    "state": "active",
    "user": "https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST"
  }
}
```

</details>

<details>

<summary>Invite User to Calendly Organization</summary>

## Invite User to Calendly Organization

This action allows you to invite users to join your Calendly organization by sending an invitation email to their email address.

### Prerequisites

* You need to have an active Calendly account with organization admin privileges
* You need to know your Organization UUID (found in your Calendly organization settings)

### Configuration

#### Organization UUID

Enter the UUID of your Calendly organization. This is a unique identifier in the format:

```
00000000-0000-0000-0000-000000000000
```

You can find your Organization UUID:

1. Log in to your Calendly account
2. Go to your Organization settings
3. Look for the Organization UUID in the settings or URL

#### Email Address

Enter the email address of the person you want to invite to your organization. This should be a valid email address in the format:

```
user@example.com
```

### Advanced Options

#### Output Variable (Optional)

If you want to store the response from Calendly (which includes details about the invitation), specify a variable name here. The response will contain information such as:

* Invitation UUID
* Organization UUID
* Email address
* Status of the invitation
* Created at timestamp

### What Happens Next

When you run this action, Calendly will send an invitation email to the specified email address. The recipient will need to accept the invitation to join your organization.

</details>

<details>

<summary>List Activity Log Entries</summary>

## List Activity Log Entries

This connector retrieves activity log entries from your Calendly account, allowing you to monitor and track changes made within your organization.

### Basic Configuration

* **Count**: Specify how many results to return per page (1-100). Default is 10 if not specified.
* **Sort Order**: Choose whether to display newest entries first (`created_at:desc`) or oldest entries first (`created_at:asc`).
* **Action**: Filter by specific actions (e.g., `created`, `updated`, `deleted`).
* **Namespace**: Filter by resource type (e.g., `event_type`, `scheduling_link`, `user`).

### Advanced Filters

* **Page Token**: For pagination, use the `next_page_token` from a previous response to get the next page of results.
* **Actor User UUID**: Filter by the UUID of the user who performed the action.
* **Organization URI**: Filter by organization URI in the format `https://api.calendly.com/organizations/ORGANIZATION_UUID`.
* **Min/Max Created At**: Filter by date range using ISO 8601 format (e.g., `2023-01-01T00:00:00Z`).

### Output

The connector returns a JSON object containing:

* A collection of activity log entries
* Pagination information including links to the next page if available

### Example Response

```json
{
  "collection": [
    {
      "action": "created",
      "actor": {
        "type": "user",
        "uri": "https://api.calendly.com/users/ABCDEF123456"
      },
      "created_at": "2023-09-15T14:30:00.000000Z",
      "details": {
        "event_type_name": "30 Minute Meeting"
      },
      "namespace": "event_type",
      "organization": "https://api.calendly.com/organizations/ORGID123456",
      "resource": {
        "type": "event_type",
        "uri": "https://api.calendly.com/event_types/EVENTTYPE123456"
      },
      "uri": "https://api.calendly.com/activity_log_entries/LOGENTRY123456"
    }
  ],
  "pagination": {
    "count": 10,
    "next_page": "https://api.calendly.com/activity_log_entries?count=10&page_token=NEXTPAGETOKEN",
    "next_page_token": "NEXTPAGETOKEN",
    "previous_page": null,
    "previous_page_token": null
  }
}
```

### Notes

* This connector uses the Calendly V2 API
* Activity logs are only available for Organization-level accounts
* Historical data may be limited based on your Calendly plan

</details>

<details>

<summary>List Event Invitees</summary>

## List Event Invitees

This connector retrieves a list of invitees for a specific Calendly event. Use this to get information about people who have scheduled meetings through your Calendly event links.

### Configuration

#### Event Configuration

* **Event UUID**: Enter the UUID of the specific Calendly event for which you want to list invitees. This is the unique identifier for a scheduled event.
  * Example: `0123456789abcdef0123456789abcdef`
  * You can find this UUID in the URL of your Calendly event or from the Calendly API.

#### Pagination Options

* **Count**: The number of invitees to return per page (between 1-100). Default is 25.
* **Page Token**: For paginating through large result sets. Leave empty for the first page. For subsequent pages, use the page token returned in the previous response.

#### Output Configuration

* **Output Variable**: The name of the variable where the list of invitees will be stored. This variable will contain the full response from Calendly, including invitee details and pagination information.

### Output Format

The connector returns a JSON object containing:

```json
{
  "collection": [
    {
      "uri": "https://api.calendly.com/scheduled_events/EVENT_UUID/invitees/INVITEE_UUID",
      "status": "active",
      "name": "John Doe",
      "email": "john.doe@example.com",
      "created_at": "2023-01-01T12:00:00.000000Z",
      "updated_at": "2023-01-01T12:00:00.000000Z",
      "event": "https://api.calendly.com/scheduled_events/EVENT_UUID",
      "tracking": {
        "utm_campaign": null,
        "utm_source": null,
        "utm_medium": null,
        "utm_content": null,
        "utm_term": null
      },
      "text_reminder_number": null,
      "rescheduled": false,
      "old_invitee": null,
      "new_invitee": null,
      "cancel_url": "https://calendly.com/cancellations/CANCEL_CODE",
      "reschedule_url": "https://calendly.com/reschedulings/RESCHEDULE_CODE",
      "payment": null,
      "no_show": null
    }
    // Additional invitees...
  ],
  "pagination": {
    "count": 25,
    "next_page": "https://api.calendly.com/scheduled_events/EVENT_UUID/invitees?count=25&page_token=NEXT_PAGE_TOKEN",
    "previous_page": null,
    "next_page_token": "NEXT_PAGE_TOKEN",
    "previous_page_token": null
  }
}
```

### Common Use Cases

* Retrieve attendee information for a specific meeting
* Export meeting participant details to other systems
* Track attendance for events and webinars
* Build custom follow-up workflows based on meeting attendance

</details>

<details>

<summary>List Event Type Availability Schedules</summary>

## List Event Type Availability Schedules

This connector retrieves the availability schedules for a specific event type in Calendly. It allows you to view when a particular event type is available for scheduling.

### Configuration

#### Event Type UUID

Enter the UUID of the event type you want to retrieve availability schedules for. This is a unique identifier for your Calendly event type.

**Where to find it:** The UUID can be found in the URL of your event type in Calendly. For example, if your event type URL is:

```
https://calendly.com/your-name/meeting-type/267c5d10-9940-4f10-8f8a-d5fc332b2d6f
```

The UUID would be: `267c5d10-9940-4f10-8f8a-d5fc332b2d6f`

#### Pagination Options

**Count**

The maximum number of results to return per page. Default is 25, and the maximum allowed is 100.

**Page Token**

If you're paginating through a large set of results, you can use this field to specify which page of results to return. Leave empty for the first page. The response will include a `next_page_token` if there are more results available.

#### Output Variable

Specify a name for the variable that will store the availability schedules result. This variable will contain all the schedule information returned by the Calendly API.

### Example Response

The output will be a JSON object containing the availability schedules, similar to this:

```json
{
  "collection": [
    {
      "resource": {
        "uri": "https://api.calendly.com/availability_schedules/ABCDEFGHIJKLMNOP",
        "name": "Working Hours",
        "rules": [
          {
            "type": "wday",
            "wday": "monday",
            "intervals": [
              {
                "from": "09:00",
                "to": "17:00"
              }
            ]
          },
          {
            "type": "wday",
            "wday": "tuesday",
            "intervals": [
              {
                "from": "09:00",
                "to": "17:00"
              }
            ]
          }
        ]
      }
    }
  ],
  "pagination": {
    "count": 25,
    "next_page": null,
    "next_page_token": null,
    "previous_page": null,
    "previous_page_token": null
  }
}
```

### Notes

* This connector requires authentication with Calendly, which is handled automatically by MindStudio.
* If the event type UUID doesn't exist, you'll receive an error message.

</details>

<details>

<summary>List Event Type Available Times</summary>

## List Event Type Available Times

This connector allows you to retrieve available time slots for a specific Calendly event type within a given date range. This is useful for displaying available scheduling options programmatically in your workflow.

### Prerequisites

* A Calendly account with OAuth integration set up
* Event types created in your Calendly account

### Configuration

#### Event Type UUID

Enter the UUID of the Calendly event type you want to check availability for. This is the unique identifier for your event type.

**Where to find it:** The UUID is part of the URL when you view your event type in Calendly. For example, in the URL `https://calendly.com/your-name/30min`, you would need to find the UUID that corresponds to this event type in your Calendly dashboard or via the API.

#### Date Range

**Start Time**

The beginning of the date range to check for availability, in ISO 8601 format.

Example: `2023-12-01T00:00:00Z`

**End Time**

The end of the date range to check for availability, in ISO 8601 format.

Example: `2023-12-07T23:59:59Z`

> **Note:** The date range cannot exceed 1 month.

#### Additional Options

**Timezone (Optional)**

The IANA timezone to return available times in. If not specified, the event type's default timezone will be used.

Example: `America/New_York`, `Europe/London`, `Asia/Tokyo`

#### Output

**Output Variable**

Specify a name for the variable that will store the list of available time slots. This variable can be used in subsequent steps of your workflow.

### Output Format

The connector will return an array of available time slots in the following format:

```json
{
  "collection": [
    {
      "status": "available",
      "start_time": "2023-12-01T09:00:00Z",
      "invitees_remaining": 1
    },
    {
      "status": "available",
      "start_time": "2023-12-01T10:00:00Z",
      "invitees_remaining": 1
    }
  ]
}
```

You can access individual time slots using the output variable you specified.

</details>

<details>

<summary>List Event Type Hosts</summary>

## List Event Type Hosts

This connector retrieves all hosts associated with a specific Calendly event type.

### What You'll Need

* A Calendly account with OAuth integration set up
* The UUID of the event type you want to list hosts for

### Finding Your Event Type UUID

The Event Type UUID is a unique identifier for your Calendly event type. You can find it in the URL when viewing the event type in Calendly:

1. Log in to your Calendly account
2. Navigate to the event type you want to use
3. Look at the URL in your browser, which will look something like: `https://calendly.com/d/abc-123/my-event-name`
4. The UUID is the alphanumeric string in the URL (format: `00000000-0000-0000-0000-000000000000`)

### Output

The connector will return an array of host objects with the following structure:

```json
[
  {
    "uri": "https://api.calendly.com/users/ABCDEF123456",
    "user": {
      "uri": "https://api.calendly.com/users/ABCDEF123456",
      "name": "John Doe",
      "email": "john@example.com"
    }
  }
]
```

Each host object contains information about a user who can host the specified event type.

### Common Issues

* **404 Error**: This usually means the event type UUID doesn't exist or you don't have access to it
* **401/403 Error**: Authentication or authorization issues with your Calendly account
* **Empty Results**: The event type exists but has no hosts assigned to it

</details>

<details>

<summary>List Event Types</summary>

## List Event Types

This connector retrieves a list of event types from your Calendly account. Event types are the different meeting types you've configured in your Calendly account (like "15 Minute Meeting", "30 Minute Introduction", etc.).

### Configuration

#### Query Parameters

* **User**: The URI of the user to list event types for. If left empty, the connector will use the authenticated user.
  * Example: `https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST`
  * You can find your user ID by going to your Calendly profile settings
* **Active Status**: Filter event types by their active status
  * **All Event Types**: Return both active and inactive event types
  * **Active Only**: Return only active event types
  * **Inactive Only**: Return only inactive event types
* **Count**: The number of event types to return per page (1-100). Default is 10.
* **Page Token**: For pagination. If you received a next page token from a previous request, enter it here to get the next page of results.

#### Output

* **Output Variable**: The variable name where the results will be stored. The output will include:
  * `collection`: Array of event type objects
  * `pagination`: Information about next/previous pages

### Example Response

```json
{
  "collection": [
    {
      "uri": "https://api.calendly.com/event_types/ABCDEFGHIJKLMNOPQRST",
      "name": "15 Minute Meeting",
      "active": true,
      "description": "A brief introduction call",
      "slug": "15min",
      "color": "#0088ff",
      "duration": 15,
      "kind": "solo",
      "pooling_type": null,
      "type": "StandardEventType",
      "created_at": "2023-01-01T12:00:00.000000Z",
      "updated_at": "2023-01-01T12:00:00.000000Z",
      "internal_note": null,
      "scheduling_url": "https://calendly.com/username/15min",
      "secret": false,
      "profile": {
        "type": "User",
        "name": "John Doe",
        "owner": "https://api.calendly.com/users/ABCDEFGHIJKLMNOPQRST"
      }
    }
  ],
  "pagination": {
    "count": 1,
    "next_page": null,
    "previous_page": null,
    "next_page_token": null,
    "previous_page_token": null
  }
}
```

</details>

<details>

<summary>List Events</summary>

## List Events

This connector retrieves scheduled events from your Calendly account with optional filtering parameters.

### Configuration Options

#### Event Filters

* **Min Start Time**: Optional. Filter to include only events starting on or after this time. Use ISO 8601 format (e.g., `2023-01-01T00:00:00Z`).
* **Max Start Time**: Optional. Filter to include only events starting on or before this time. Use ISO 8601 format (e.g., `2023-12-31T23:59:59Z`).
* **Event Status**: Optional. Filter events by their status:
  * Active: Events that are currently scheduled
  * Canceled: Events that have been canceled
* **Number of Events**: Optional. Maximum number of events to return (between 1-100). Defaults to 10 if not specified.

#### Output Configuration

* **Output Variable**: Required. The name of the variable where the list of events will be stored. This variable will contain an array of event objects with details like event ID, title, start/end times, status, and location.

### Example Usage

To retrieve your 20 most recent active events:

1. Leave "Min Start Time" empty
2. Leave "Max Start Time" empty
3. Select "Active" for "Event Status"
4. Enter "20" for "Number of Events"
5. Specify an output variable name like "calendlyEvents"

### Notes

* This connector uses the Calendly API v2
* The connector requires a valid Calendly OAuth connection
* Times are in UTC timezone in ISO 8601 format

</details>

<details>

<summary>List Group Relationships</summary>

## List Group Relationships

This connector retrieves a list of users who are members of a specified Calendly group.

### Configuration

#### Group Configuration

* **Group URI**: Enter the full URI of the Calendly group for which you want to list relationships. This is the unique identifier for the group.
  * Example: `https://api.calendly.com/groups/ABCDEF123456`
  * You can find your group URI in the Calendly dashboard under Organization Settings > Groups, or by using the List Groups API endpoint.

#### Pagination Options

* **Count**: The number of results to return per page. Maximum value is 100.
  * Default: 100
  * Recommended to leave at default unless you need a smaller batch size.
* **Page Token**: For paginating through large result sets. Leave empty for the first page.
  * When processing multiple pages, use the page token returned in the previous response.

#### Output Configuration

* **Output Variable**: The name of the variable where the results will be stored.
  * The output will contain an array of group membership objects and pagination information.

### Output Format

The connector returns an object with the following structure:

```json
{
  "collection": [
    {
      "uri": "https://api.calendly.com/group_memberships/ABCDEF123456",
      "group": "https://api.calendly.com/groups/GHIJKL789012",
      "user": "https://api.calendly.com/users/MNOPQR345678",
      "created_at": "2023-01-01T12:00:00.000000Z",
      "updated_at": "2023-01-01T12:00:00.000000Z"
    },
    // Additional group memberships...
  ],
  "pagination": {
    "count": 100,
    "next_page": "https://api.calendly.com/group_memberships?count=100&page_token=NEXT_PAGE_TOKEN",
    "previous_page": null,
    "next_page_token": "NEXT_PAGE_TOKEN"
  }
}
```

### Use Cases

* Retrieve all users in a specific group for reporting or management
* Sync group membership information with other systems
* Verify user access and permissions within your organization

</details>

<details>

<summary>List Groups</summary>

## List Groups

This connector retrieves a list of groups in your Calendly organization. Groups are collections of users within an organization that can be used for scheduling, permissions, and other organizational purposes.

### Configuration

#### Query Parameters

* **Count**: The number of results to return per page (between 1 and 100). If not specified, the default is 10.
* **Page Token**: Used for pagination. Include a page token to retrieve the next page of results. Leave this empty when retrieving the first page.

#### Output

* **Output Variable**: The name of the variable where the results will be stored. This variable will contain an object with:
  * `groups`: An array of group objects from your Calendly organization
  * `pagination`: Information about pagination, including the next page token if more results are available

### Example Response

```json
{
  "groups": [
    {
      "uri": "https://api.calendly.com/organization_memberships/groups/ABCDEF123456",
      "name": "Sales Team",
      "created_at": "2023-01-15T10:00:00.000000Z",
      "updated_at": "2023-01-15T10:00:00.000000Z"
    },
    {
      "uri": "https://api.calendly.com/organization_memberships/groups/GHIJKL789012",
      "name": "Marketing Team",
      "created_at": "2023-01-20T14:30:00.000000Z",
      "updated_at": "2023-01-20T14:30:00.000000Z"
    }
  ],
  "pagination": {
    "count": 10,
    "next_page": "https://api.calendly.com/organization_memberships/groups?count=10&page_token=NEXT_PAGE_TOKEN",
    "next_page_token": "NEXT_PAGE_TOKEN",
    "previous_page": null,
    "previous_page_token": null
  }
}
```

### Notes

* This connector requires OAuth authentication, which is handled automatically by the platform.
* The maximum number of results per page is 100.
* Use the page token from the pagination information to retrieve subsequent pages of results.

</details>

<details>

<summary>List Organization Invitations</summary>

## List Organization Invitations

This connector retrieves a list of pending invitations for your Calendly organization.

### Setup

1. **Organization URI** - Enter the URI of your Calendly organization
   * Format: `https://api.calendly.com/organizations/ORGANIZATION_UUID`
   * You can find your organization UUID in your Calendly account settings or by using the Calendly API to list your organizations
2. **Pagination Options** (optional)
   * **Count**: Maximum number of results to return per page (1-100)
   * **Page Token**: Token for retrieving subsequent pages of results
     * Leave empty for the first page
     * For subsequent pages, use the `next_page_token` value from the previous response
3. **Output Variable** - Name of the variable where the results will be stored

### Output

The connector returns a JSON object containing:

```json
{
  "collection": [
    {
      "created_at": "2023-01-01T12:00:00.000000Z",
      "email": "user@example.com",
      "last_sent_at": "2023-01-01T12:00:00.000000Z",
      "organization": "https://api.calendly.com/organizations/ORGANIZATION_UUID",
      "status": "pending",
      "updated_at": "2023-01-01T12:00:00.000000Z",
      "uri": "https://api.calendly.com/organization_invitations/INVITATION_UUID",
      "user": null
    }
    // Additional invitations...
  ],
  "pagination": {
    "count": 25,
    "next_page": null,
    "next_page_token": null,
    "previous_page": null,
    "previous_page_token": null
  }
}
```

### Notes

* This connector only retrieves pending invitations
* You must have admin permissions in the organization to view invitations
* The Calendly account connected to MindStudio must have access to the specified organization

</details>

<details>

<summary>List Organization Memberships</summary>

## List Organization Memberships

This action retrieves a list of all users who are members of a specified Calendly organization.

### Configuration

#### Organization UUID

Enter the UUID of the Calendly organization you want to list memberships for. This is a required field.

Example: `123e4567-e89b-12d3-a456-426614174000`

You can find your organization UUID in the Calendly admin dashboard or by using the "List Organizations" API endpoint.

#### Count

The number of results to return per page. This is optional and defaults to 10 if not specified.

* Minimum: 1
* Maximum: 100

#### Page Token

If you're paginating through a large result set, you can include the page token from a previous response to continue listing where that request left off. This field is optional.

#### Output Variable

The name of the variable where the results will be stored. This variable will contain an object with:

* `collection`: An array of organization membership objects
* `pagination`: Information about pagination

### Example Response

```json
{
  "collection": [
    {
      "resource": {
        "uri": "https://api.calendly.com/organization_memberships/MEMBERSHIP_UUID",
        "role": "owner",
        "user": {
          "uri": "https://api.calendly.com/users/USER_UUID",
          "name": "John Doe",
          "email": "john.doe@example.com"
        },
        "organization": "https://api.calendly.com/organizations/ORGANIZATION_UUID",
        "updated_at": "2023-01-01T12:00:00.000000Z",
        "created_at": "2023-01-01T12:00:00.000000Z"
      }
    }
  ],
  "pagination": {
    "count": 10,
    "next_page": "https://api.calendly.com/organization_memberships?organization=ORGANIZATION_UUID&count=10&page_token=NEXT_PAGE_TOKEN"
  }
}
```

</details>

<details>

<summary>List Outgoing Communications</summary>

## List Outgoing Communications

This connector retrieves a list of outgoing communications from your Calendly account.

### Configuration

#### Organization URI

Enter the URI of your Calendly organization. This is required and should be in the format:

```
https://api.calendly.com/organizations/ORGANIZATION_UUID
```

You can find your organization UUID in your Calendly account settings or by using the Calendly API to list your organizations.

#### Status (Optional)

Filter communications by their current status:

* **All**: Show communications with any status
* **Pending**: Show only pending communications
* **Sent**: Show only sent communications
* **Failed**: Show only failed communications

#### Sort (Optional)

Choose how to sort the results:

* **Created (Newest First)**: Sort by creation date, newest communications first
* **Created (Oldest First)**: Sort by creation date, oldest communications first

#### Page Size (Optional)

Specify how many results to return per page (1-100). Default is 25.

#### Page Token (Optional)

For pagination, enter the token received from a previous request to get the next set of results. Leave empty for the first page.

#### Output Variable

Enter a name for the variable that will store the list of communications. This variable will contain the full response from Calendly, including the communications collection and pagination information.

### Output Format

The connector returns data in the following format:

```json
{
  "collection": [
    {
      "uri": "https://api.calendly.com/outgoing_communications/COMMUNICATION_UUID",
      "status": "sent",
      "created_at": "2023-01-01T12:00:00.000000Z",
      "updated_at": "2023-01-01T12:05:00.000000Z",
      "scheduled_at": "2023-01-01T12:00:00.000000Z",
      "organization": "https://api.calendly.com/organizations/ORGANIZATION_UUID",
      "recipient": {
        "email": "recipient@example.com",
        "name": "Recipient Name"
      },
      "template": {
        "uri": "https://api.calendly.com/communication_templates/TEMPLATE_UUID",
        "name": "Template Name"
      },
      "event": "https://api.calendly.com/scheduled_events/EVENT_UUID",
      "invitee": "https://api.calendly.com/scheduled_events/EVENT_UUID/invitees/INVITEE_UUID",
      "user": "https://api.calendly.com/users/USER_UUID"
    }
  ],
  "pagination": {
    "count": 25,
    "next_page": "https://api.calendly.com/outgoing_communications?page_token=NEXT_PAGE_TOKEN",
    "previous_page": "https://api.calendly.com/outgoing_communications?page_token=PREVIOUS_PAGE_TOKEN",
    "next_page_token": "NEXT_PAGE_TOKEN",
    "previous_page_token": "PREVIOUS_PAGE_TOKEN"
  }
}
```

</details>

<details>

<summary>List Routing Form Submissions</summary>

## List Routing Form Submissions

This action retrieves a list of submissions for a specific Calendly routing form.

### Configuration

#### Routing Form UUID

Enter the UUID of the routing form you want to retrieve submissions for. This is a required field.

Example UUID format: `81d6e1d0-a0e1-4f8c-8eaf-f50e22ba6ec7`

You can find the routing form UUID in your Calendly account or from the URL when viewing the routing form.

#### Results Per Page

Specify how many submissions to retrieve per request (between 1-100). The default is 10.

#### Sort Order

Choose how to sort the submissions:

* **Newest First**: Shows the most recent submissions first (default)
* **Oldest First**: Shows the oldest submissions first

#### Page Token

If you're implementing pagination and want to retrieve a specific page of results, enter the page token here. Leave this empty to retrieve the first page of results.

The response will include a `next_page_token` if there are more results available, which you can use for subsequent requests.

### Output

The action will return an object containing:

* `submissions`: An array of routing form submissions with their details
* `pagination`: Information about pagination, including the next page token if more results are available

Example output:

```json
{
  "submissions": [
    {
      "uri": "https://api.calendly.com/routing_form_submissions/ABCDEF123456",
      "routing_form": "https://api.calendly.com/routing_forms/81d6e1d0-a0e1-4f8c-8eaf-f50e22ba6ec7",
      "submitter": {
        "name": "John Doe",
        "email": "john@example.com"
      },
      "tracking": {
        "utm_campaign": "spring_promotion",
        "utm_source": "email"
      },
      "questions_and_answers": [
        {
          "question": "What service are you interested in?",
          "answer": "Consulting"
        }
      ],
      "result": {
        "calendly_invitee_uri": "https://api.calendly.com/scheduled_events/GHIJKL789012/invitees/MNOPQR345678"
      },
      "created_at": "2023-04-01T12:00:00.000000Z"
    }
  ],
  "pagination": {
    "next_page_token": "eyJsYXN0X2l0ZW0iOiIyMDIzLTA0LTAxVDEyOjAwOjAwLjAwMDAwMFoifQ=="
  }
}
```

</details>

<details>

<summary>List Routing Forms</summary>

## List Routing Forms

This connector retrieves a list of routing forms from your Calendly account. Routing forms allow you to direct users to specific event types based on their responses to questions.

### Configuration

#### Query Parameters

* **Count**: Specify how many routing forms to return per page (1-100). Default is 10.
* **Page Token**: Used for pagination. Leave blank for the first page, then use the token returned in the response to get subsequent pages.
* **Sort By**: Choose how to sort the results:
  * Created (newest/oldest first)
  * Updated (newest/oldest first)
  * Name (alphabetically ascending/descending)

#### Output

* **Output Variable**: The name of the variable where the results will be stored. This variable will contain the full response including:
  * `collection`: Array of routing form objects
  * `pagination`: Object with pagination details including `next_page_token` if available

### Example Response

```json
{
  "collection": [
    {
      "uri": "https://api.calendly.com/routing_forms/FORM123",
      "name": "Customer Intake Form",
      "status": "active",
      "created_at": "2023-01-15T14:30:00.000000Z",
      "updated_at": "2023-02-01T09:15:00.000000Z"
    },
    {
      "uri": "https://api.calendly.com/routing_forms/FORM456",
      "name": "Support Request Form",
      "status": "active", 
      "created_at": "2023-03-10T11:20:00.000000Z",
      "updated_at": "2023-03-15T16:45:00.000000Z"
    }
  ],
  "pagination": {
    "count": 2,
    "next_page": null,
    "next_page_token": null,
    "previous_page": null,
    "previous_page_token": null
  }
}
```

### Notes

* This connector requires authentication with your Calendly account.
* To view more details about a specific routing form, you can use the URI provided in the response.

</details>

<details>

<summary>List User Availability Schedules</summary>

## List User Availability Schedules

This connector retrieves a list of availability schedules for a specified Calendly user. Availability schedules define when a user is available for meetings.

### Configuration

#### User URI

Enter the URI of the Calendly user whose availability schedules you want to retrieve. The URI follows this format:

```
https://api.calendly.com/users/{UUID}
```

Where `{UUID}` is the unique identifier for the user.

Example:

```
https://api.calendly.com/users/ABCDEF123456
```

You can find your user UUID by:

1. Going to your Calendly account
2. Navigating to "Integrations" or "API & Webhooks" section
3. Looking for your user ID in the API documentation or settings

#### Output Variable

Specify a variable name to store the list of availability schedules. This variable will contain an array of schedule objects, each with:

* ID
* Name
* Default status
* Time zone
* Availability rules

### Example Response

The connector will return data in this format:

```json
{
  "collection": [
    {
      "resource": {
        "uri": "https://api.calendly.com/user_availability_schedules/SCHEDULE_UUID",
        "name": "Working Hours",
        "user": "https://api.calendly.com/users/USER_UUID",
        "default": true,
        "timezone": "America/New_York",
        "rules": [
          {
            "type": "wday",
            "wday": "monday",
            "intervals": [
              {
                "from": "09:00",
                "to": "17:00"
              }
            ]
          },
          // Additional rules for other days
        ]
      }
    },
    // Additional schedules
  ]
}
```

### Troubleshooting

* Ensure you have the correct User URI format
* Verify that your Calendly authentication is properly configured
* If you receive an error, check that the user exists and that you have permission to access their schedules

</details>

<details>

<summary>List User Busy Times</summary>

## List User Busy Times

This connector retrieves a list of busy times for a Calendly user within a specified date range. Use this to check when a user is unavailable for scheduling.

### Configuration

#### User Selection

* **User UUID**: Enter the UUID of the Calendly user whose busy times you want to retrieve. This is the unique identifier for the user in Calendly's system.
  * You can find this in the Calendly user profile URL. For example, in `https://calendly.com/username/meeting`, the user UUID would be associated with "username".
  * To get the actual UUID, you may need to use the Calendly API to look up the user by their username first.

#### Date Range

* **Start Time**: The beginning of the time period for which you want to check busy times.
  * Must be in ISO-8601 format: `YYYY-MM-DDThh:mm:ssZ`
  * Example: `2023-01-01T00:00:00Z` for January 1st, 2023 at midnight UTC
* **End Time**: The end of the time period for which you want to check busy times.
  * Must be in ISO-8601 format: `YYYY-MM-DDThh:mm:ssZ`
  * Example: `2023-01-31T23:59:59Z` for January 31st, 2023 at 11:59:59 PM UTC
  * The maximum range between start and end time is typically 60 days

#### Output

* **Output Variable**: Name of the variable where the busy times data will be stored.
  * The output will contain an array of busy time objects, each with start and end times.

### Example Output

```json
{
  "collection": [
    {
      "start_time": "2023-01-15T14:00:00Z",
      "end_time": "2023-01-15T14:30:00Z",
      "calendly_event_id": "ABCDEFGHIJKLMNOP",
      "external_event_id": null
    },
    {
      "start_time": "2023-01-16T09:00:00Z",
      "end_time": "2023-01-16T10:00:00Z",
      "calendly_event_id": null,
      "external_event_id": "external_123456"
    }
  ],
  "pagination": {
    "count": 2,
    "next_page": null
  }
}
```

### Notes

* The connector uses the Calendly API v2
* The date range should be reasonable (typically under 60 days) to avoid performance issues
* Times are returned in UTC timezone

</details>

<details>

<summary>List User Meeting Locations</summary>

## List User Meeting Locations

This connector retrieves a list of meeting locations for a specified Calendly user. Meeting locations are the places where a user can schedule meetings, such as Zoom, Google Meet, Microsoft Teams, or in-person locations.

### When to use this connector

Use this connector when you need to:

* Get all available meeting locations for a Calendly user
* Check what meeting platforms a user has configured
* Retrieve location details before scheduling a meeting

### Configuration

#### User UUID

Enter the UUID of the Calendly user whose meeting locations you want to retrieve. The UUID is a unique identifier for a Calendly user.

You can find a user's UUID in their Calendly profile URL. For example, in the URL `https://calendly.com/user/profile`, the UUID would be found in the user's profile settings or API section.

Example UUID format: `ABCDEFGHIJKLMNOPQRST`

#### Output Variable

Enter a name for the variable where the list of meeting locations will be stored. This variable will contain an array of location objects with details like type, location name, and other relevant information.

### Response Format

The output will be stored in the specified variable as a JSON object with a structure similar to:

```json
{
  "collection": [
    {
      "type": "zoom",
      "location": "zoom.us/meeting",
      "status": "active"
    },
    {
      "type": "google_meet",
      "location": "meet.google.com",
      "status": "active"
    },
    {
      "type": "in_person",
      "location": "123 Main Street, Suite 456",
      "status": "active"
    }
  ],
  "pagination": {
    "count": 3,
    "next_page": null
  }
}
```

### Authentication

This connector uses OAuth authentication which is handled automatically by the platform. No additional authentication configuration is required.

</details>

<details>

<summary>List Webhook Subscriptions</summary>

## List Webhook Subscriptions

This connector retrieves a list of webhook subscriptions for your Calendly organization. Webhook subscriptions notify external systems when events occur in Calendly.

### Configuration

#### Organization URL

Enter the URL of your Calendly organization. This is required to identify which organization's webhooks to retrieve.

Example format:

```
https://api.calendly.com/organizations/ABCDEF123456789
```

You can find your organization ID in the Calendly web app under Settings > Organization > General.

#### Scope (Optional)

Filter webhooks by their scope:

* **All**: Return all webhook subscriptions (default)
* **Organization**: Only return organization-scoped webhooks
* **User**: Only return user-scoped webhooks

#### Count (Optional)

Specify how many webhook subscriptions to return per page (1-100). Defaults to 10 if not specified.

#### Page Token (Optional)

If you've already retrieved some webhooks and want to get the next page of results, enter the page token from the previous response's pagination object.

#### Output Variable

Enter a name for the variable that will store the webhook subscription data. This variable will contain:

* A `collection` array with webhook subscription objects
* A `pagination` object with details for retrieving additional pages

### Example Response

```json
{
  "collection": [
    {
      "uri": "https://api.calendly.com/webhook_subscriptions/WEBHOOK_UUID",
      "callback_url": "https://your-callback-url.com/webhooks",
      "created_at": "2023-01-01T12:00:00.000000Z",
      "updated_at": "2023-01-01T12:00:00.000000Z",
      "retry_started_at": null,
      "state": "active",
      "events": ["invitee.created", "invitee.canceled"],
      "scope": "organization",
      "organization": "https://api.calendly.com/organizations/ORGANIZATION_UUID",
      "user": null,
      "creator": "https://api.calendly.com/users/USER_UUID"
    }
  ],
  "pagination": {
    "count": 1,
    "next_page": null,
    "previous_page": null,
    "next_page_token": null,
    "previous_page_token": null
  }
}
```

</details>

<details>

<summary>Remove User from Organization</summary>

## Remove User from Organization

This connector allows you to remove a member from your Calendly organization. This is useful when someone leaves your team or no longer needs access to your organization's Calendly resources.

### Required Information

#### Organization Membership UUID

You need to provide the UUID of the organization membership you want to remove. This is a unique identifier for the user's membership in your organization.

**Format example:** `12345678-1234-1234-1234-123456789abc`

You can find this UUID by:

1. Using the "List Organization Memberships" connector (if available)
2. Using the Calendly API directly: `GET https://api.calendly.com/organization_memberships`
3. Checking the URL when viewing a user in your Calendly organization settings

#### Output Variable

Specify a name for the variable that will store the result of this operation. This variable will contain a success message if the removal is completed successfully.

### What Happens When You Run This Connector

When executed, this connector will:

1. Send a request to Calendly to remove the specified user from your organization
2. The user will immediately lose access to your organization's Calendly resources
3. Store a success message in your specified output variable

### Permissions Required

You must have admin privileges in your Calendly organization to remove users. The OAuth connection used by this connector must have the appropriate scopes to manage organization memberships.

### Common Issues

* **404 Error**: This occurs if the membership UUID doesn't exist or has already been removed
* **403 Error**: This happens if your account doesn't have permission to remove users
* **401 Error**: This indicates an authentication issue with your Calendly connection

</details>

<details>

<summary>Revoke Organization Invitation</summary>

## Revoke Organization Invitation

This connector allows you to revoke a pending invitation for a user to join your Calendly organization. Once revoked, the invitation link will no longer work, and the user will not be able to join your organization with that invitation.

### Prerequisites

* You must have administrator permissions in your Calendly organization
* The invitation must be in a pending state (not yet accepted)

### Configuration

#### Invitation Details

* **Invitation UUID**: Enter the unique identifier of the invitation you want to revoke. This UUID can be found:
  * In the URL of the invitation email
  * By using the "List Organization Invitations" connector to view all pending invitations
  * In the Calendly dashboard under Organization > Members > Pending Invitations

Example UUID format: `0b42c8b5-3894-4c33-9c36-f4c3d5c5c4c0`

#### Response Configuration

* **Success Message Variable**: Enter a name for the variable that will store the success message after the invitation is revoked. You can reference this variable in subsequent steps of your workflow.

### What Happens

When this connector runs:

1. It sends a request to Calendly to revoke the specified invitation
2. If successful, the invitation is immediately invalidated
3. The success message is stored in your specified output variable

### Notes

* This action cannot be undone. Once an invitation is revoked, you'll need to send a new invitation if you want to invite the user again.
* If the invitation UUID doesn't exist or has already been accepted/revoked, the connector will return an error.

</details>

<details>

<summary>Update Event Type </summary>

## Update Event Type

This connector allows you to update an existing event type in your Calendly account. You can modify properties such as name, description, duration, color, and various booking settings.

### Prerequisites

* You need to have connected your Calendly account to MindStudio
* You need the UUID of an existing event type you want to update

### Configuration

#### Event Type Details

* **Event Type UUID**: The unique identifier for the event type you want to update. You can find this in the URL of your event type page (e.g., `https://calendly.com/your-username/event-name` - the UUID is in the API, not the URL shown here) or by using the List Event Types connector.
* **Name**: The new name for your event type (leave empty to keep current name)
* **Description**: A detailed description of your event type (leave empty to keep current description)
* **Color**: The color for your event type in hexadecimal format (e.g., `#FF0000` for red)
* **Duration**: The length of the event in minutes (e.g., `30` for a 30-minute meeting)

#### Booking Settings

* **Minimum Notice Time**: The minimum time in minutes before an event that someone can book (e.g., `60` for 1 hour)
* **Maximum Notice Time**: The maximum time in days ahead that someone can book (e.g., `60` for 60 days)
* **Secret**: Whether the event type should be secret (only accessible via direct link)
* **Kind**: The type of event (solo, group, round robin, or collective)

#### Availability Settings

* **Active**: Whether the event type is active and available for booking

#### Output

* **Output Variable**: The name of the variable where the response will be stored. This will contain the updated event type information.

### Example Response

The output variable will contain the full updated event type object, which looks similar to:

```json
{
  "resource": {
    "uri": "https://api.calendly.com/event_types/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
    "name": "Updated Meeting",
    "description": "This is an updated description",
    "duration": 30,
    "kind": "solo",
    "active": true,
    "color": "#FF0000",
    "secret": false,
    "slug": "updated-meeting",
    "scheduling_url": "https://calendly.com/username/updated-meeting"
  }
}
```

### Notes

* Only fields you provide values for will be updated; all other fields will remain unchanged
* You must provide the Event Type UUID to identify which event type to update
* The Calendly API uses V2 (V1 will be deprecated by August 27, 2025)

</details>

<details>

<summary>Update Event Type Availability</summary>

## Update Event Type Availability

This connector allows you to update the availability schedules for a Calendly event type.

### Configuration

#### Event Type UUID

Enter the UUID of the event type you want to update. This is the unique identifier for your event type and can be found in the URL when viewing the event type in Calendly.

For example, if your event type URL is:

```
https://calendly.com/d/abc-123/my-event?month=2023-11
```

The UUID would be the part after `/d/` and before the event name: `abc-123`.

#### Availability Rules

Enter a JSON array of availability rules that define when your event type is available for booking. Each rule specifies days and time intervals.

**Example formats:**

**Weekday rules** (type: "wday"):

```json
[
  {
    "type": "wday",
    "days": [1, 2, 3, 4, 5],
    "intervals": [
      { "from": "09:00", "to": "17:00" }
    ]
  }
]
```

This example makes the event available Monday through Friday (1-5) from 9 AM to 5 PM.

**Multiple time blocks per day**:

```json
[
  {
    "type": "wday",
    "days": [1, 2, 3, 4, 5],
    "intervals": [
      { "from": "09:00", "to": "12:00" },
      { "from": "13:00", "to": "17:00" }
    ]
  }
]
```

This creates a lunch break from 12 PM to 1 PM.

**Different schedules for different days**:

```json
[
  {
    "type": "wday",
    "days": [1, 3, 5],
    "intervals": [
      { "from": "09:00", "to": "17:00" }
    ]
  },
  {
    "type": "wday",
    "days": [2, 4],
    "intervals": [
      { "from": "12:00", "to": "20:00" }
    ]
  }
]
```

This sets Monday, Wednesday, Friday to 9 AM - 5 PM, and Tuesday, Thursday to 12 PM - 8 PM.

**Note**: Days are numbered 0-6, where 0 is Sunday and 6 is Saturday.

#### Output Variable

Enter a name for the variable that will store the response from Calendly.

### Notes

* This connector requires a valid Calendly OAuth connection
* You must have permission to edit the event type you're updating
* The availability rules will completely replace the existing rules for the event type

</details>


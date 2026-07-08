# Data Model: MVP RSS Reader

## Entities

### Subscription
Represents a single feed subscription entered by the user.

- **Id**: Unique identifier for the subscription in the current session or in-memory collection
- **Url**: The feed URL provided by the user
- **CreatedAt**: Optional timestamp for ordering or debugging

#### Validation Rules
- The URL MUST be present and non-empty.
- Duplicate URLs MUST be ignored within the current session.
- The app does not need to validate that the URL points to a real RSS or Atom feed for the MVP.

### SubscriptionList
Represents the active set of subscriptions visible to the user.

- **Subscriptions**: An ordered collection of Subscription entries
- **State**: In-memory only for the MVP

#### State Rules
- A new subscription is appended to the list after a successful add action.
- Empty submissions do not change the list.

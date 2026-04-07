# Domain Model

## 1. Purpose
This document defines the initial business domain of Streaming Finder.

The goal is to identify the core concepts of the system before implementing technical details.

---

## 2. Core Domain Concepts

### Title
Represents a movie or series that a user can search for.

#### Attributes
- id
- name
- type (movie | series)
- description
- releaseYear
- imageUrl

#### Notes
A Title is the main searchable entity in the system.

---

### Provider
Represents a streaming platform where a title may be available.

#### Attributes
- id
- name
- baseUrl
- logoUrl

#### Notes
Examples: Netflix, Prime Video, Disney+, Max.

---

### Availability
Represents the availability of a title on a specific provider.

#### Attributes
- id
- titleId
- providerId
- providerLink
- accessType (subscription | rent | buy) - optional for future
- region - optional for future

#### Notes
Availability connects a Title with a Provider.

---

## 3. Relationships

### Title ↔ Provider
A Title can be available on many Providers.  
A Provider can offer many Titles.

This is a many-to-many relationship.

### Availability as Association
Availability is the association entity between Title and Provider, since the relationship has its own attributes such as:
- providerLink
- region
- accessType

---

## 4. Search Perspective

From the user point of view:

- the user searches for a Title
- the system returns matching Titles
- the user selects one Title
- the system shows its Availability entries
- each Availability points to a Provider

---

## 5. Initial Domain Scope

The first version of the domain includes only:
- Titles
- Providers
- Availability

The following concepts are intentionally excluded for now:
- User
- Watchlist
- Recommendation
- Notification
- Subscription account
- Viewing history

---

## 6. Future Domain Evolution

The domain may later evolve to include:
- Region-specific availability
- User accounts
- Watchlists
- Recommendation engine
- Title popularity
- Availability sync history

---

## 7. Domain Notes

- A Title does not contain the provider data directly.
- Provider data should remain independent from Title data.
- Availability may change over time and could later require update/sync logic.
- The domain should remain simple in the first version to support fast learning and implementation.

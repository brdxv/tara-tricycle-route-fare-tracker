# TARA: Tricycle Route and Fare Tracker for Rizal Province

A web-based system that helps commuters in Rizal Province find tricycle routes, terminals, and stops, and estimate fares before they ride, while giving drivers and administrators a single, consistent reference for routes and pricing.

> Final project for **CS 13: Programming Languages**, BS Computer Science, University of Rizal System – Morong (March 2026). Team project (4 members).

## Why TARA?

Tricycle transport in many Rizal barangays is informal: routes, stops, and fares vary by terminal and are usually learned by word of mouth ("Saan sakayan?", "Magkano hanggang doon?"). Newcomers and students often overpay or take inefficient routes, and passengers and drivers sometimes disagree on fares. TARA organizes route and fare information into one transparent, searchable platform. It supports, but doesn't replace, the existing setup.

## Features

**Commuters**
- Search routes by origin and destination, with stop sequences and route details
- Interactive route map (Leaflet + OpenStreetMap)
- Fare estimator based on defined fare rules, including discounted fares
- Saved locations and search history
- Route feedback and reviews

**Administrators**
- Full CRUD management of routes, stops, and terminals
- User management (commuters, drivers, administrators)
- Reports and feedback monitoring

**Platform**
- Role-based authentication (admin, commuter, driver) with hashed passwords
- Session handling and per-role dashboards

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Maps | Leaflet, OpenStreetMap |
| Backend | PHP (mysqli) |
| Database | MySQL / MariaDB |
| Deployment config | Vercel (`vercel-php` runtime) |

## Project Structure

```text
├── index.php, login.php, register.php     # entry and auth pages
├── dashboard_admin.php / dashboard_user.php
├── routes.php, route_map.php, terminals.php, fare_estimator.php
├── manage_routes.php, manage_stops.php, manage_users.php, reports.php
├── php/                                   # form actions, auth, DB connection, sessions
├── css/, js/, assets/
└── database.sql                           # schema + seed data
```

## Running Locally

1. Install [XAMPP](https://www.apachefriends.org/) (Apache + MySQL/MariaDB).
2. Copy this folder into `htdocs/`.
3. Create a database named `tara_db` and import `database.sql`.
4. Set your DB connection through environment variables (`DB_HOST`, `DB_USER`, `DB_PASS`, `DB_NAME`) or edit `php/db_connect.php`. The default port in the file is `3307`, so change it to `3306` if your MySQL uses the standard port.
5. Open `http://localhost/<folder-name>/` in your browser.

The seed data includes a sample account with the password `password` (see `database.sql`). Change it before deploying anywhere.

## Database

Tables: `users`, `routes`, `stops`, `sessions`, `reviews`, `saved_locations`.

## Author

Developed by **Ian Kurt G. Valencia** and teammates as a course project at the University of Rizal System – Morong.

# CampusSwap

Mobile app for Universidad de los Andes students to exchange or sell course materials. Built as a team for Construcción de Aplicaciones Móviles.

## Features

- Listing materials with photos from the camera or gallery, search and sorting.
- Chat between buyer and seller, and a map to agree on a meeting point on campus.
- Exchange history, favorites, notifications and ratings after each exchange.
- Usage events sent to the back end for the analytics dashboard.
- Uses device sensors: location for meeting points, the ambient light sensor to adjust the theme, and battery level to slow down chat refreshes when the battery is low.

## Architecture

The code in `lib/` is split into layers:

- `Data`: models, data sources and repository implementations that call the back-end API.
- `Domain`: entities, use cases, business rules and strategies (for example, how listings are sorted).
- `Presentation`: screens, widgets and state management.

The database schema is in `db_context/schema.prisma` (PostgreSQL): users, materials, chat rooms and messages, exchanges, meeting points, wishlist, notifications, ratings and analytics events. Architecture diagrams are in `docs/`.

## Running

```bash
flutter pub get
flutter run --dart-define-from-file=config/development.json
```

`config/development.json` holds the back-end API endpoint.

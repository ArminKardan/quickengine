# `z` Object Documentation

The `z` object is a global utility available in the front-end environments of both `Admin Panel` and `XWebsite` platforms. It provides access to user data, multilingual variables, styles, and other contextual information required for building dynamic interfaces.

## Common Properties

### `z.crossstyles`
Contains key-value pairs to control cross-platform styling. For instance, styles for QE forms are defined here.

### `z.lang`
Provides access to language-specific key-value pairs for multilingual support. For example:
- `z.lang.hi` will be `"Hi"` when English is selected.
- `z.lang.hi` will be `"سلام"` when Persian is selected.

### `z.qestyles`
Includes styling definitions specific to QE components.

### `z.root`
Represents the root path based on the selected language:
- English → `/en`
- Persian → `/fa`

Useful for language-aware routing.

### `z.styles`
Holds CSS styles defined in `[PROJECT ROOT]/styles/styles.module.css`.

---

## User Objects

### `z.middleuser`
Contains metadata and configuration for the current service user.

#### Basic Info:
- `uid`: Unique user ID (hex string, originally an `ObjectId`)
- `name`, `image`, `email`, `phone`

#### Localization:
- `lang`: Language code (`en`, `fa`, `fr`, etc.)
- `cchar`: Country code (`US`, `UK`, etc.)
- `ccode`: Country phone code (`+1`, `+98`, etc.)
- `unit`: Currency unit (`usd`, `toman`, `usdt`, etc.)

#### Service Information:
- `status`: Service status (`approved`, `rejected`, `waiting`)
- `mongourl`: MongoDB connection string (owned by `middleuser`)
- `role`: Array of assigned roles (e.g., `["admin", "editor"]`)
- `quota`: Total quota for service usage (0 = unlimited)
- `usedquota`: Number indicating used quota
- `quotaunit`: Unit of quota measurement
- `servid`: Unique service ID
- `servsecret`: Service secret string

#### Authentication:
- `rolecheck(roles: string[])`: Returns `true` if user has any of the specified roles.
- `tempsecret.generate()`: Asynchronously generates a 6-digit MFA code.
- `tempsecret.verify(code: string)`: Verifies the 6-digit MFA code.

---

### `z.topuser`
Contains limited information about the top-level owner of the service.

- `uid`, `name`, `image`, `email`, `phone`
- `lang`, `cchar`, `ccode`, `unit`

---

### `z.enduser` (Available only on `XWebsite`)

Contains information about the visiting end-user.

- `uid`, `name`, `image`, `email`, `phone`
- `lang`, `cchar`, `ccode`, `unit`

#### Roles & Authentication (inherited from `middleuser`):
- `role`: Array of roles assigned by `middleuser`
- `rolecheck(roles: string[])`: Checks enduser role authorization
- `tempsecret.generate()`: Asynchronously generates a 6-digit MFA code
- `tempsecret.verify(code: string)`: Validates the MFA code

---

## Notes
- All user-related fields are sourced from the QE users database.
- Language codes follow standard ISO 639-1 two-letter abbreviations.
- `mongourl` differs between `middleuser` and `explore` context (`topuser`-owned).
# Timebutler for Home Assistant

[![HACS Validation](https://github.com/basti-fantasti/hacs-timebutler/actions/workflows/validate.yml/badge.svg)](https://github.com/basti-fantasti/hacs-timebutler/actions/workflows/validate.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A Home Assistant custom integration for [Timebutler](https://timebutler.com) time tracking platform. Provides sensors showing employee work status, absences, and availability.

## Features

- **Individual User Sensors** - Track each employee's current status (working, paused, vacation, sick, off)
- **Group Sensors** - Count of people working, on break, on vacation, etc.
- **Department Filtering** - Group sensors per department
- **Configurable Polling** - Adjustable update interval (1-60 minutes)

## Installation

### HACS (Recommended)

1. Open HACS in Home Assistant
2. Click the three dots menu > **Custom repositories**
3. Add URL: `https://github.com/basti-fantasti/hacs-timebutler`
4. Category: **Integration**
5. Click **Add**
6. Search for "Timebutler" and install

### Manual Installation

1. Download the `custom_components/timebutler` folder
2. Copy it to your Home Assistant `config/custom_components/` directory
3. Restart Home Assistant

## Configuration

1. Go to **Settings** > **Devices & Services**
2. Click **Add Integration**
3. Search for "Timebutler"
4. Enter your Timebutler API token
5. Configure polling interval (optional, default: 5 minutes)

## Sensors

### Individual Sensors

Each user gets a sensor: `sensor.timebutler_<username>`

**States:**
- `working` - Currently clocked in
- `paused` - On break
- `vacation` - On vacation
- `sick` - Sick leave
- `off` - Not working

**Attributes:**
- `department` - User's department
- `email` - User's email
- `status_since` - When current status started
- `absence_end` - End date of current absence (if applicable)

### Group Sensors

- `sensor.timebutler_people_working` - Count of people currently working
- `sensor.timebutler_people_on_break` - Count of people on break
- `sensor.timebutler_people_on_vacation` - Count of people on vacation

Each group sensor includes a `names` attribute with the list of people.

## Requirements

- Home Assistant 2023.1 or newer
- Timebutler account with API access
- API token from Timebutler settings

## Support

- [Report Issues](https://github.com/basti-fantasti/hacs-timebutler/issues)
- [Documentation](https://github.com/basti-fantasti/hacs-timebutler)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

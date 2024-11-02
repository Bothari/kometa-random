# Kometa Collection Visible Randomiser

This utility script is designed to work alongside [Kometa](https://github.com/kometa-team/kometa), helping you manage the visibility of your Plex collections. It enables you to turn on or off the visibility of collections in the Plex front end based on your preferences.

## Features
- Randomly select collections from specified groups and set their visibility.
- Supports user confirmation if chosen.
- Handles multiple collection YML files, ensuring collections are managed separately and correctly.
- Integrates with `cron` for scheduled updates.
- Docker image.

## Prerequisites
- Python 3.10 or higher
- `pip` for Python package management
- `cron` (for scheduling on Unix-like systems)

## Installation
1. **Clone the Repository**
   ```bash
   git clone https://github.com/bothari/kometa-random.git
   cd kometa-collection-utility```

## Configuration
Create a `config.yml` file in the root directory of the project with the following structure:

```yaml
files:
  - "path/to/your/collections1.yml"
  - "path/to/your/collections2.yml"
groups:
  _group_name: 3  # Number of collections to select from this group
  _another_group_name: 5
confirmation: true  # Set to false to disable user confirmation
schedule: "5 7 * * *"  # Cron schedule to run the script (e.g., 7:05 AM daily)
```

- files: List of paths to your Kometa collection YML files.
- groups: Specify the number of collections to select for each group (label must start with _).
- confirmation: Enable or disable user confirmation for selections.
- schedule: Cron schedule for running the script.

## Usage
# Running the Script Manually
You can run the script manually using:
```python kometa-random.py```

# Using with Docker
```docker run --rm -v $(pwd)/config.yml:/app/config.yml kometa-utility```
-	Ensure the config.yml file is properly mounted in the container.


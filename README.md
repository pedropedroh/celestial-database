# Celestial Database

Welcome to the Celestial Database project! This project is a PostgreSQL database that stores information about various celestial bodies, including galaxies, stars, planets, moons, and asteroids.

## Project Overview

The Celestial Database consists of five main tables:

- **Galaxy**: Contains information about different galaxies.
- **Star**: Contains information about stars and their respective galaxies.
- **Planet**: Contains details about planets and the stars they orbit.
- **Moon**: Stores information about moons and their respective planets.
- **Asteroid**: Contains data on various asteroids in our solar system.

## Database Structure

### Tables

1. **Galaxy**
   - `galaxy_id`: Primary key (SERIAL)
   - `name`: Name of the galaxy (VARCHAR, UNIQUE, NOT NULL)
   - `description`: Description of the galaxy (TEXT)
   - `has_life`: Indicates if the galaxy has life (BOOLEAN, NOT NULL)
   - `age_in_millions_of_years`: Age of the galaxy (INT, NOT NULL)
   - `distance_from_earth`: Distance from Earth (NUMERIC)

2. **Star**
   - `star_id`: Primary key (SERIAL)
   - `name`: Name of the star (VARCHAR, UNIQUE, NOT NULL)
   - `galaxy_id`: Foreign key referencing `galaxy` (INT, NOT NULL)
   - `brightness`: Brightness of the star (NUMERIC, NOT NULL)
   - `temperature`: Temperature of the star (INT, NOT NULL)
   - `has_planets`: Indicates if the star has planets (BOOLEAN, NOT NULL)

3. **Planet**
   - `planet_id`: Primary key (SERIAL)
   - `name`: Name of the planet (VARCHAR, UNIQUE, NOT NULL)
   - `star_id`: Foreign key referencing `star` (INT, NOT NULL)
   - `has_life`: Indicates if the planet has life (BOOLEAN, NOT NULL)
   - `diameter`: Diameter of the planet (NUMERIC, NOT NULL)
   - `age_in_millions_of_years`: Age of the planet (INT, NOT NULL)

4. **Moon**
   - `moon_id`: Primary key (SERIAL)
   - `name`: Name of the moon (VARCHAR, UNIQUE, NOT NULL)
   - `planet_id`: Foreign key referencing `planet` (INT, NOT NULL)
   - `has_atmosphere`: Indicates if the moon has an atmosphere (BOOLEAN, NOT NULL)
   - `distance_from_planet`: Distance from the planet (NUMERIC, NOT NULL)
   - `orbit_period`: Orbit period of the moon (INT, NOT NULL)

5. **Asteroid**
   - `asteroid_id`: Primary key (SERIAL)
   - `name`: Name of the asteroid (VARCHAR, UNIQUE, NOT NULL)
   - `diameter`: Diameter of the asteroid (NUMERIC, NOT NULL)
   - `has_life`: Indicates if the asteroid has life (BOOLEAN, NOT NULL)
   - `distance_from_earth`: Distance from Earth (NUMERIC, NOT NULL)
   - `orbit_period`: Orbit period of the asteroid (INT, NOT NULL)

## Installation

To set up the database, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/pedropedroh/celestial-database.git
   cd celestial-database

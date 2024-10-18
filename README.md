## Project Summary

Here's a summary of the schema and its tables for the `famous_paintings` database:

1. **`style`**:
   - Stores different painting styles.
   - Columns: 
     - `style_id` (Primary Key, auto-incrementing)
     - `style_name` (Unique)

2. **`artists`**:
   - Stores information about artists.
   - Columns: 
     - `artist_id` (Primary Key)
     - `full_name`, `first_name`, `middle_name`, `last_name`, `nationality`
     - `style_id` (Foreign Key to `style`)
     - `birth_year`, `death_year`

3. **`canavas_size`**:
   - Stores canvas dimensions for paintings.
   - Columns: 
     - `size_id` (Primary Key)
     - `width`, `height`, `label`

4. **`museum`**:
   - Stores information about museums.
   - Columns: 
     - `museum_id` (Primary Key)
     - `name`, `address`, `city`, `state`, `postal`, `country`, `phone`, `url`

5. **`museum_hours`**:
   - Stores the opening hours of museums.
   - Columns: 
     - `museum_hours_id` (Primary Key, auto-incrementing)
     - `museum_id` (Foreign Key to `museum`)
     - `day`, `opentime`, `closetime`

6. **`work`**:
   - Stores information about individual artworks.
   - Columns: 
     - `work_id` (Primary Key)
     - `name`
     - `artist_id` (Foreign Key to `artists`)
     - `style_id` (Foreign Key to `style`)
     - `museum_id` (Foreign Key to `museum`)

7. **`products`**:
   - Stores information about products for sale based on artworks.
   - Columns: 
     - `product_id` (Primary Key, auto-incrementing)
     - `work_id` (Foreign Key to `work`)
     - `size_id` (Foreign Key to `canavas_size`)
     - `sale_price`, `regular_price`

This schema structures information about paintings, artists, museums, and the artworks sold as products, ensuring relationships between these entities with foreign keys.

**Recipe_Organisations**  
  
CREATE TABLE recipe_organisations (

    recipe_id INT,                              -- Recipe ID to link the recipe

    category VARCHAR(255) NOT NULL,            -- Category of the recipe (e.g., "Dessert", "Main course")

    rating DECIMAL(3,2) NOT NULL,                -- Rating of the recipe, can be up to 5.00

    PRIMARY KEY (recipe_id),                     -- Primary key is recipe_id

    FOREIGN KEY (recipe_id) REFERENCES recipe_management(recipe_id) -- Foreign key constraint

    ON DELETE CASCADE                    -- If the recipe is deleted, the record here is also deleted );

**desc recipe_organisations;**  
  
![](file:///C:/Users/z046771/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

--------------------------------------------------------------------------------------------------------------------------------------

**Recipe_Cooking**

CREATE TABLE recipe_cooking (

    recipe_id INT,                              -- Recipe ID referencing the recipe

    recipe_name VARCHAR(255) NOT NULL,           -- Name of the recipe

    recipe_instruction TEXT NOT NULL,           -- Detailed instructions for cooking

    timer INT NOT NULL,                         -- Cooking time in minutes

    PRIMARY KEY (recipe_id),                    -- Primary key is the recipe_id

    FOREIGN KEY (recipe_id) REFERENCES recipe_management(recipe_id) -- Foreign key constraint

    ON DELETE CASCADE,                          -- If the recipe is deleted, cascade the deletion here

    CONSTRAINT unique_recipe_instruction UNIQUE (recipe_id, recipe_name) -- Ensure unique combination

);

**desc recipe_cooking;**

![](file:///C:/Users/z046771/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

**Recipe_Management**

CREATE TABLE recipe_management (

    recipe_id INT AUTO_INCREMENT PRIMARY KEY,  -- Unique ID for each recipe

    recipe_name VARCHAR(255) NOT NULL,         -- Name of the recipe

    recipe_ingredients TEXT NOT NULL,          -- Ingredients required for the recipe

    CONSTRAINT unique_recipe_name UNIQUE (recipe_name)  -- Ensure no duplicate recipe names

);

**desc recipe_management;**

![](file:///C:/Users/z046771/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

TABLE RELATIONSHIP DIAGRAM (ER DIAGRAM)

![](file:///C:/Users/z046771/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)
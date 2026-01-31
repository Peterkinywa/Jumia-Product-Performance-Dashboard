# Jumia-Product-Performance-Dashboard
The objective of this project is to design and build an interactive Excel dashboard that analyzes the performance of products listed on Jumia. I explored how pricing, discounts, reviews and ratings influence product performance and customer engagement. The final dashboard supports data-driven decision-making in an e-commerce context.

## Data Cleaning and Preparation
- Checked for/and handled missing values, especially in the Reviews (replaced missing reviews with 0) and Rating columns (replaced mssing values with Not Provided)
- Identified and removed duplicate product entries from the product column.
- Converted price columns into numeric format by removing “KSh” (Used find and replace).
- Ensured the Discount column is numeric and properly formatted as a percentage.
- Converted the Rating column from text format (e.g. “4.5 out of 5”) to numeric values 4.5, 3.8, 2.9 etc
- Converted negative reviews to positive

## Data Enrichment
Created the below columns and calculated the values based on the below formulas:
- Discount Amount (KSh) - `=C21-B21`

- Rating Category - `=IF(F21="Not Provided","N/A",IF(F21<3,"Poor Rating",IF(F21<=4.4,"Average Rating",IF(F21>=4.5,"Excellent Rating"))))`

- Discount Category - `=IF(D21<20%,"Low Discount",IF(D21<=40%,"Medium Discount","High Discount"))`

- Current price range - `=IF(B21<800,"Low Priced Product",IF(B21<2500,"Medium Priced Product",IF(B21>=2500,"High Value Product")))
`

## Data Analysis
#### Descriptive Analysis
1.  Average current price, old price, discount percentage and rating
| Metric                       | Value                |
|----------------------------- |----------------------|
| Average current price        |   `KES 1,208.26`     |
| Average old price            |   `KES 1,837.75`     |
| Average discount percentage  |   `36.3169%`         |
| Average rating               |   `3.889473684`      |

2. Most expensive product - 32PCS Portable Cordless Drill Set With Cyclic Battery Drive -26 Variable Speed
   Least expensive product - 3PCS Single Head Knitting Crochet Sweater Needle Set
   
3. Average rating and discount by discount category

4. Products distribution across rating categories

### Trend and Relationship Analysis 
1. Relationship between discount percentage and number of reviews
2. Relationship between rating and number of reviews
3. Whether higher discounts lead to increased customer engagement
4. Whether higher-rated products tend to have more reviews

### Product Performance Analysis

1. Top 10 products with the highest discounts

| Product                                                                      | Discount percentage |
|------------------------------------------------------------------------------|---------------------|
| 6 In 1 Bottle Can Opener Multifunctional Easy Opener                         |     64%             |
| Creative Owl Shape Keychain Black                                            |     61%             |
| 5-PCS Stainless Steel Cooking Pot Set With Steamed Slices                    |     55%             |
| LASA FOLDING TABLE SERVING STAND                                             |     55%             |
| LASA 3 Tier Bamboo Shoe Bench Storage Shelf                                  |     54%             |
| Mythco 120COB Solar Wall Ligt With Motion Sensor And Remote Control 3 Modes  |     54%             |
| Classic Black Cat Cotton Hemp Pillow Case For Home Car                       |     53%             |
| 3PCS Single Head Knitting Crochet Sweater Needle Set                         |     53%             |
| Intelligent  LED Body Sensor Wireless Lighting Night Light USB               |     52%             |
| Exfoliate And Exfoliate Face Towel - Black                                   |     52%             |

2. Top 10 products with the most reviews

| Product                                                                      |  No. of reviews     |
|------------------------------------------------------------------------------|---------------------|
| 120W Cordless Vacuum Cleaners Handheld Electric Vacuum Cleaner               |     69              |
| 137 Pieces Cake Decorating Tool Set Baking Supplies                          |     55              |
| Electronic Digital Display Vernier Caliper                                   |     49              |
| 3D Waterproof EVA Plastic Shower Curtain 1.8*2Mtrs                           |     44              |
| 100 Pcs Crochet Hook Tool Set Knitting Hook Set With Box                     |     39              |
| Punch-free Great Load Bearing Bathroom Storage Rack Wall Shelf-White         |     36              |
| 53 Pieces/Set Yarn Knitting Crochet Hooks With Bag - Pansies                 |     32              |
| Portable Mini Cordless Car Vacuum Cleaner - Blue                             |     24              |
| 53Pcs/Set Yarn Knitting Crochet Hooks With Bag - Fortune Cat                 |     20              |
| 52 Pieces Cake Decorating Tool Set Gift Kit Baking Supplies                  |     20              |

3. Top 5 highest-rated and bottom 5 lowest-rated products
| Product                                                                          |   Rating           |
|----------------------------------------------------------------------------------|--------------------|
| Classic Black Cat Cotton Hemp Pillow Case For Home Car                           |     5              |
| LASA Aluminum Folding Truck Hand Cart - 68kg Max                                 |     5              |
| Konka Healty Electric Kettle, 24-hour Heat Preservation,1.5L,800W, White         |     5              |
| Anti-Skid Absorbent Insulation Coaster  For Home Office                          |     5              |
| Peacock  Throw Pillow Cushion Case For Home Car                                  |     5              |

| Product                                                                             |   Rating             |
|-------------------------------------------------------------------------------------|----------------------|
| 7-piece Set Of Storage Bags, Travel Storage Bags, Shoe Bags                         |     2.2              |
| Artificial Potted Flowers Room Decorative Flowers (2 Pieces)                        |     2.2              |
| 5-PCS Stainless Steel Cooking Pot Set With Steamed Slices                           |     2.1              |
| Electric LED UV Mosquito Killer Lamp, Outdoor/Indoor Fly Killer Trap Light -USB     |     2.1              |
| Wall-mounted Sticker Punch-free Plug Fixer                                          |     2.0              |

4. A comparison between high-discount and low-discount products based on average rating and number of reviews
| Discount category      | Average rating     | No. of reviews |
| -----------------------|--------------------|----------------|
| High Discount          |     3.613          |  59            |
| Low Discount           |     3.725          |  18            |

Intepretation: High-discount products generate greater customer engagement through increased reviews while low-discount products achieve slightly higher customer satisfaction as reflected in better average ratings.

## Dashboard Design  

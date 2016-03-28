1) What do you think each column means? What do you think each row means?

Each row is an item of an order made at Chipotle, sometimes with multiple items belonging to the same order (hence the repeating order_ids). Each column describes an aspect of the item, with choice_description listing the different ingredients the customer requested in the respective order.

    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ head chipotle.tsv
    order_id        quantity        item_name       choice_description      item_price
    1       1       Chips and Fresh Tomato Salsa    NULL    $2.39
    1       1       Izze    [Clementine]    $3.39
    1       1       Nantucket Nectar        [Apple] $3.39
    1       1       Chips and Tomatillo-Green Chili Salsa   NULL    $2.39
    2       2       Chicken Bowl    [Tomatillo-Red Chili Salsa (Hot), [Black Beans, Rice, Cheese, Sour Cream]]      $16.98
    3       1       Chicken Bowl    [Fresh Tomato Salsa (Mild), [Rice, Cheese, Sour Cream, Guacamole, Lettuce]]     $10.98
    3       1       Side of Chips   NULL    $1.69
    4       1       Steak Burrito   [Tomatillo Red Chili Salsa, [Fajita Vegetables, Black Beans, Pinto Beans, Cheese, Sour Cream, Guacamole, Lettuce]]   $11.75
    4       1       Steak Soft Tacos        [Tomatillo Green Chili Salsa, [Pinto Beans, Cheese, Sour Cream, Lettuce]]       $9.25

    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ tail chipotle.tsv
    1831    1       Carnitas Bowl   [Fresh Tomato Salsa, [Fajita Vegetables, Rice, Black Beans, Cheese, Sour Cream, Lettuce]]       $9.25
    1831    1       Chips   NULL    $2.15
    1831    1       Bottled Water   NULL    $1.50
    1832    1       Chicken Soft Tacos      [Fresh Tomato Salsa, [Rice, Cheese, Sour Cream]]        $8.75
    1832    1       Chips and Guacamole     NULL    $4.45
    1833    1       Steak Burrito   [Fresh Tomato Salsa, [Rice, Black Beans, Sour Cream, Cheese, Lettuce, Guacamole]]       $11.75
    1833    1       Steak Burrito   [Fresh Tomato Salsa, [Rice, Sour Cream, Cheese, Lettuce, Guacamole]]    $11.75
    1834    1       Chicken Salad Bowl      [Fresh Tomato Salsa, [Fajita Vegetables, Pinto Beans, Guacamole, Lettuce]]      $11.25
    1834    1       Chicken Salad Bowl      [Fresh Tomato Salsa, [Fajita Vegetables, Lettuce]]      $8.75
    1834    1       Chicken Salad Bowl      [Fresh Tomato Salsa, [Fajita Vegetables, Pinto Beans, Lettuce]] $8.75
    

2) How many orders do there appear to be?
 
1834.


3) How many lines are in this file?

4623.

    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ wc -l chipotle.tsv
    4623 chipotle.tsv


4) Which burrito is more popular, steak or chicken?

Chicken.

    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ grep -i steak chipotle.tsv | wc -l
    706
    
    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ grep -i chicken chipotle.tsv | wc -l
    1565


5) Do chicken burritos more often have black beans or pinto beans?

More often black beans.

    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ grep -i 'chicken.*black' chipotle.tsv | wc -l
    759
    
    MONOLITH@MONOLITH-PC MINGW64 ~/Desktop/GA DATA SCI/GA-SEA-DAT2/data (master)
    $ grep -i 'chicken.*pinto' chipotle.tsv | wc -l
    265


6) Make a list of all of the CSV or TSV files in the GA-SEA-DAT1 repo (using a single command). 

    Rachel@Elphaba MINGW64 ~/desktop/GA Data Science
    $ find GA-SEA-DAT2/ -name *.tsv | find GA-SEA-DAT2/ -name *.csv
    GA-SEA-DAT2/data/airlines.csv
    GA-SEA-DAT2/data/Airline_on_time_west_coast.csv
    GA-SEA-DAT2/data/bank-additional.csv
    GA-SEA-DAT2/data/bikeshare.csv
    GA-SEA-DAT2/data/citibike_feb2014.csv
    GA-SEA-DAT2/data/drinks.csv
    GA-SEA-DAT2/data/drones.csv
    GA-SEA-DAT2/data/hitters.csv
    GA-SEA-DAT2/data/icecream.csv
    GA-SEA-DAT2/data/imdb_1000.csv
    GA-SEA-DAT2/data/mtcars.csv
    GA-SEA-DAT2/data/NBA_players_2015.csv
    GA-SEA-DAT2/data/ozone.csv
    GA-SEA-DAT2/data/pronto_cycle_share/2015_station_data.csv
    GA-SEA-DAT2/data/pronto_cycle_share/2015_trip_data.csv
    GA-SEA-DAT2/data/pronto_cycle_share/2015_weather_data.csv
    GA-SEA-DAT2/data/syria.csv
    GA-SEA-DAT2/data/titanic.csv
    GA-SEA-DAT2/data/ufo.csv
    GA-SEA-DAT2/data/vehicles_test.csv
    GA-SEA-DAT2/data/vehicles_train.csv
    GA-SEA-DAT2/data/yelp.csv


7) Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files in the GA-SEA-DAT1 repo.

    Rachel@Elphaba MINGW64 ~/desktop/GA Data Science/GA-SEA-DAT2 (master)
    $ grep -ri 'dictionary' | wc -w
    1227

Optional) Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!

Chips and Guacamole (as a singular item) are about as popular as vegetarian entrees.

    Rachel@Elphaba MINGW64 ~/desktop/GA Data Science/GA-SEA-DAT2/data (master)
    $ grep -i 'chips and guacamole' chipotle.tsv | wc -l
    479
    
    Rachel@Elphaba MINGW64 ~/desktop/GA Data Science/GA-SEA-DAT2/data (master)
    $ grep -i 'veggie' chipotle.tsv | wc -l
    477

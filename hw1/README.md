# ga-data9-hw-1
General Assembly Data Science 9 Homework Number 1


## Exploratory Exploratory Analysis of File [ chipotle.tsv ]


#### 1: Column Description
head -n1 chipotle.tsv
order_id quantity item_name item_choices item_price


#### 2: Row Description
head -n10 chipotle.tsv
tail -n10 chipotle.tsv
Each row represents an order


#### 3: Total number of orders
wc -l chipotle.tsv = 4623 - 1: 4622


#### 4: Total number of lines in file
wc -l chipotle.tsv = 4623: 4623


#### 5: Most popular Burrito (Chicken or Steak)
First Up: Chicken

grep "Chicken Burrito" chipotle.tsv | grep "1\tChic" | wc -l = 521 * 1 = 521

grep "Chicken Burrito" chipotle.tsv | grep "2\tChic" | wc -l = 28  * 2 =  56

grep "Chicken Burrito" chipotle.tsv | grep "3\tChic" | wc -l = 2   * 3 =   6

grep "Chicken Burrito" chipotle.tsv | grep "4\tChic" | wc -l = 2   * 4 =   8

Total: 591



Next Up: Steak

grep "Steak Burrito" chipotle.tsv | grep "1\tStea" | wc -l = 352 * 1 = 352

grep "Steak Burrito" chipotle.tsv | grep "2\tStea" | wc -l = 14  * 2 =  28

grep "Steak Burrito" chipotle.tsv | grep "3\tStea" | wc -l = 2   * 3 =   6

Total: 386

Most Popular Burrito is Chicken


#### 6: In Chicken Burritos, Pinto Beans or Black Beans

grep 'Chicken Burrito' chipotle.tsv | grep 'Black Beans' | wc -l = 282

grep 'Chicken Burrito' chipotle.tsv | grep 'Pinto Beans' | wc -l = 105

Most Popular Bean in Chicken Burritos are Black Beans


#### 7: Number of occurrences of the word 'dictionary' in DAT9 rep

grep -ir "dictionary" . = 2



#### 8: Interesting Information about chipotle.tsv

grep 'Guacamole' chipotle.tsv | grep 'Steak' | wc -l    = 257

grep 'Guacamole' chipotle.tsv | grep 'Chicken' | wc -l  = 557

grep 'Guacamole' chipotle.tsv | grep 'Carnitas' | wc -l = 60

grep 'Guacamole' chipotle.tsv | grep 'Barb' | wc -l     = 69

Guacamole is paired more often with Chicken items

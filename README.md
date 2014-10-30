Costing-API
===========
This readme is mostly for my own benefit. If this idea sounds interesting, then by all means jump in.

//Personal tirade: My culinary school ripped me off. They barely taught me how to cook and never emphasised basic business skills. Pitching a new dish should be viewed the same as a presentation in any corporate meeting. You need estimates on cost, profit, expected sales, a path to implementation, etc. Walking a user through this program ensures they create the bare minimum that is expected by chefs, restaraunt groups, hotel groups, etc.//

The conundrum that I'm going to address is one that vexed me for the first 2 years of my career. "How do I make a dish that will be put on a menu?" Most of the time, the dish is poorly presented.

The web API will be simple, it walks you through multiple steps, one at a time, to help refine a dish into a professional presentation.

1) Conceptualize the dish

Ask the user to name the dish. This is the name of the file.
Ask the user for expected_food_cost.

2) Estimate a cost

Ask user for the number of components in the dish. Name each component.
Create a recipe_card for each component
recipe_card has values [name_of_ingredient, unit, number_of_units, unit_cost]

Only the last two values are used in the algorithm. Sum the products of the final 2 units for all ingredients in a recipe card. Then sum all the recipe cards together. This value is the actual_cost for the dish.

Prompt the user for a pricepoint (pp)
actual_cost / pp = estimated_food_cost_percentage

estimated_food_cost_percentage <= estimated_food_cost_percentage.

If true then skip step 3.
If false then step 3

3) Loop back to the start of step 2 until estimated_food_cost_percentage <= estimated_food_cost_percentage


Crazy things to attempt to implement at a later time:
Suggestions for lower cost ingredients based on "The Flavor Bible"
Access to online databases of multiple vendors. Easy comparison of prices.


4) Estimate labor cost for Production

For every recipe provided in step 2 or 3, prompt user for yield and time_to_cook. Also prompt for wage.
calculate time_to_cook/yield and add all the recipes together. conveert time value to hours and multiply by wage
display the individual recipe times and labor cost as a table with the total at the bottom
Ask user if they want to alter yield or wage. Then move to step 5

5) Estimate time cost for Pickup

Ask user for a pick_time.

Ask user for an order of operations (ooo). Allow for multiple variables in each "step". Ask for a time value for every operation entered. For operations in the same step, drop all but the highest value.

Example

1) Heat two pans
2) Sear Fish
2) Saute Veggies

Very basic, but the takeaway is cooks are often expected to perform multiple functions at once.  
P = pickup_time = sum_of_all_time_values
 if P <= pick_time
 then step six
 if P > pick_time
 print warning
 then step six


Enough learning material, back to the meta-idea.

P <= 8 minutes


6) mis en plas map

This is totally out of my league, which means I'll be tackling the end first.

User is provided a playground. There are images of standard containers found in a kitchen: squeze bottles, 9-pans, third-pans, etc.

User assigns a container to each recipe_card. User can now drag and drop those images of containers around a field to visually organize the mis en plas. User can hit "next" at any time. This part can be left blank if wanted.

7) Wrapping it up

Print the steps reverse order
1)mep_map
2)ooo and labor costs (for both P and R)
3)each recipe_card on a different page
4)a summary page including name, estimated_labor_cost, estimated_food_cost

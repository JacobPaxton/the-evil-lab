# Overview
I want to learn how to cook and start cooking, but I want to do it in a kinda nerdy way.

# Thoughts
There's probably something that already exists for this, but I'd like to build one.

An app, or some kind of interface, that:

1. pieces together the ingredients you have and available recipes for those ingredients
2. knows recipes that are an ingredient or two away from what you have, and suggests some purchases
3. can pick a recipe for you based on the occasion and your ingredients (breakfast, snack, party, etc)
4. sources (and ranks!) recipes from popular cookbooks based on some magic
5. can track what you've cooked (and liked/disliked), what you want to cook, etc with a per-recipe button
6. will suggest recipes to avoid soon-to-expire ingredients
7. will track ingredient purchase date and figure out the expected expiration date (in lieu of one)

Essentially this is a database project with cookbook scraping.

- ingredients you have: your_ingredients database table additions/deletions
- recipes: name, ingredients, occasion (one-hot? keyed?), cookbook references, number of references found
- available recipes for your ingredients: any recipe with 'ingredients' value entirely found in your_ingredients table
- one-more-ingredient: recipes that match your_ingredients except for one value
- pick a recipe: randomly select from available recipes + occasion via querying
- recipe sourcing: download cookbooks, scrape recipes into database, avoid repeat entries
- tracking: another database table with additions via one-click
- recipe suggestion based on expiry: your_ingredients, search soonest-expiring, look for available recipes with that ingredient(s)
- expected expiry: no clue. magic? probably scraping.
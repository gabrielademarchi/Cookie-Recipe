# Cookie-Recipe

A perfect chocolate chip cookie (CCC) is an understated wonder. Picture it: the blend of textures and the aroma, a one-way ticket to Grandma's house. But with so many recipes online, each one claiming that they are “the best”, how do we choose the one that will give us that burst of comfort in just one bite?
In another chapter of "sisters who code to find answers to the most random stuff", my sister Daniela Demarchi and I get our hands dirty where generative AI merges with the delicious world of baking, mixing chocolate chips and bayesian averages for an unanticipated twist.

**The Data**

The hardest part of this project, as is usually the case, was obtaining and cleaning the data. Equipped with oven mitts and data science, we scraped allrecipes.com for as many chocolate chip cookie recipes links as we could get our hands on. For each link, our algorithm extracted recipe details, such as ratings, number of reviews and ingredients. In the data cleaning phase, we refined the dataset, removing entries without ratings and filtering out recipes that weren't exactly for a CCC (e.g. chocolate chip cookie flavored pie).

**The Ranking**

Creating a meaningful ranking strategy based on ratings can be challenging. Which recipe is better: the one with 1000 4-star reviews or the one with a 5-star score but only 100 reviews? 
This is where the Bayesian average steps in. In simple terms, it helps us make sense of the reviews, ensuring that a recipe's score isn't disproportionately influenced by a small number of enthusiastic or critical reviews. It's a practical tool that gives us a clearer picture of a recipe's reliability.
Here's the formula at play:

*Bayesian_Average = (R * v + C * m) / (v + m)*

In this equation:<br />
R is the rating of the recipe.<br />
v is the number of reviews the recipe has received.<br />
C is a constant, representing the average rating across all recipes.<br />
m is a parameter, a sort of smoothing factor, preventing extreme values from having too much influence.<br />
By incorporating the number of reviews and considering a baseline average rating, the Bayesian average gives a more reliable score. 

**The Model**

With our data prepared, we finally reached the model. We employed OpenAI's API to learn from the selected recipes, their ingredients, quantities, and Bayesian ratings to generate a new best possible recipe.
The result was something we hadn't considered before: adding pretzels to our chocolate chip cookies. Quite the surprise, especially in a Brazilian kitchen where those twists aren't the norm. But we were definitely up for trying it out! So, we rolled up our sleeves and put our code to the test in the kitchen.
At this stage, we also replaced special fraction characters, such as "½", with floats, adding to the previous integer if necessary (so “2 ½” would turn into 2.5). This was necessary to ensure that our model would have no problems reading ingredient amounts in recipes.
The cookies were delicious! The pretzels added a delightful crunch and a hint of salty flavor, bringing the entire cookie experience together. 

So, here's our chocolate chip cookie experiment, folks! It's not just about the cookies, it's a glimpse into what generative AI can achieve with a dash of data and a sprinkle of creativity.
We leave you with this food for thought (pun intended): Generative AI has the power to transform even the most mundane aspects of our lives. From optimizing daily routines to enhancing decision-making, it's a versatile tool ready to lend a hand. So, let's savor the sweetness of innovation and acknowledge that generative AI isn't just about cookies—it's about making the ordinary extraordinary.

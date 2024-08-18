# 🎉 Recipe Quest 🎉

Welcome to Recipe Quest, your go-to Vue.js app for discovering and exploring tasty meals! 🍲✨ Dive into a world of flavors and find recipes that will make your taste buds dance!

## 🚀 Getting Started

1. **Clone the repo:**

   ```bash
   git clone https://github.com/yourusername/recipe-quest.git
   ```

2. **Go to the project folder:**

   ```bash
   cd vue-recipe-search-app
   ```

3. **Install the goodies:**

   ```bash
   npm install
   ```

4. **Start cooking! 🍳**

   ```bash
   npm run dev
   ```

## 🥳 Features

❇︎ **Home Sweet Home**: Discover random meals that’ll make you go “Yum!” 🤤
❇︎ **Meal Hunt**: Search for meals by name—find exactly what you’re craving!
❇︎ **Letter Lovin’**: Browse meals starting with your favorite letter. A to Z! 🔠
❇︎ **Ingredient Magic**: Search for meals based on ingredients. What’s in your fridge? 🥕🍗
❇︎ **Meal Details**: Get all the juicy details about your favorite meals! 📜

## 🌟 Routes

❇︎ "/": Home page with random meal fun.
❇︎ "/by-name/:name?": Search for meals by name.
❇︎ "/by-letter/:letter?": Find meals that start with a letter.
❇︎ "/ingredients": List and search ingredients.
❇︎ "/by-ingredient/:ingredient": Meals featuring a specific ingredient.
❇︎ "/meal/:id": Deep dive into meal details.

## 🎨 Vue Components

❇︎ `Meals.vue`: Show off those scrumptious meals!
❇︎ `YouTubeButton.vue`: Dive into YouTube recipes with a click. 🎥
❇︎ `DefaultLayout.vue`: The cozy layout for logged-in users.

## 🛠️ Vuex Store

Manages:

❇︎ `searchedMeals`: Meals found with your search.
❇︎ `mealsByLetter`: Meals by the letter of the day.
❇︎ `mealsByIngredient`: Meals with your chosen ingredient.
❇︎ `ingredient`: The ingredient that’s got your attention!

## 🌐 API

We use a fantastic external API to fetch meal data. Check out `axiosClient.js` to configure it.

## 🤝 Contributing

Got ideas or found a bug? We’d love to hear from you! Open issues or send us a pull request!

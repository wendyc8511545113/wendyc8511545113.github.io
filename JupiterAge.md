---
layout: page
title: Jupiter Age
subtitle: Find out your age in Jupiter!
---

# 🚀 How Old Are You on Jupiter? 🌌  

Ever wondered how many years you've been around *if you lived on Jupiter*? 🪐 Well, wonder no more!  

This **C# program** calculates your **Jupiter age** based on Earth's years. Since Jupiter takes **11.86 Earth years** to orbit the Sun, you're *technically* much younger over there!  

Interact with the code here:

### **Enter Your Earth Age**:
<form id="ageForm">
    <label for="earthAge">Enter your age in Earth years: </label>
    <input type="number" id="earthAge" name="earthAge" required>
    <button type="submit">Calculate</button>
</form>

<p id="result"></p>

<script>
  // Function to calculate Jupiter age
  document.getElementById('ageForm').onsubmit = function(event) {
    event.preventDefault();  // Prevent page reload on form submission

    const userAge = parseFloat(document.getElementById('earthAge').value);
    const jupiterYears = 11.86;

    if (isNaN(userAge) || userAge <= 0) {
      document.getElementById('result').innerHTML = "Please enter a valid age!";
      return;
    }

    const jupiterAge = userAge / jupiterYears;
    const journeyToJupiter = 6.142466;  // Time to Jupiter
    const newEarthAge = userAge + journeyToJupiter;
    const newJupiterAge = newEarthAge / jupiterYears;
    document.getElementById('result').innerHTML = `
      <strong>Your Results:</strong><br>
      <strong>Earth Age:</strong> ${userAge} Earth years<br>
      <strong>Jupiter Age:</strong> ${jupiterAge.toFixed(2)} Jupiter years<br>
      <strong>Time to Jupiter:</strong> ${journeyToJupiter} years<br>
      <strong>New Earth Age:</strong> ${newEarthAge.toFixed(2)} Earth years<br>
      <strong>New Jupiter Age:</strong> ${newJupiterAge.toFixed(2)} Jupiter years
    `;
  };
</script>


**Check the C# code out here⬇️**
     
      int userAge = 11;  // Your Age
      Console.WriteLine($"I am {userAge} Earth years old.");
      
      double jupiterYears = 11.86;   // Length of years on Jupiter (in Earth years)
      Console.WriteLine($"Jupiter in 1 Earth year is {jupiterYears} Jupiter years.");
     
      double jupiterAge = userAge / jupiterYears;    // Age on Jupiter
      Console.WriteLine($"I would be {jupiterAge} Jupiter years old.");
      
      double journeyToJupiter = 6.142466;   // Time to Jupiter
      Console.WriteLine($"It will take {journeyToJupiter} years to get to Jupiter.");
      
      double newEarthAge = userAge + journeyToJupiter;   // New Age on Earth
      Console.WriteLine($"My new Earth age would be {newEarthAge}.");
      
      double newJupiterAge = newEarthAge / jupiterYears;   // New Age on Jupiter
      Console.WriteLine($"And my name Jupiter age would be {newJupiterAge}.");

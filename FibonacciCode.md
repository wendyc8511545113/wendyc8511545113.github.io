---
layout: page
title: C# Fibonacci
subtitle: A C# coding project
---

This simple **C# console application** allows users to generate the Fibonacci sequence up to a specified number of terms. The program dynamically allocates memory, calculates the sequence efficiently, and validates user input to ensure a smooth experience. Users can repeatedly request Fibonacci sequences or exit the program by typing **"quit"**.  

## 🛠 Features  
- ✅ **Accepts user input** for the number of terms  
- ✅ **Dynamically allocates storage** for Fibonacci numbers  
- ✅ **Uses a dedicated method** to compute the sequence  
- ✅ **Returns success or error messages** based on input validation  
- ✅ **Loops until the user decides to exit**  

## 📚 Learning Outcomes  
This project is a great introduction to:  
- 🔹 **C# programming basics**  
- 🔹 **Loops and arrays**  
- 🔹 **Function creation and method calls**  
- 🔹 **Algorithm implementation for Fibonacci sequences**  

```csharp <br>
using System;
class FibonacciSeries
{
    static void Main()
    {
        while (true)  // User input loop
        {
            Console.WriteLine("Enter a term of the Fibonacci number series (or quit to exit): ");
            string userInput = Console.ReadLine();
            
            if (userInput.ToLower() == "quit")  // Exit program if user enters "quit"
            {
                break;
            }

            if (int.TryParse(userInput, out int numTerms) && numTerms > 0)   // Try to parse the input and ensure it's a valid positive number
            {
                int[] fibSeries = new int[numTerms];

                bool success = Fibo(numTerms, fibSeries);

                if (success)
                {
                    Console.WriteLine($"Fibonacci series for {numTerms} terms:");
                    foreach (var term in fibSeries)
                    {
                        Console.WriteLine(term);
                    }
                }
                else
                {
                    Console.WriteLine("Please enter a valid number of terms.");
                }
            }
            else
            {
                Console.WriteLine("Error in Fibo. Please enter a valid positive integer.");
                continue;
            }
        }
    }

    static bool Fibo(int terms, int[] results)    // Method to calculate Fibonacci series
    {
        if (terms <= 0 || results == null || results.Length < terms)  // Check for invalid terms
        {
            return false;
        }

        results[0] = 0;   // Initialize the first two terms of the Fibonacci sequence
        if (terms > 1)
        {
            results[1] = 1;
        }
        
        for (int i = 2; i < terms; i++)  // Calculate remaining Fibonacci terms
        {
            results[i] = results[i - 1] + results[i - 2];
        }

        return true; // Return true when successful
    }
}

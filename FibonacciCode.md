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

```csharp

/* Program Overview:
 * This program calculates and displays the Fibonacci number series for a user-specified number.
 * The program will continue to run until the user types "quit" to exit.
 * 
 * Main Method: User input loop location
 * Fibo Method: Fibonacci calculation location
 */

using System;
class FibonacciSeries
{
    static void Main()
    {
        // User input loop
        while (true)
        {
            // Prompt the user for input
            Console.WriteLine("Enter a term of the fibonacci number series (or quit to exit)>> ");
            string userInput = Console.ReadLine();

            // Exit program if user enters "quit"
            if (userInput.ToLower() == "quit")
            {
                break;
            }

            // Try to parse the input and ensure it's a valid positive number
            if (int.TryParse(userInput, out int numTerms) && numTerms > 0)
            {
                int[] fibSeries = new int[numTerms];

                // Call the Fibo method to calculate 
                bool success = Fibo(numTerms, fibSeries);

                // If calculation successful, print the series
                if (success)
                {
                    Console.WriteLine("Fibonacci series for {0} terms: ", numTerms);
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
                // If input is invalid
                Console.WriteLine("Error in Fibo. Please enter a valid positive integer.");
                continue;
            }
        }
    }

    // Method to calculate Fibonacci series

    static bool Fibo(int terms, int[] results)
    {
        // Check for invalid terms
        if (terms <= 0 || results == null || results.Length < terms)
        {
            return false;
        }

        // Initialize the first two terms of the Fibonacci sequence

        results[0] = 0;
        if (terms > 1)
        {
            results[1] = 1;
        }

        // Calculate remaining Fibonacci terms

        for (int i = 2; i < terms; i++)
        {
            results[i] = results[i - 1] + results[i - 2];
        }

        return true; // Return true when successful
    }
}

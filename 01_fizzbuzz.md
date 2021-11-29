# C# Three Ways: Fizzbuzz

<!-- OMITTED -->

In this exercise you will test-drive Fizzbuzz. As with all Makers materials you will be expected to learn by doing, by thinking hard, and through independent research. You will be rewarded for your efforts with learning that you can really apply to solve the challenges ahead. Consider this a hiking trail, not a tour bus.

Let's get started.

## Installing the prerequisites

Go ahead and install these prerequisites.

* Head over to [Microsoft](https://visualstudio.microsoft.com/downloads/) and download Visual Studio for Mac. Follow the instructions to install it on your computer.
* The first time you open Visual Studio, you'll be asked "What would you like to install?". Make sure only `.NET Core` is selected and hit "Install and Update"
* When asked to Sign In, skip for now. If you prefer the VSCode keyboard bindings, select those. If you don't have a preference yet, chose the Visual Studio for Mac ones.

## Hello World

Let's begin with a Hello World. Open Visual Studio <!-- OMITTED --> and create a new file. Select a console application, and target the .NET 5 Framework. Name the project 'HelloWorld' (C# uses `PascalCasing`). You'll see in the program.cs file the structure of our hello world program already written for us:

```C#
// `using` is how we import dependencies.
// we'll need the System library to use the Console and write output there.
using System;

// This is the name of this program
namespace HelloWorld
{
    // class Program is always the 'entry point' of our application. When we run the application
    // This is the class that will be loaded and run automatically
    class Program
    {
        // Inside the program class, the Main method is always what runs first
        // when we run our application
        static void Main(string[] args)
        {
            // We use the 'Console' class (in the System library)
            // and the WriteLine method to write to the terminal console
            Console.WriteLine("Hello World!");
        }
    }
}
```

We can run our application by selecting "Run" from the menu bar. Choose "Run without debugging". You'll see a terminal open up and _build_ your application, then shortly after _run_ the application

You should see 'Hello World' printed in this newly opened tutorial.

Got it? Great! Let's move on.

## Fizzbuzz

Your task is to test-drive a program that takes a max number and returns a string. The string should list out the numbers counting up to and including the given max number, substituting Fizz where the number is divisible by 3, Buzz where it is divisible by 5, and FizzBuzz where it is divisible by both 3 and 5.

Here's an example:

```
CALLING:
  fizzbuzz(15)
SHOULD RETURN:
  "1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz"
```

You're going to test drive this, which will be much easier if you avoid printing to the terminal.

First, we'll need to add a testing framework to our project. To do this, we will first create a new Console Application and call the project name 'Core', but the solution name 'FizzBuzz'. This is a convention in C#, so just stick to naming this way for now. 

Next, we'll right click the solution named "FizzBuzz" and select Add > New Project. Choose an MSTest project this time, and call it 'UnitTests'. Finally, in the UnitTests folder, right click on dependencies and select 'Add reference'. Add the Core project as a reference.

Great ! We're all set up for writing TDD C# now.

Here is a starting point for testing:

```C#
// FizzBuzz/UnitTests/FizzBuzzTest.cs
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Core;

namespace UnitTests
{
    // We use the annotations [TestClass]
    [TestClass]
    public class FizzBuzzTest
    {
        // ... and [TestMethod] to tell the C# compiler these are test classes and methods
        [TestMethod]
        public void List_Numbers_Up_To_One()
        {
            FizzBuzz fizzBuzz = new();

            string result = fizzBuzz.generate(1);

            Assert.AreEqual("1", result);
        }

        [TestMethod]
        public void List_Numbers_Up_To_Two()
        {
            FizzBuzz fizzBuzz = new();

            string result = fizzBuzz.generate(2);

            Assert.AreEqual("1, 2", result);
        }
    }
}


// FizzBuzz/Core/FizzBuzz.cs
using System;

namespace Core
{
    public class FizzBuzz
    {
        public string generate(int count)
        {
            return "1";
        }
    }
}
```

You're done when your code passes the following acceptance criteria:

```
CALLING:
  fizzbuzz(100)
SHOULD RETURN:
  "1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz, 16, 17, Fizz, 19, Buzz, Fizz, 22, 23, Fizz, Buzz, 26, Fizz, 28, 29, FizzBuzz, 31, 32, Fizz, 34, Buzz, Fizz, 37, 38, Fizz, Buzz, 41, Fizz, 43, 44, FizzBuzz, 46, 47, Fizz, 49, Buzz, Fizz, 52, 53, Fizz, Buzz, 56, Fizz, 58, 59, FizzBuzz, 61, 62, Fizz, 64, Buzz, Fizz, 67, 68, Fizz, Buzz, 71, Fizz, 73, 74, FizzBuzz, 76, 77, Fizz, 79, Buzz, Fizz, 82, 83, Fizz, Buzz, 86, Fizz, 88, 89, FizzBuzz, 91, 92, Fizz, 94, Buzz, Fizz, 97, 98, Fizz, Buzz"
```

### What you'll need to learn

Amongst other things, you'll need to learn:

* [C# basics (Branches, Loops, Lists, etc)](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/tutorials/)
* [C# types](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types)
* [C# classes and objects](https://www.geeksforgeeks.org/c-sharp-class-and-object/)
* [Testing in C#](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-mstest)
* [MSTest Documentation](https://docs.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting?view=visualstudiosdk-2022) and specifically [MSTest Assertions](https://docs.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert?view=visualstudiosdk-2022)

<!-- OMITTED -->

## Done?

[Go to the next challenge](./02_bank.md)


<!-- BEGIN GENERATED SECTION DO NOT EDIT -->

---

**How was this resource?**  
[😫](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/01_fizzbuzz.md&prefill_Sentiment=😫) [😕](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/01_fizzbuzz.md&prefill_Sentiment=😕) [😐](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/01_fizzbuzz.md&prefill_Sentiment=😐) [🙂](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/01_fizzbuzz.md&prefill_Sentiment=🙂) [😀](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/01_fizzbuzz.md&prefill_Sentiment=😀)  
Click an emoji to tell us.

<!-- END GENERATED SECTION DO NOT EDIT -->

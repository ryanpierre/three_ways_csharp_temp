# C# Three Ways: Bank

<!-- OMITTED -->

In this exercise you'll test-drive Bank. Where Fizzbuzz introduced you to the
rudimentary conditions and loops of the language, Bank introduces you to
way modules of code are organised in a language. 

## C#'s Paradigm

C# is a statically typed, object-oriented language. Here's what 
that means:

* **Statically Typed** means you are responsible for telling the compiler
  what type all of the variables are.
* **Object Oriented** means it structures large programs using Objects. Those
  objects encapsulate (control within them) state and expose methods that
  operate on that state for others to call. They are created from templates
  called Classes.

Here's an example of a secret diary program. Take a careful read of it to
understand what it is doing and compare it to languages you know.

```C#
// Core/Diary.cs
using System;

namespace Core
{
    public class Diary : IDiary
    {
        private readonly string contents = "Eric Cantona is the best footballer";

        public string Read()
        {
            return contents;
        }
    }
}

// Core/SecretDiary.cs
using System;

namespace Core
{
    public class SecretDiary
    {
        private bool locked = true;
        private readonly Diary diary;

        public SecretDiary(Diary contents)
        {
            diary = contents;
        }

        public string Read()
        {
            if(locked)
            {
                throw new InvalidOperationException("Go away!");
            }

            return diary.Read();
        }

        public void Unlock()
        {
            locked = false;
        }

        public void Lock()
        {
            locked = true;
        }
    }
}

// Core/Program.cs
using System;

namespace Core
{
    class Program
    {
        static void Main(string[] args)
        {
            Diary diary = new();
            SecretDiary secretDiary = new(diary);

            // secretDiary.Unlock();

            Console.WriteLine(secretDiary.Read());
        }
    }
}

```

You'll see after you use the `Run > Without Debugging` command that the "Go Away!" error is thrown. If we uncomment the `Unlock()` line, we'll find that the diary contents are printed in the console.

## Exercise

Your task is to write an application that a user can call to make bank
transactions and then print a bank statement to the terminal. We'll write it using TDD, and we'll utilise the MSTest framework and the [Moq mocking library](https://github.com/moq/moq4) to make our lives easier. Some languages don't have things like `double` built into the testing framework and require a second dependency like Moq in order to mock and stub objects. It can still be done without the library, but it's almost never done that way.

To get started, create a new console application called Core, inside the Bank solution. Then, add a testing project to the solution as we did in the fizzbuzz example. Finally, we'll use NuGet to install the Moq dependency by right clicking on our testing project dependencies, selecting Manage NuGet... and then finding the Moq library in the search bar. Make sure to also add Core as a dependency to our UnitTests project too.

### Requirements

* Implement deposits and withdrawals
* Implement an account statement that prints a heading row, and the date, amount
  an balance of each transaction, most recent first.
* You don't need to implement a command-line or user interface, test-driving
  and calling it in your main method / via REPL is enough. <!-- OMITTED -->
* Data can be kept in memory, doesn't need to be in a database.

### Acceptance Criteria

Below is an example of how your code should be called, and what it should
output.

<!-- OMITTED -->

```C#

// Core/Program.cs
using System;

namespace Core
{
    class Program
    {
        static void Main(string[] args)
        {
            BankAccount bankAccount = new();

            // Given a client makes a deposit of 1000 on 2021-01-01
            bankAccount.Deposit(1000, DateTime.Parse("Jan 10, 2021"));

            // And a deposit of 2000 on 2021-01-13
            bankAccount.Deposit(2000, DateTime.Parse("Jan 13, 2021"));

            // And a withdrawal of 500 on 2021-01-14
            bankAccount.Withdraw(500, DateTime.Parse("Jan 14, 2021"));

            // When she prints her bank statement
            Console.WriteLine(bankAccount.GenerateStatement());
        }
    }
}
```

Then she would see:

```
date || credit || debit || balance
14/01/2021 || - || 500.00 || 2500.00
13/01/2021 || 2000.00 || - || 3000.00
10/01/2021 || 1000.00 || - || 1000.00
```

## What you'll need to learn

Amongst other things, you'll need to learn:

* [How to manage external dependencies in C#](https://docs.microsoft.com/en-us/nuget/consume-packages/install-use-packages-visual-studio)
* [Learn about object oriented programming in C#](https://zetcode.com/lang/csharp/oopi/)
* [Best practices for testing in C#](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices)
* [Learn about interfaces - you'll need these to successfully mock classes](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/interfaces)

<!-- OMITTED -->


<!-- BEGIN GENERATED SECTION DO NOT EDIT -->

---

**How was this resource?**  
[😫](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/02_bank.md&prefill_Sentiment=😫) [😕](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/02_bank.md&prefill_Sentiment=😕) [😐](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/02_bank.md&prefill_Sentiment=😐) [🙂](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/02_bank.md&prefill_Sentiment=🙂) [😀](https://airtable.com/shrUJ3t7KLMqVRFKR?prefill_Repository=makersacademy/three_ways&prefill_File=csharp/02_bank.md&prefill_Sentiment=😀)  
Click an emoji to tell us.

<!-- END GENERATED SECTION DO NOT EDIT -->

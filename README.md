# Groovy Closure Exception Handling

This repository demonstrates an unusual behavior in Groovy related to exception handling within closures.  When an exception is thrown inside a closure passed to a method, the code after the closure call in the method is not executed.  This example highlights this behavior and provides a solution to handle it properly.

## Bug

The `bug.groovy` file contains a Groovy script that defines a method `methodWithClosure` which takes a closure as an argument. The closure throws a `RuntimeException`. The script demonstrates that the `println` statement after the closure call is not reached when the exception occurs within the closure.

## Solution

The `bugSolution.groovy` file presents a corrected version, using a `try-catch` block to handle the potential exception within the `methodWithClosure` method, ensuring the code after the closure call executes correctly, even when an exception occurs inside the closure.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `groovy bug.groovy`. Observe the output.  Note that "This line won't be reached" is not printed.
4. Run `groovy bugSolution.groovy`. Observe the output.  Note that "This line will be reached" *is* printed.

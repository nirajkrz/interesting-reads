## The Recursion

#### The three key features of recursion
All recursive functions should have three key features:
##### A Termination Condition
Simply put: if(something bad happened){ STOP }; The Termination Condition is our recursion fail-safe. Think of it like your emergency brake. It’s put there in case of bad input to prevent the recursion from ever running. In our factorial example, if (x < 0) return; is our termination condition. It’s not possible to factorial a negative number and thus, we don’t even want to run our recursion if a negative number is input.
##### A Base Case
Simply put: if(this happens) { Yay! We're done }; The Base Case is similar to our termination condition in that it also stops our recursion. But remember, the termination condition is a catch-all for bad data. Whereas the base case is the goal of our recursive function. Base cases are usually within an if statement .In the factorial example, if (x === 0) return 1; is our base case. We know that once we’ve gotten x down to zero, we’ve succeeded in determining our factorial!
##### The Recursion
Simply put: Our function calling itself. In the factorial example, return x * factorial(x — 1); is where the recursion actually happens. We’re returning the value of the number x multiplied by the value of whatever factorial(x-1) evaluates to.


```
function factorial(x) {
  // TERMINATION
  if (x < 0) return;
  // BASE
  if (x === 0) return 1;
  // RECURSION
  return x * factorial(x - 1);
}
factorial(3);
// 6

```


#### Factorial Function Flow
Lets examine exactly what happens when we call our Factorial Function:
1. We first call our function passing in the value of 3.
factorial(3);
2. This results in the function being run. Both if statements fail and our recursion line runs. We return the integer 3 multiplied by the value of factorial(3-1).
return 3 * factorial(2);
3. When factorial(2) is run, both if statements fail again and recursion occurs. We return the integer 2 multiplied by the value of factorial(2-1).
return 2 * factorial(1);
4. When factorial(1) is run, both if statements fail again and recursion occurs. We return the integer 1 multiplied by the value of factorial(1-1).
return 1 * factorial(0);
5. When factorial(0) is run, something different happens. Zero is our base case, so that if statement passes and our function returns 1.
if (x === 0) return 1;
Now that our function has finally returned, everything will ‘unwind’. This is because recursion is simply a group of nested function calls. With nested functions, the most inner nested function will return first.

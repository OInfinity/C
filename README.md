# C
Tell me the difference please:

1. int main(void)

{
    printf("Hello, world!\n");  
} 

and

2. int main(void)

{

    printf("Hello, world!\n");
    
    return 0;
    
} 

V2. No return Value
- A return value goes back where it was called (From a calling function)

✅ Summary:
- `Calling a function` means running that function.
- main() is called by the OS.
- printf() is called by you inside main().
- return 0 = Stop executing.

| Function   | Who calls it?             | What it does                         |
| ---------- | ------------------------- | ------------------------------------ |
| `main()`   | The operating system      | Starts your program                  |
| `printf()` | **You** (inside `main()`) | Prints "Hello, world!" to the screen |

When we say a function is called, it means the program jumps to execute the code inside that function, we write return 0, it means successfully executed, stops and return to where you were called (get outside of the function), return means: “I'm done here — go back to where the function was called, optionally sending back a value.”

🔹 Case 1: In Modern C (C99 and later):
- If `main()` ends without a return, the compiler will automatically add return 0;.
- So: ✅ No problem.
- That's why your program still runs fine — because it’s treated as if return 0; was there.

🔹 Case 2: In Older C (like C89):
- No return = ⚠️ Undefined behavior
- The compiler might not know what value to return.
- Could lead to:
- Random values returned,
- Warnings/errors during compilation,
- Unpredictable behavior on some systems.

| Case                           | What Happens                                                               |
| ------------------------------ | -------------------------------------------------------------------------- |
| `return 0;` in `main()`        | Clean, defined exit — control goes back to the OS                          |
| No `return` in `main()` (C99+) | Still works — compiler assumes `return 0;`                                 |
| No `return` in `main()` (C89)  | Undefined behavior — should be avoided                                     |
| No `return` in other functions | ❌ Error or undefined behavior if the function promises to return something |





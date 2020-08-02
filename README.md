# Usage

1. Add `profiler.h` and `profiler.mm` to your project.

2. Add `PROFILING=1` to your "Preprocessor macros" setting

3. Profile functions of interest using `PSTART` and `PEND` macros:

  ```objective-c
  void FunctionToProfile(arg0, arg1, ...) {
      PSTART
      // some code I want to profile
     
      PEND
   } 
  ```

  

4. The profiler dump will be printed when your program exits, OR do this in your debugger:

    GDB
    ```
    call (void)ProfilerExitFunction()
    ```
    
    LLDB
    ```
    expr (void)ProfilerExitFunction()
    ```

    This will get you your profiler dump in your debug console.

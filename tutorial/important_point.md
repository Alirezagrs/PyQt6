# sys.exit(app.exec())
### In PyQt (whether PyQt5 or PyQt6) when you run your program, it must enter an event loop; that is, the program sits and waits for events like clicks, keyboard, resize, etc. to happen.This is done by the app.exec() method.<br>That is, if you don't write this, the window will open and close immediately, because there is no loop.<br>

### The exec() function returns an exit code.This code is usually:
### 0 means the program closed successfully.

### Anything other than 0 means an error or a special condition caused the closure.

### We pass this value to sys.exit(...) to tell the operating system what state the program closed in.

### If you just write app.exec() , the program will open and close, but the exit code will not be passed to the operating system.

### In practice, this doesn't matter on most systems, but it does matter in scripts or when you're running the program from another program.

### ✅ sys.exit(app.exec()) → Standard and correct, especially for programs that run seriously on the operating system.

### ⚠️ app.exec() → also works, but does not output the status to the operating system.
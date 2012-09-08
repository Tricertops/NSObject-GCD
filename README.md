`NSObject+GCD`
==============

Simple Objective-C wrapper for most used Grand Central Dispatch functions.

**Features:**
  - You can call these methods on any object in your code (I recommend to always use `self`).
  - `-performOnMainThread:wait:` – execute block on main thread from any other thread
  - `-performAsynchronous:` – execute block in background (to return back to main thread use method mentioned above)
  - `-performAfter:block:` – execute block on the same thread, but after some delay 

**Examples:**
  - Background task with completion on Main Thread:

        [self performAsynchronous:^{
            
            // Background Task
            
            [self performOnMainThread:^{
                // Completion on Main Thread
            } wait:NO];
        }];

  - Delayed execution:

        [player play];
        [self performAfter:3 block:^{
            [player pause];
        }];
        
------------------------------------------------------------------------------------------
**TODO:** Add documentation comments.

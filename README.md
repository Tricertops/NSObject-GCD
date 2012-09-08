`NSObject+GCD`
==============

Simple Objective-C wrapper for Grand Central Dispatch functions.

**Features:**
  - Since it is category on `NSObject`, you can call these on any object in your code (except `NSProxies` ...), but it has no role on execution. Use always `self`.
  - `-performOnMainThread:wait:` – execute block on main thread/queue from any other thread/queue
  - `-performAsynchronous:` – execute block in background (to return back to main thread/queue use method mentioned above)
  - `-performAfter:block:` – execute block on the same thread/queue, but after some delay 

**Examples:**
  - Background task with completion on main thread:

        [self performAsynchronous:^{
            
            // Background Task
            
            [self performOnMainThread:^{
                // Completion on Main Queue
            } wait:NO];
        }];

  - Delayed execution:

        [player play];
        [self performAfter:3 block:^{
            [player pause];
        }];
------------------------------------------------------------------------------------------
**TODO:** Add documentation comments.

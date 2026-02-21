# Unity Things

## Abstract Class 

Apa itu Abstract Class yang ada pada :
```c#
    public abstract class Interactable : MonoBehaviour
```

Artinya <br>
<ul>abstract → You cannot attach this directly to a GameObject. </ul>
<ul>It is meant to be inherited. </ul>
<ul>Other scripts will extend it. </ul>

PART 1 — Logic Behind Interactable
Core Idea:

Create a universal interaction entry point.

Instead of writing:

if (object is Door) { ... }
if (object is Chest) { ... }
if (object is Keypad) { ... }


You just do:

hit.GetComponent<Interactable>().baseInteract();


And polymorphism handles the rest.

The Interaction Flow

When player presses E:

Player
  ↓
baseInteract()
  ↓
1. Optional UnityEvent
2. Call Interact() (child version)


Interact() is empty in the base class,
but overridden in child classes.

That’s the flexible part.
# Unity Things

## Abstract Class 

Apa itu Abstract Class yang ada pada :
```c#
public abstract class Interactable : MonoBehaviour
```

Artinya <br>
<li>Abstract → Kelas yang tidak dapat ditempel pada sebuah game objek unity</li>
<li>Kelas ini tujuannya untuk diwariskan oleh kelas lain</li>
<li>Kelas lain menjadi perpanjangan tangan kelas abstrak, seperti Interactable </li>

## Logic Behind Interactable
We got this Interactable.cs for a basic FPS 3D game:
```c#
public abstract class Interactable : MonoBehaviour
{
    // Pesan muncul jika object yg dituju memiliki tag 'Interactable'
    public string promptMessage;

    // If true → use Unity Events system
    // If false → only use code override
    public bool useEvents;

    public void baseInteract()
    {
        //jika ada assigned function dari editor, maka lakukan itu
        if (useEvents)
        {
            // perform a behaviour based on assigned function
            GetComponent<InteractionEvent>().OnInteract.Invoke(); 
        }
        // jika tidak ada maka gunakan function yang ada pada extended script 
        // yang di-attach pada interactable object
        Interact(); //inherited function from extended script
    }

    //use virtual void because can be overridden
    protected virtual void Interact() { } 
}
```

!!! question "Apa ini??"    
Interactable.cs adalah sebuah kelas abstrak yang bisa ditemukan pada sebuah projek game 3D unity. Kelas ini biasa digunakan sebagai basis kelas untuk semua objek yang interactable pada game unity. Misalnya pintu, NPC, karakter lawan, dan lain-lain.

Create a universal interaction entry point.

Instead of writing:

```
if (object is Door) { ... }
if (object is Chest) { ... }
if (object is Keypad) { ... }
```

You just do:
```
hit.GetComponent<Interactable>().baseInteract();
```
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
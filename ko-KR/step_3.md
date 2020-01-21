## Shooting arrows

Let's code your arrow to shoot when the space bar is pressed.

\--- task \---

Stop the other script (the one moving the arrow) when the space bar is pressed.

![target sprite](images/target-sprite.png)

```blocks3
when [space v] key pressed
stop [other scripts in sprite v]
```

\--- /task \---

\--- task \---

프로젝트를 다시 테스트해 보세요. This time, your arrow should stop moving **when the space bar is pressed**.

\--- /task \---

\--- task \---

Animate your arrow, so that it looks like it's moving towards the target.

![target sprite](images/target-sprite.png)

```blocks3
when [space v] key pressed
stop [other scripts in sprite v]
+repeat (50)
change size by (-10)
end
```

\--- /task \---

\--- task \---

Test your game again. This time, when you press the space bar you should see your arrow get smaller, as if it's moving towards the target.

![target with the cross hair on it](images/archery-animate-test.png)

\--- /task \---

\--- task \---

Once your arrow is at the target, you can tell the player how many points they have scored. For example, they could score 200 points for hitting the yellow.

![target sprite](images/target-sprite.png)

```blocks3
when [space v] key pressed
stop [other scripts in sprite v]
repeat (50)
change size by (-10)
end
+if <touching color (#ffff00) ?> then
say [200 points] for (2) seconds
end
```

\--- /task \---

\--- task \---

You can also play a sound if they hit the yellow.

![target sprite](images/target-sprite.png)

```blocks3
when [space v] key pressed
stop [other scripts in sprite v]
repeat (50)
change size by (-10)
end
if <touching color (#ffff00) ?> then
+start sound (cheer v)
say [200 points] for (2) seconds
end
```

\--- /task \---

\--- task \---

Finally, you need to broadcast the `new arrow`{:class="block3events"} message again to get a new arrow.

![target sprite](images/target-sprite.png)

```blocks3
when [space v] key pressed
stop [other scripts in sprite v]
repeat (50)
change size by (-10)
end
if <touching color (#ffff00) ?> then
start sound (cheer v)
say [200 points] for (2) seconds
end
+broadcast (new arrow v)
```

\--- /task \---
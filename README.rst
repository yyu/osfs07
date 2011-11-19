Operating System From Scratch
-----------------------------

Step 07: TTYs
`````````````

Currently once the system boots, all we do is to sit in the chair and watch it.
It's time to add some interaction.

Keyboard
''''''''

How does the OS know it when a key is pressed?
It's easy: the keyboard generates an interrupt to let the OS know.
We will enable the keyboard interrupt, write a handler and read the code of the key(s) from the keyboard.
See ``a/`` and ``b/``.

Now we have the codes of keys pressed.
We use a process to manipulate them (see ``c/``) so that
we can recognize letters and numbers (see ``d/``), Shift, Alt and Ctrl (see ``e/``) and even
Pause and PrintScreen (see ``f/``).
Then we can decide how to deal with these key presses, probably display something in the screen (see ``g/``):

.. image:: http://osfromscratch.org/snapshots/original/%E5%9B%BE07.09%20%E6%95%B2%E5%87%BB%E6%97%A0%E6%B3%95%E5%A4%84%E7%90%86%E7%9A%84%E6%8C%89%E9%94%AE%E4%B8%8D%E5%86%8D%E6%89%93%E5%8D%B0%E5%A5%87%E6%80%AA%E7%9A%84%E7%AC%A6%E5%8F%B7.png

Screen
''''''

The screen is small. It won't be long before you type too many letters in it, so we should support screen scroll.
We want to see where we are when typing, so we should be able to move the cursor (the cursor hasn't moved for long).
All of these can be easily done by writing some I/O ports.
We'll try to write some ports in ``h/``.

Console & TTY
'''''''''''''

When using Linux, we know we can swtich TTYs by pressing Alt+Fx, where x is 1, 2, ...
We will simulate this in our OS (see ``i/`` and ``j/``):

.. image:: http://osfromscratch.org/snapshots/original/%E5%9B%BE07.19%20%E6%98%BE%E7%A4%BA%E5%BC%80%E5%A7%8B%E5%9C%B0%E5%9D%80%E8%A2%AB%E9%87%8D%E6%96%B0%E8%AE%BE%E7%BD%AE.png

Everything is good.
It's time to polish our code to support screen scroll (see ``k/``), Enter and Backspace (see ``l/``), CapsLock, NumLock and ScrLock (see ``m/``).

TASK and PROC
'''''''''''''

So far we have two types of processes: a system process TTY and three user processes A, B and C.
As was mentioned in `Step 06`_, we want them to run in different privilege levels.
See ``n/`` for details.

printf
''''''

We use ``printf()`` a lot.
Now that we have our own OS, we should implement one.
See ``o/`` for details.


`‹prev`_   `next›`_

.. _`Step 06`: https://github.com/yyu/osfs06
.. _`‹prev`: https://github.com/yyu/osfs06
.. _`next›`: https://github.com/yyu/osfs08

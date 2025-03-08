---
title: "Find the egg"
date: 2024-11-24T22:24:28+02:00
draft: false
---

I made a silly little game in a few minutes fith my son. He just wanted to play a little more "Hollow Knight" and I just wanted to direct that into something more creative and useful. So we came up with this silly game idea - "Find the Egg!". It would just show a little grid and you'd have to guess where on the grid the egg is.

**Grid**
```
# # #
# # #
# # #
```

**No egg**
```
X # #
# # #
# # #
```

**Found the egg**
```
# # #
# # #
# 0 #
```

### The gist

[https://gist.github.com/ariedov/63cc2a359b0545a9e90ee52b82e0c925](https://gist.github.com/ariedov/63cc2a359b0545a9e90ee52b82e0c925)

### And here is the code.

```python
import random
import os

random.seed()

row = -1
col = -1

egg_row = random.randint(1, 3)
egg_col = random.randint(1, 3)

while True:
    os.system('cls' if os.name == 'nt' else 'clear')
    for i in range(1, 4):
        for j in range(1, 4):
            if ((i == egg_row and j == egg_col)
                    and (row == egg_row and col == egg_col)):
                print("0", end=" ")
            elif i == row and j == col:
                print("X", end=" ")
            else:
                print("#", end=" ")
        print()

    if row == egg_row and col == egg_col:
        input("Вітаю, ти знайшов яйце!")
        row = -1
        col = -1
        random.seed()
        egg_row = random.randint(1, 3)
        egg_col = random.randint(1, 3)

    try:
        row = int(input("Який рядок? "))
        print(row)
        col = int(input("Яка колонка? "))
        print(col)
    except ValueError:
        pass
    except EOFError:
        pass
```


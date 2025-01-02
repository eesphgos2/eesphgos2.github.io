---
layout: page
title: Programming
description: game code
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---


there is a code of naviget in forest 

{% raw %}

```c
#include <stdio.h>
#include <stdlib.h>
int navigetForest(int x);

int gold = 0, energy = 100, level = 1, a;

int main()
{

  unsigned seed;

  scanf("%u", &seed);

  srand(seed);

  navigetForest(rand() % 4);
  return 0;
}

int navigetForest(int x)
{
  int gg;
  enum status
  {
    Treasure,
    Monster,
    Puzzle,
    Rest
  };

  enum status game;

  game = x;
  if (level == 11)
  {
    printf("You Win.\nGold = %d", gold);
    return 1;
  }
  if (energy <= 0)
  {
    printf("Game Over! You ran out of energy at level %d.", level);
    return 1;
  }

  switch (game)
  {

  case Treasure:

    printf("Level %d: Challenge - TREASURE\n", level);
    gg = 10 + rand() % 40;
    gold += gg;
    printf("You found gold! Gold +%d, Energy -10\n", gg);
    energy -= 10;
    printf("Current Stats: Gold = %d, Energy = %d\n", gold, energy);
    printf("\n");
    level++;
    break;
  case Monster:

    printf("Level %d: Challenge -  MONSTER\n", level);
    printf("You fought a monster! Energy -30\n");
    energy -= 30;
    printf("Current Stats: Gold = %d, Energy = %d\n", gold, energy);
    printf("\n");
    level++;
    break;
  case Puzzle:

    printf("Level %d: Challenge - PUZZLE\n", level);
    printf("You solved a puzzle! Energy -20\n");
    energy -= 20;
    printf("Current Stats: Gold = %d, Energy = %d\n", gold, energy);
    printf("\n");
    level++;
    break;
  case Rest:

    energy += 20;
    if (energy > 100)
    {
      energy = 100;
    }
    break;
  }

  return navigetForest(rand() % 4);
}

```

{% endraw %}

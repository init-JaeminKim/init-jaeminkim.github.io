---
title: "[C++]Number of Cases in 2D Vector"
date:   2020-09-13 14:37:56

categories:
  - C++
---

**_Congratulations!_**

You've got the free toppings you can put on a pizza. You may want to select at least one topping from the table below, but the same type of toppings cannot be chosen. Then, How many numbers of cases exist?

| Type     | Name                     |
|----------|--------------------------|
| Meats    | Bacon, Sausage, Chicken  |
| Seafoods | Shrimp                   |
| Veggies  | Onion, Mushroom          |
| Cheeses  | Provolone                |

First of all, we have to consider the case that only one topping is selected. So, the number of toppings in the same type will be counted, and add 1 to the count for each unchosen type of topping.

```cpp
int solution(vector<vector<string>> toppings) {
    int answer = 1;
    unordered_map<string, int>solution_map;
    for(auto t : toppings){
        solution_map[t[1]]++;
    }//Meats = 3, Seafoods = 1, Veggies = 2, Cheeses = 1
    for(auto pair : solution_map){
        answer *= pair.second + 1;
    }
    return answer - 1;
}
```

The reason of subtracting 1 from `answer` is to except the case that none of toppings is not be chosen.

There are total **47** options for you.

**Enjoy Pizza Night!**
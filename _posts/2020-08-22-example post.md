---
title: "Find Different Elements Between Two Vectors in C++"
date:   2020-09-05 13:45:35

categories:
  - C++
---

There are two simple ways: Comparing Indexes and [Hash Table](https://en.wikipedia.org/wiki/Hash_table).

## 1. Comparing Indexes

Here are two vectors.

```cpp
string solution(vector<string> applicants, vector<string> successful)
{
  //do someting
}
```

Before comparing, the elements in both vetors need to be in order with `std::sort()`.

```cpp
  sort(applicants.begin(), applicants.end());
  sort(successful.begin(), successful.end());
```
**Note:** The time complexity of `std::sort()` is _O(n log n)_.
{: .notice--info}

It's ready to compare the indexes of two vetors. If any differences are founded within `for()` statement, the index is returned.

```cpp
for(int i = 0; i < successful.size(); ++i)
{
  if(applicants[i] != successful[i])
  {
    return applicants[i];
  }
}
```

## 2. unordered_map

Let's create an unordered_map like this:

```cpp
string solution(vector<string> applicants, vector<string> successful)
{
  unordered_map<string, int> solution_map;
}
```

**Note:** on an average the cost of search, insert and delete from `Hash table` is O(1).
{: .notice--info}

Then, increment the _values_ of each _key_ in solution_map. On the same principle, decrement the _values_ of each _key_ which are in "successful".

```cpp
for(string name: applicants){
  solution_map[name]++;
  }
for(string name: successful){
  solution_map[name]--;
  }
```

Now we know the value bigger than 0 is the diffent element.

```cpp
for(auto pair: solution_map){
  if (pair.second>0){
    return pair.first;
  }
}
```
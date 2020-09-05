---
title: "Find Different Elements Between Two Vectors in C++"
date:   2020-09-05 13:45:35

categories:
  - C++
---

## 1. Comparing Indexes

Here are two vectors.

```cpp
string solution(vector<string> applicants, vector<string> successful)
{
  //do someting
}
```

Before comparing, the elements in both vetors need to be in order with `sort()`.

```cpp
  sort(applicants.begin(), applicants.end());
  sort(successful.begin(), successful.end());
```

Now, it's ready to compare the indexes of two vetors. If any differences are founded within `for()` statement, the index is returned.

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

**Watch out!** This paragraph of text has been [emphasized](#) with the `{: .notice--info}` class.
{: .notice--info}


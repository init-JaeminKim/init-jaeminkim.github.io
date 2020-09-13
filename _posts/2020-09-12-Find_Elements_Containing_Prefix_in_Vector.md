---
title: "Check if Elements Containing Prefix in Vector"
date:   2020-09-12 12:21:20

categories:
  - C++
---

Let's initialize the vector like this:

```cpp
vector <string> vec {"620", "762074223", "6205524421"};
```

The first element in the vector is the prefix, and the rest may have the prefix or not. If an element has the prefix, return **TRUE**.

For better performance, you can use `std::sort()`. Then, check if the elements have the prefix with `string::find()`.

```cpp
bool solution(vector<string> vec) {

    bool answer = false;

    sort(vec.begin(), vec.end());

    for(int i = 0; i < vec.size()-1; i++){
        if(vec[i+1].find(vec[0]) == 0){
            answer = true;
        }
    }

    return answer;
}
```

`string::substr()` also can be used to check the elements like this:

```cpp
if ( vec[i] == vec[i+1].substr(0, vec[i].size()))
```

Performance difference between two methods is described [[here]](https://stackoverflow.com/questions/12388713/performance-look-for-a-substring-substr-vs-find)
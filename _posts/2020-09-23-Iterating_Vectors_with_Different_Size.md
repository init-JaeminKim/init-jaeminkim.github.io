---
title: "Iterating Vectors with Different Size"
date:   2020-09-23 15:57:44

categories:
  - C++
---

Here are three vectors containing correct answers for each test takers, and they christmas-treed the test like below:

```cpp
vector<int> solution(vector<int> answerSheet) {
    vector <int> test1 {1,2,3,4,5};
    vector <int> test2 {2, 1, 2, 3, 2, 4, 2, 5};
    vector <int> test3 {3, 3, 1, 1, 2, 2, 4, 4, 5, 5};
}
```

To grade the test, the correct answers are compared with answerSheet. If the size of correct answers is larger or smaller than answerSheet, it will make index error. So, we can use property of `Modulus operation`.

**Note:** The result of the modulus operation is 0 ~ N-1.
{: .notice--info}

```cpp
int user1=0;
int user2=0;
int user3=0;

for(int i=0; i<answerSheetheet.size(); i++){
  if(test1[i%5] == answerSheet[i]) user1++;
  if(test2[i%8] == answerSheet[i]) user2++;
  if(test3[i%10] == answerSheet[i]) user3++;
  }
```

Now, we can iterate three vectors at the same time and count the number of right answers for each test takers.

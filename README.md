# C++作业
## 2.23
    不能判断指针p是否指向了一个合法的对象。因为不知道p是否已经被初始化。
## 2.24
    void *是特殊的指针，可以存放任意对象的地址。指针lp和i两者类型不一致，所以非法。
## 2.25
    (a)ip和i都是int型的指针，r是int型的引用。
    (b)i是int型的变量，ip是一个空指针。
    (c)ip是int型的指针， ip2是int型变量。
## 2.35
    j是int型变量；k是int型引用；p是int型指针；j2是int型变量；k2是int型引用。
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    const int i = 42;
    auto j = i;
    const auto &k = i;
    auto *p = &i;
    const auto j2 = i, &k2 = i;
    cout << typeid(i).name() << endl;
    cout << typeid(j).name() << endl;
    cout << typeid(k).name() << endl;
    cout << typeid(p).name() << endl;
    cout << typeid(j2).name() << endl;
    cout << typeid(k2).name() << endl;
    return 0;
}

 ```
## 3.4
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    string a, b;
    cin >> a >> b;
    if(a == b)
        cout << "a、b大小相等";
    else
        cout << max(a, b);
    return 0;
}
```
改写：
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    string a, b;
    cin >> a >> b;
    if(a.size() == b.size())
        cout << "a、b长度相等";
    else if(a.size() > b.size())
        cout << a;
    else
        cout << b;
    return 0;
}
```
## 3.5
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    string s, S;
    while(getline(cin, s))
    {
        S += s;
        cout << S;
    }

    return 0;
}
```
修改：
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    string s, S;
    while(getline(cin, s))
    {
        S += s + ' ';
        cout << S;
    }

    return 0;
}
```
## 3.20
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    vector<int> a;
    int i, x, sum = 0;
    cin >> x;
    a.push_back(x);
    for(i = 1; i <= 999; i++)
    {
        sum = 0;
        cin >> x;
        a.push_back(x);
        sum = a[i - 1] + a[i];
        cout << sum << ' ';
    }
    return 0;
}
```
改写：
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    vector<int> a;
    int i, x, sum = 0;
    for(i = 0; i <= 999; i++)
    {
        cin >> x;
        a.push_back(x);
    }
    for(i = 0; i <= 499; i++)
    {
        sum = 0;
        sum = a[i] + a[999 - i];
        cout << sum << ' ';
    }
    return 0;
}
```
## 3.23
```C++
#include<bits/stdc++.h>
using namespace std;
int main() {
    vector<int> a;
    int i, x, sum = 0;
    for(i = 0; i <= 9; i++)
    {
        cin >> x;
        a.push_back(x);
    }
    auto n = a.begin();
    for(i = 0; i <= 9; i++)
    {
        *n *= 2;
        n++;
        cout << a[i] << ' ';
    }
    return 0;
}
```

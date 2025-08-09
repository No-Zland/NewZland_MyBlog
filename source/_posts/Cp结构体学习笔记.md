---
title: Cp结构体学习笔记
date: 2025-08-07 14:27:19
tags:
---

1. 下列关于结构体变量操作中正确的是_____。
```c
struct student
{
   char num[10];
   char name[20], sex;
   int age;
   float score[3];
   float ave;
};
```
A、`stu2={"2008002","GaoPing",'M',18,86.3,80.5,89.4,85.4};`

B、`struct student stu1={"2008001","LiNing",'M',19,84.3,82.5,89.4,85.4};`

C、`if(stu1==stu2)`

D、`printf("%10s%20s%c%3d%4.1f%4.1f%4.1f%4.1",stu1);`

我的答案：B


2. 若有以下结构体定义，则选择（）赋值是正确的。
```c
struct s
{
        int x;
        int y;
}vs;
```
A、`s.x = 10`

B、`s.vs.x = 10`

C、`struct  va; va.x = 10`

D、`struct s va = {10}`

我的答案：D


3. 已知学生记录描述：
```c
struct student
{
    int  no;
    char name[20];
    char sex;
    struct
    {
            int  year;
            int  month;
            int  day;
    }birth;
}s;
```
设变量s的生日为2022年11月22日，对生日赋值正确的是（   ）

A、`year = 2022； month = 11； day = 22;`

B、`birth.year = 2022; birth.month = 11; birth.day =22;`

C、`s.year = 2022; s.month = 11; s.day =22;`

D、`s.birth.year = 2022; s.birth.month = 11; s.birth.day =22;`

我的答案：D


4. 已知有如下结构体定义，且有`p=&data`，则对data中的成员a的正确引用是（）
```c
struct sk
{
        int a;
        float b;
}data,*p
```
A、`(*p).data`

B、`(*p).a`

C、`p->data.a`

D、`p.data.a`

我的答案：B


5. 若有以下说明语句：
```c
struct student
{ 
    int num;
    char name[ ];
    float score;
}stu;
```
则下面的叙述不正确的是（）

A、struct是结构体类型的关键字

B、struct student 是用户定义的结构体类型

C、num, score都是结构体成员名

D、stu是用户定义的结构体类型名

我的答案：D


6. 若有以下说明语句：
```c
struct date
{ 
        int year;
        int month;
        int day;
}brithday;
```
则下面的叙述不正确的是（）

A、struct是声明结构体类型时用的关键字

B、struct date 是用户定义的结构体类型名

C、brithday是用户定义的结构体类型名

D、year,day 都是结构体成员名

我的答案：C


7. 以下对结构变量stu1中成员age的非法引用是（）
```c
struct student
{
        int age；
        int num；
}stu1,*p；
p=&stu1；
```
A、`stu1.age`

B、`student.age`

C、`p->age`

D、`(*p).age`

我的答案：B


8. 假设有以下的C语言代码：
```c
typedef struct
{ 
        int id;
        char name[50]; 
} Student; 

void printInfo(Student *s) 
{ 
        printf("ID: %d, Name: %s\n", s->id, s->name);
} 

int main() 
{ 
        Student s1 = {1, "Alice"};
        printInfo(&s1);
        return 0;
}
```
关于这段代码，以下说法正确的是()

A、printInfo函数不能直接访问s1的id和name成员

B、printInfo(&s1)调用是错误的，因为它传递了一个结构体而不是指针

C、printInfo函数通过结构体指针s访问了s1的id和name成员

D、如果将printInfo函数的参数改为Student s，则printInfo(s1);的调用将比printInfo(&s1);更快

我的答案：C


9. 下列代码中，（）接收一个指向Student结构体的指针，并打印其id和name？
```c
typedef struct {  
   int id;  
   char name[50];  
} Student;
```
A、`void print(Student s) { /* ... */ }`

B、`void print(Student* s) { printf("%d, %s\n", s->id, s->name); }`

C、`void print(Student s*) { /* ... */ }`

D、`void print(Student *s) { printf("%d, %s\n", s.id, s.name); }`

我的答案：B


10. 下列代码中，（）选项正确地通过指针p修改了结构体s的name成员？
```c
typedef struct {  
   char name[50];  
} MyStruct;  

MyStruct s = {"old_name"};  
MyStruct *p = &s;
```
A、`p->name = "new_name";`

B、`*p.name = "new_name";`

C、`strcpy(p->name, "new_name");`

D、`p = "new_name";`

我的答案：C


11. 已知有如下定义：
```c
struct
{
int x;
int y;
}s[2] = {{1,2},{3,4}},*p=s;
```
则表达式`++p->x`的值为___,表达式`(++p)->x`的值为_____。

我的答案：2、3


12. 设有以下说明语句：
```c
typedef struct stu
{ int a;
  float b;
} stutype;
```
则stutype是用户定义的结构体____。

我的答案：类型名


13. 假设有一个结构体类型Person，其中包含两个成员：int age和char name[50]。请填写以下代码，使其能够创建一个Person类型的变量p，并声明一个指向该变量的指针ptr，然后通过指针修改p的age成员。
```c
typedef struct {  
   int age;  
   char name[50];  
} Person;  

Person p;  
Person *ptr = _________; // 指向p  
ptr->age = 30; // 修改p的age成员
```

我的答案：&p


14. 假设有一个结构体类型Student，现在有一个指向Student的指针stuPtr。如果要将这个指针设置为指向新分配的内存，应使用________函数？
```c
typedef struct {  
   // ... 结构体成员 ...  
} Student;  

Student *stuPtr = ______(sizeof(Student)); // 填写代码以分配内存
```

我的答案：malloc


15. 假设有一个结构体类型Data，现在有一个Data类型的数组dataArray，以及一个指向Data的指针dataPtr。要让dataPtr指向dataArray的第一个元素，应如何赋值。（只需填写表达式）
```c
typedef struct {  
   // ... 结构体成员 ...  
} Data;  

Data dataArray[10];  
Data ______ = ______; // 填写表达式
```

我的答案：*dataPtr、&dataArray[0]


16. 对于结构体类型的变量，我们只能通过其成员的名字直接访问它的成员，而不能通过指针访问。

我的答案：错误


17. 结构体指针在声明时不需要指定结构体的大小，只需要指定指针的类型。

我的答案：正确


18. 如果一个结构体指针被赋值为NULL，那么它就不能再被重新指向一个有效的结构体变量。

我的答案：错误


19. 使用malloc函数为结构体分配内存后，必须手动调用free函数来释放这块内存，否则会导致内存泄漏。

我的答案：正确


20. 如果一个结构体指针指向了某个结构体变量，那么修改这个指针所指向的内容也会修改该结构体变量的内容。

我的答案：正确


21. 设计一个程序，输入五个学生的信息，包括学号（整型）、姓名（字符串）、数学成绩（浮点型）、计算机成绩（浮点型），之间1个空格间隔。程序需要计算每个学生的平均分（取两位小数）和总分，并按照总分从高到低对学生进行排序。如果总分相同，则按照学号从小到大排序。最后需要输出排序前、后的结果。

定义结构体来存储学生信息；使用数组来存储五个学生的结构体变量；编写函数来计算每个学生的总分和平均分；使用冒泡排序或其他排序算法对学生数组进行排序，注意总分相同时要按学号排序；输出排序前、后的学生信息。

标准输入样例：
```
1 ZhangSan 85.5 90  
2 LiSi 92 88.5  
3 WangWu 88 92  
4 ZhaoLiu 90 90  
5 SunQi 89.5 87
```

部分格式（直接复制，不要自己写否则会引起全半角不一致等问题）
```c
scanf("%d %s %f %f",********************);

printf("学号: %d, 姓名: %s, 数学成绩: %.1f, 计算机成绩: %.1f, 总分: %.1f, 平均分: %.2f\n",**************************);  

printf("排序前：\n"); 

printf("\n排序后：\n");
```

标准输出样例：
```
排序前： 

学号: 1, 姓名: ZhangSan, 数学成绩: 85.5, 计算机成绩: 90.0, 总分: 175.5, 平均分: 87.75 

学号: 2, 姓名: LiSi, 数学成绩: 92.0, 计算机成绩: 88.5, 总分: 180.5, 平均分: 90.25 

学号: 3, 姓名: WangWu, 数学成绩: 88.0, 计算机成绩: 92.0, 总分: 180.0, 平均分: 90.00 

学号: 4, 姓名: ZhaoLiu, 数学成绩: 90.0, 计算机成绩: 90.0, 总分: 180.0, 平均分: 90.00 

学号: 5, 姓名: SunQi, 数学成绩: 89.5, 计算机成绩: 87.0, 总分: 176.5, 平均分: 88.25 

排序后： 

学号: 2, 姓名: LiSi, 数学成绩: 92.0, 计算机成绩: 88.5, 总分: 180.5, 平均分: 90.25 

学号: 3, 姓名: WangWu, 数学成绩: 88.0, 计算机成绩: 92.0, 总分: 180.0, 平均分: 90.00 

学号: 4, 姓名: ZhaoLiu, 数学成绩: 90.0, 计算机成绩: 90.0, 总分: 180.0, 平均分: 90.00 

学号: 5, 姓名: SunQi, 数学成绩: 89.5, 计算机成绩: 87.0, 总分: 176.5, 平均分: 88.25 

学号: 1, 姓名: ZhangSan, 数学成绩: 85.5, 计算机成绩: 90.0, 总分: 175.5, 平均分: 87.75
```

```c
#include <stdio.h>

struct S {
    int id;
    char n[20];
    float m;
    float c;
    float t;
    float a;
};

int main() {
    struct S s[5];
    int i = 0;
    while (i < 5) {
        scanf("%d %s %f %f\n", &s[i].id, s[i].n, &s[i].m, &s[i].c);
        s[i].t = s[i].m + s[i].c;
        s[i].a = s[i].t / 2;
        i++;
    }

    printf("排序前：\n");
    i = 0;
    while (i < 5) {
        printf("学号: %d, 姓名: %s, 数学成绩: %.1f, 计算机成绩: %.1f, 总分: %.1f, 平均分: %.2f\n", 
               s[i].id, s[i].n, s[i].m, s[i].c, s[i].t, s[i].a);
        i++;
    }

    int j = 0;
    while (j < 4) {
        i = 0;
        while (i < 4 - j) {
            if (s[i].t < s[i+1].t || 
                (s[i].t == s[i+1].t && s[i].id > s[i+1].id)) {
                struct S tmp = s[i];
                s[i] = s[i+1];
                s[i+1] = tmp;
            }
            i++;
        }
        j++;
    }

    printf("\n排序后：\n");
    i = 0;
    while (i < 5) {
        printf("学号: %d, 姓名: %s, 数学成绩: %.1f, 计算机成绩: %.1f, 总分: %.1f, 平均分: %.2f\n", 
               s[i].id, s[i].n, s[i].m, s[i].c, s[i].t, s[i].a);
        i++;
    }

    return 0;
}
```

![img](tmp/125212803074_docx.datword_media_image1.gif)


22. 请编写程序实现以下功能：
(1) 定义一个结构体类型，其中成员包括年、月、日；
(2) 编写函数days()，用于计算本日是本年中的第几天。

注意闰年问题

输入格式请参考：
```c
scanf("%d %d %d", *************);
```
```
2023 3 15
```

输出格式请参考：
```c
printf("%d年%d月%d日是本年中的第%d天\n",*********************************);
```
```
2023年3月15日是本年中的第74天
```

本实验过程中的测试用例：
```
2023 3 15
2020 2 29
2022 12 31
```

```c
#include <stdio.h>

struct D {
    int y;
    int m;
    int d;
};

int ds(struct D dd) {
    int md[12] = {31,28,31,30,31,30,31,31,30,31,30,31};
    int t = dd.d;
    
    if (dd.y % 4 == 0 && (dd.y % 100 != 0 || dd.y % 400 == 0)) {
        md[1] = 29;
    }
    
    for (int i = 0; i < dd.m - 1; i++) {
        t += md[i];
    }
    
    return t;
}

int main() {
    struct D dd;
    scanf("%d %d %d", &dd.y, &dd.m, &dd.d);
    int d = ds(dd);
    printf("%d年%d月%d日是本年中的第%d天\n", dd.y, dd.m, dd.d, d);
    return 0;
}
```

![img](tmp/125212803074_docx.datword_media_image1.gif)


23. 结构体指针和结构体变量在内存中的存储方式是一样的。

我的答案：错误


24. 给定以下结构体和指针的声明：
```c
typedef struct
{  
   char *name;  
   int value;  
} Item;  
Item items[3] = {{"Apple", 5}, {"Banana", 10}, {"Cherry", 15}};  
Item *p = items;
```
以下（）表达式可以访问Banana的value？

A、`p[1].value`

B、`p->value + 1`

C、`*(p + 1)->value`

D、`((p + 1)->value)`

我的答案：A


25. 考虑以下结构体和指针的声明：
```c
typedef struct
 {  
   int id;  
   float score;  
} Student;   
Student students[5];  
Student *ptr = students;
```
在以下循环中，（）可以通过指针ptr遍历整个students数组？

A、
```c
for (int i = 0; i < 5; i++) {  
   printf("%d %f\n", ptr->id, ptr->score);  
   ptr = ptr + sizeof(Student); 
}
```

B、
```c
for (int i = 0; i < 5; i++) {  
   printf("%d %f\n", ptr[i].id, ptr[i].score);  
}
```

C、
```c
for (int i = 0; i < 5; i++) {  
   printf("%d %f\n", *ptr.id, *ptr.score);  
   ptr++;  
}
```

D、
```c
for (int i = 0; i < 5; i++) {  
   printf("%d %f\n", *ptr->id, *ptr->score);  
   ptr = ptr + 1;  
}
```

我的答案：B


26. 假设有以下结构体定义：
```c
typedef struct
{  
   int id;  
   char name[50];  
   float score;  
} Student;  
Student student1 = {1, "Alice", 90.5};
```
有一个指向该结构体的指针p，请填写初始化该指针的代码：

`Student *p = __________。`

我的答案：&student1


27. 给定一个结构体Person，其中包含了name（姓名）和age（年龄）两个成员。现有一个Person类型的数组people，数组长度为5。请补充下面的代码，使得程序能够遍历数组people，并输出每个人的姓名和年龄，如果某个人的年龄等于30，则输出"This person is 30 years old."。
```c
#include <stdio.h>  
#include <string.h>  
typedef struct
{  
   char name[50];  
   int age;  
} Person;  
int main()
 {  
   Person people[5] = {  
       {"Alice", 25},  
       {"Bob", 30},  
       {"Charlie", 20},  
       {"David", 30},  
       {"Eve", 35}  
   };  
   for (int i = 0; i < 5; i++) {  
       printf("Name: %s, Age: %d\n", people[i].name, people[i].age);  
       if (_______==30) { // 请在此处填写合适的条件表达式  
           printf("This person is 30 years old.\n");  
       }  
   }  
   return 0;  
}
```

我的答案：people[i].age


28. 给定以下结构体指针数组的定义和初始化：
```c
Student *studentsPtr[3];  
studentsPtr[0] = &student1;

// 假设student1是之前定义的Student结构体变量  
// 假设studentsPtr[1]和studentsPtr[2]也被初始化为指向有效的Student结构体
```
现在，我们想通过遍历这个指针数组并打印出每个学生的id，请填写循环体内的代码：
```c
for (int i = 0; i < 3; i++)
{  
   printf("%d\n", __________->id);  
}
```

我的答案：studentsPtr[i]


29. 假设有一个结构体指针ptr，它指向一个包含int和char数组的结构体。现在想要通过ptr访问结构体中的int成员，并将其值设置为100。请填写相关代码：
```c
typedef struct
{  
   int number;  
   char text[50];  
} MyStruct;  
MyStruct *ptr = (MyStruct * )malloc(sizeof(MyStruct));  
if (ptr != NULL) {  
   // 填写代码来设置ptr指向的结构体中的number成员为100  
   __________ = 100;  
   // ... 其他操作 ...  
   free(ptr);  
}
```

我的答案：ptr->number


30. 假设有一个结构体Person，其中包含一个指向另一个结构体Address的指针。现在有一个指向Person结构体的指针p，我们想要通过p来修改Address结构体中的street成员。请填写相关代码：
```c
typedef struct
{  
   char street[100];  
   int number;  
} Address;  
typedef struct
{  
   char name[50];  
   Address *address;  
} Person;   
Person *p = (Person * )malloc(sizeof(Person));  
if (p != NULL) {  
   p->address = (Address * )malloc(sizeof(Address));  
   if (p->address != NULL) {  
       // 填写代码来设置p指向的Person结构体中的address成员的street成员为"123 Main St"  
       strcpy(__________, "123 Main St");  
       // ... 其他操作 ...  
       free(p->address);  
   }  
   free(p);  
}
```

我的答案：p->address->street


31. 判断以下代码段是否正确：
```c
typedef struct
{  
   int id;  
   char name[50];  
} Person;  
void printPerson(Person *person)
{  
   printf("ID: %d, Name: %s\n", person->id, person->name);  
}  
int main()
{  
   Person person1 = {1, "Alice"};  
   printPerson(&person1); // 调用printPerson函数并传入person1的地址  
   Person *ptr = &person1;  
   printf("ID: %d, Name: %s\n", ptr->id, ptr->name); // 直接使用ptr访问person1的成员  
   return 0;  
}
```

我的答案：正确
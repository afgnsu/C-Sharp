# 07-1 撰寫類別(class)

#### (1) 專案架構 

```
專案
  |__ Employee.cs  
  |__ MainClass.cs  
```


#### (2-1) Student.cs

```
namespace Ntub.Imd
{
    public class Employee
    {
        //----------------------
        // 成員, member
        //----------------------
        public string name;
        public char rank;
        public int workHours;
    }
}
```


#### (2-2) MainClass.cs

```
using System;
using Ntub.Imd;

class MainClass 
{
    public static void Main(string[] args)
    {
        Employee s = new Employee();
        
        s.name="tommy";
        s.rank='A';
        s.workHours=100;
        
        Console.WriteLine("name:{0}", s.name);
        Console.WriteLine("rank:{0}", s.rank);
        Console.WriteLine("working hours:{0}", s.workHours);        
    }    
}
```

#### (3) 執行結果

```
name:tommy
rank:A
working hours:100
```


#### (4) 注意事項
```
1. 類別中包括成員及方法, 或是其中之一.
2. 
```

# 07-2 類別的private成員

#### (1) 專案架構 

```
專案
  |__ Employee.cs  
  |__ MainClass.cs  
```


#### (2-1) Employee.cs

```
namespace Ntub.Imd
{
    public class Employee
    {
        //------------------------------
        // 成員
        //------------------------------
        private string name;
        private char rank;
        private int workHours;

        //------------------------------
        // 建構元
        //------------------------------        
        public Employee(string name, char rank, int workHours)
        {
            setName(name);
            setRank(rank);
            setWorkHours(workHours);
        }
        
        //------------------------------
        // getters
        //------------------------------        
        public string getName(){return this.name;}
        public char getRank(){return this.rank;}
        public int getWorkHours(){return this.workHours;}
        
        //------------------------------
        // setters
        //------------------------------          
        public void setName(string name){this.name=name;}
        public void setRank(char rank){this.rank=rank;}
        public void setWorkHours(int workHours)
        {
             if(workHours>=0)
            {
                this.workHours=workHours;   
            }
            else
            {
                this.workHours=0;
            }           
        }
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
        Employee s = new Employee("tommy", 'A', -100);
        
        Console.WriteLine("name:{0}", s.getName());
        Console.WriteLine("rank:{0}", s.getRank());
        Console.WriteLine("working hours:{0}", s.getWorkHours());        
    }    
}
```

#### (3) 執行結果

```
name:tommy
rank:A
working hours:0
```


#### (4) 注意事項
```
1. 類別中的private無法直接取存, 可用建構元或getter, setter方法取存.
2. 建構元是一種特別的方法, 它的名稱必須和類別名稱一樣, 它在物件生成後自動執行.
```

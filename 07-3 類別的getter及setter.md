# 07-3 類別的getter及setter

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
        private string _name;
        private char _rank;
        private int _workHours;
        
        //------------------------------
        // getter及setter
        //------------------------------        
        public string name {set; get;}
        public char rank{set; get;}
        public int workHours
        {
            set
            {
                if(value>=0) {this._workHours=value;}
                else {this._workHours=0;} 
            }
            
            get
            {
                return this._workHours;
            }
        }

        //------------------------------
        // 建構元
        //------------------------------        
        public Employee(string name, char rank, int workHours)
        {
            this.name=name;
            this.rank=rank;
            this.workHours=workHours;
        }

        //------------------------------
        // 建構元
        //------------------------------         
        public Employee(){}
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
        s.workHours=-100;
        
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
working hours:0
```


#### (4) 注意事項
```
1. 以類似直接取用的方式成員呼叫getter及setter.
2. setter中的value是成員的設定值.
```

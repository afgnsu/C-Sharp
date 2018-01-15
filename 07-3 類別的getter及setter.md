# 07-3 類別的getter及setter

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
        //------------------------------
        // 成員
        //------------------------------
        private string _name;
        public string name {set; get;}
        
        private char _rank;
        public char rank{set; get;}
        
        private int _workHours;
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
        // 建構元(1)
        //------------------------------        
        public Employee(string name, char rank, int workHours)
        {
            this.name=name;
            this.rank=rank;
            this.workHours=workHours;
        }

        //------------------------------
        // 建構元(2)
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

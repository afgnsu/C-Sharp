# 08-5 父親的參考-兒子的實體-用override

#### (1) 專案架構 

```
專案
  |__ Staff.cs 
  |__ Driver.cs  
  |__ MainClass.cs  
  
   ______________
  | Staff        |
  |______________|
  |              |
  | + Salary()   |
  |______________|  父親, Base Class
         |
   ______|_______
  | Driver       |
  |______________|
  |              |
  | + Salary()   |
  |______________|  兒子, Derived Class  
  
```


#### (2-1) Staff.cs

```
namespace Ntub.Imd
{
    class Staff
    {
        //------------------------
        // 成員
        //------------------------
        public string no;
        public string name;
        public string rank;
        
        //------------------------
        // 建構元
        //------------------------
        public Staff(string no, string name, string rank)
        {
            this.no = no;
            this.name = name;
            this.rank = rank;
        }
        
        //------------------------
        // 方法
        //------------------------        
        public virtual int Salary()
        {
            if(this.rank.Equals("A"))
            {
                return 50000;
            }
            else if(this.rank.Equals("B"))
            {
                return 40000;
            }
            else
            {
                return 30000;
            }
        }        
    }
}
```


#### (2-2) Driver.cs

```
namespace Ntub.Imd
{
    class Driver : Staff
    {
        //------------------------
        // 成員
        //------------------------
        public string license;
        public string phoneNo;
        
        
        //------------------------
        // 建構元
        //------------------------
        public Driver(string no, string name, string rank, string license, string phoneNo) : base(no, name, rank)
        {
            this.license = license;
            this.phoneNo = phoneNo;
        } 
        
        //------------------------
        // 方法
        //------------------------        
        public override int Salary()
        {
            return base.Salary() + 3000;
        }
        
    }
}
```



#### (2-3) MainClass.cs

```
using System;
using Ntub.Imd;

class MainClass 
{
    public static void Main(string[] args)
    {
        //-----------------------------------------
        // 生成一個司機的實體, 但是用員工的參考
        //-----------------------------------------
        Staff s3 = new Driver("E003", "smith", "C", "AB0003", "0911333444");
        
        Console.WriteLine("no:{0}", s3.no);
        Console.WriteLine("name:{0}", s3.name);
        Console.WriteLine("rank:{0}", s3.rank);
        Console.WriteLine("salary:{0}", s3.Salary()); 
    }    
}
```

#### (3) 執行結果

```
no:E003
name:smith
rank:C
salary:33000
```


#### (4) 注意事項
```
1. 如果兒子用override修飾與父親同名的Salary()方法, 那麼父親的Salary()要用virtual修飾.
2. 以override修飾後, 父親參考呼叫的Salary(), 是兒子的Salary()內容.
```

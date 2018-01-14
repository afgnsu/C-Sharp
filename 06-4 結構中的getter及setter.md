# 06-4 結構中的getter及setter

#### (1) 專案架構 

```
專案
  |__ Student.cs  
  |__ MainClass.cs  
```


#### (2-1) Student.cs

```
namespace Ntub.Imd
{
    public struct Student
    {
        //--------------------------
        // 欄位, getter, setter
        //--------------------------
        public string name;

        //--------------------------
        // 欄位
        //--------------------------       
        private char _gender;
        
        //--------------------------
        // getter, setter
        //--------------------------       
        public char gender
        {
            get{return this._gender;}
            set
            {
                if(value!='M' && value!='F')
                    this._gender='F';
                else
                    this._gender=value;
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
        Student s = new Student();

        s.name="tommy";
        s.gender='A';
        
        Console.WriteLine("name:{0}", s.name);
        Console.WriteLine("gender:{0}", s.gender);
    }    
}
```

#### (3) 執行結果

```
name:tommy
gender:F
```


#### (4) 注意事項
```
1. 使用getter及setter可以在設定及取出欄位前進行某些處理.
2. 在欄位名稱前加上底線, 如_gender, 有隱含private的意義.
```

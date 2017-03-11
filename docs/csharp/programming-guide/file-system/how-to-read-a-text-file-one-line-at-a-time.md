---
title: "방법: 텍스트 파일을 한 번에 한 줄씩 읽기(Visual C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "텍스트 파일 읽기, 한 줄씩"
  - "ReadLine 메서드[C#]"
  - "텍스트 파일[C#]"
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# 방법: 텍스트 파일을 한 번에 한 줄씩 읽기(Visual C#)
이 예제에서는 `StreamReader` 클래스의 `ReadLine` 메서드를 사용하여 텍스트 파일의 내용을 한 번에 한 줄씩 문자열로 읽어 들입니다.  각 텍스트 줄은 `line` 문자열에 저장되고 화면에 표시됩니다.  
  
## 예제  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## 코드 컴파일  
 코드를 복사한 다음 콘솔 응용 프로그램의 `Main` 메서드에 붙여넣습니다.  
  
 `"c:\test.txt"`를 실제 파일 이름으로 바꿉니다.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   파일이 없는 경우  
  
## .NET Framework 보안  
 파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.  예를 들어, `myFile.cs`가 C\# 소스 파일이 아닐 수도 있습니다.  
  
## 참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)
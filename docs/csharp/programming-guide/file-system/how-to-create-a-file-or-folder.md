---
title: "방법: 파일 또는 폴더 만들기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "파일 만들기[C#]"
  - "폴더 만들기[C#]"
  - "파일[C#]"
  - "폴더[C#]"
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# 방법: 파일 또는 폴더 만들기(C# 프로그래밍 가이드)
프로그램으로 컴퓨터에 폴더를 만들고, 하위 폴더를 만들고, 하위 폴더에 특정 파일을 만든 다음, 해당 파일에 데이터를 쓸 수 있습니다.  
  
## 예제  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 폴더가 이미 있을 경우 <xref:System.IO.Directory.CreateDirectory%2A>는 아무 작업도 수행하지 않으며 예외가 throw되지 않습니다.  그러나 <xref:System.IO.File.Create%2A?displayProperty=fullName>이 기존 파일을 새 파일로 바꿉니다.  예제는 기존 파일이 대체되지 않도록 `if`\-`else` 문을 사용합니다.  
  
 예제를 다음과 같이 변경하여 특정 이름을 가진 파일이 이미 있는지 여부를 기준으로 다른 결과를 지정할 수 있습니다.  이러한 파일이 없으면 코드가 파일을 하나 만듭니다.  이러한 파일이 있으면 코드가 파일에 데이터를 추가합니다.  
  
-   non\-random 파일 이름을 지정합니다.  
  
    ```c#  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
  
    ```  
  
-   `if`\-`else` 문을 다음 코드의 `using` 문으로 바꿉니다.  
  
    ```c#  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
  
    ```  
  
 데이터가 파일에 추가될 때마다 확인하려면 예제를 여러 번 실행합니다.  
  
 사용자가 시도할 수 있는 더 많은 `FileMode` 값은 <xref:System.IO.FileMode>을 참조하십시오.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   폴더 이름의 형식이 잘못된 경우.  예를 들어, 파일 이름에 잘못된 문자가 포함되어 있거나 파일 이름이 공백인 경우\(<xref:System.ArgumentException> 클래스\)  <xref:System.IO.Path> 클래스를 사용하여 유효한 경로 이름을 만듭니다.  
  
-   만들 폴더의 부모 폴더가 읽기 전용인 경우\(<xref:System.IO.IOException> 클래스\)  
  
-   폴더 이름이 `null`인 경우\(<xref:System.ArgumentNullException> 클래스\)  
  
-   폴더 이름이 너무 긴 경우\(<xref:System.IO.PathTooLongException> 클래스\)  
  
-   폴더 이름이 콜론 ":"인 경우\(<xref:System.IO.PathTooLongException> 클래스\)  
  
## .NET Framework 보안  
 부분 신뢰 상황에서는 <xref:System.Security.SecurityException> 클래스의 인스턴스가 throw될 수 있습니다.  
  
 폴더를 만들 권한이 없는 경우에는 예제에서 <xref:System.UnauthorizedAccessException> 클래스의 인스턴스가 throw됩니다.  
  
## 참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)
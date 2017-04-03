---
title: "방법: 파일 또는 폴더 만들기(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bba53c8d175d95aa3b89ba458517d439a8d2bb11
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a>방법: 파일 또는 폴더 만들기(C# 프로그래밍 가이드)
프로그래밍 방식으로 컴퓨터에 폴더를 만들고, 하위 폴더를 만들고, 하위 폴더에 파일을 만들고, 파일에 데이터를 쓸 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 폴더가 이미 있는 경우 <xref:System.IO.Directory.CreateDirectory%2A>는 아무 작업도 수행하지 않으며 예외가 throw되지 않습니다. 그러나 <xref:System.IO.File.Create%2A?displayProperty=fullName>는 기존 파일을 새 파일로 바꿉니다. 이 예제에서는 `if`-`else` 문을 사용하여 기존 파일이 바뀌지 않도록 합니다.  
  
 예제에서 다음을 변경하여 특정 이름의 파일이 이미 있는지 여부에 따라 다른 결과를 지정할 수 있습니다. 파일이 없는 경우 코드에서 파일을 만듭니다. 파일이 있는 경우 코드에서 해당 파일에 데이터를 추가합니다.  
  
-   임의가 아닌 파일 이름을 지정합니다.  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
  
    ```  
  
-   다음 코드를 사용하여 `if`-`else` 문을 `using` 문으로 바꿉니다.  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
  
    ```  
  
 예제를 여러 번 실행하여 매번 파일에 데이터가 추가되는지 확인합니다.  
  
 시도할 수 있는 추가 `FileMode` 값은 <xref:System.IO.FileMode>를 참조하세요.  
  
 다음 조건에서 예외가 발생합니다.  
  
-   폴더 이름 형식이 잘못된 경우. 예를 들어 잘못된 문자를 포함하거나 공백만으로 이루어져 있습니다(<xref:System.ArgumentException> 클래스). <xref:System.IO.Path> 클래스를 사용하여 유효한 경로 이름을 만듭니다.  
  
-   만들 폴더의 부모 폴더가 읽기 전용인 경우(<xref:System.IO.IOException> 클래스)  
  
-   폴더 이름이 `null`인 경우(<xref:System.ArgumentNullException> 클래스)  
  
-   폴더 이름이 너무 긴 경우(<xref:System.IO.PathTooLongException> 클래스)  
  
-   폴더 이름이 콜론 ":"으로만 이루어진 경우(<xref:System.IO.PathTooLongException> 클래스)  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 부분 신뢰 상황에서는 <xref:System.Security.SecurityException> 클래스 인스턴스가 throw될 수 있습니다.  
  
 폴더를 만들 수 있는 권한이 없는 경우 예제에서 <xref:System.UnauthorizedAccessException> 클래스 인스턴스가 throw됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](../../../csharp/programming-guide/file-system/index.md)

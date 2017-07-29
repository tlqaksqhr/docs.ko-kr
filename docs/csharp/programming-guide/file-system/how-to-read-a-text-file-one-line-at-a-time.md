---
title: "방법: 텍스트 파일을 한 번에 한 줄씩 읽기(Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e9327181d82a97559c7be99bb76a2a93118d796b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>방법: 텍스트 파일을 한 번에 한 줄씩 읽기(Visual C#)
이 예제에서는 `StreamReader` 클래스의 `ReadLine` 메서드를 사용하여 텍스트 파일 내용을 한 번에 한 줄씩 문자열로 읽어옵니다. 각 텍스트 줄은 `line` 문자열에 저장되고 화면에 표시됩니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 복사하고 콘솔 응용 프로그램의 `Main` 메서드에 붙여넣습니다.  
  
 `"c:\test.txt"`를 실제 파일 이름으로 바꿉니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   파일이 없을 수 있는 경우  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다. 예를 들어 `myFile.cs` 파일이 C# 소스 파일이 아닐 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](../../../csharp/programming-guide/file-system/index.md)


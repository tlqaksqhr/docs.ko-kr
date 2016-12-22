---
title: "using 지시문(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using 지시문[C#]"
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# using 지시문(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`using` 지시문에는 다음 세 가지 용도가 있습니다.  
  
-   네임스페이스에서 형식 사용을 한정할 필요가 없도록 해당 네임스페이스에서 형식 사용을 허용합니다.  
  
    ```c#  
    using System.Text;  
    ```  
  
-   형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스하도록 허용합니다.  
  
    ```c#  
    using static System.Math;  
    ```  
  
-   네임스페이스 또는 형식에 대한 별칭을 만듭니다.  이를 *using 별칭 지시문*이라고 합니다.  
  
    ```c#  
    using Project = PC.MyCompany.Project;  
    ```  
  
 `using` 키워드는 파일 및 글꼴과 같은 <xref:System.IDisposable> 개체가 제대로 처리될 수 있게 도와주는 *using 문*을 만드는 데도 사용됩니다.  자세한 내용은 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.  
  
## 정적 형식 사용  
 형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스할 수 있습니다.  
  
```c#  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
  
```  
  
 `Using static`은 액세스 가능한 정적 멤버와 지정된 형식에 선언된 중첩된 형식만 가져옵니다.  상속된 멤버는 가져오지 않습니다.  using static 지시문을 사용하여 Visual Basic 모듈을 포함한 모든 명명된 형식에서 가져올 수 있습니다.  F\# 최상위 함수가 메타데이터에서 이름이 유효한 C\# 식별자인 명명된 형식의 정적 멤버로 나타나면 F\# 함수를 가져올 수 있습니다.  
  
 `Using static`을 사용하면 지정된 형식에 선언된 확장 메서드를 확장 메서드 조회에 사용할 수 있습니다.  그러나 확장 메서드의 이름은 코드의 정규화되지 않은 참조에 대한 범위로 가져오지 않습니다.  
  
 같은 컴파일 단위 또는 네임스페이스에서 여러 using static 지시문을 통해 다양한 형식에서 가져온 같은 이름을 사용하는 메서드는 메서드 그룹을 구성합니다.  이들 메서드 그룹 내에서 오버로드 확인은 일반 C\# 규칙을 따릅니다.  
  
## 설명  
 `using` 지시문의 범위는 지시문이 나타내는 파일로 제한됩니다.  
  
 `using` 별칭을 만들면 네임스페이스 또는 형식에 대한 식별자를 더 쉽게 한정할 수 있습니다.  using alias 지시문의 오른쪽은 지시문 앞에 나오는 using 지시문과 관계없이 항상 정규화된 형식이어야 합니다.  
  
 `using` 지시문을 만들어서 네임스페이스를 지정할 필요 없이 네임스페이스에서 이 형식을 사용합니다.  `using` 지시문은 지정한 네임스페이스에 중첩된 모든 네임스페이스에 대한 액세스 권한을 제공하지 않습니다.  
  
 네임스페이스는 두 가지 범주인 사용자 정의 및 시스템 정의로 구분됩니다.  사용자 정의 네임스페이스는 코드에서 정의된 네임스페이스입니다.  시스템 정의 네임스페이스 목록을 보려면 [.NET Framework 클래스 라이브러리](http://go.microsoft.com/fwlink/?LinkID=227195)를 참조하세요.  
  
 다른 어셈블리의 메서드를 참조하는 방법에 대한 자세한 내용은 [C\# DLL 만들기 및 사용](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  
  
## 예제 1  
  
### 설명  
 다음 예제에서는 `using` 네임스페이스에 대한 별칭을 정의 및 사용하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
### 메모  
 using alias 지시문의 오른쪽에는 공개 제네릭 형식이 포함될 수 없습니다.  예를 들어 List\<T\>에 대한 using alias를 만들 수 없지만 List\<int\>에 대한 using alias를 만들 수 있습니다.  
  
## 예제 2  
  
### 설명  
 다음 예제에서는 클래스에 대한 `using` 지시문 및 `using` 별칭을 정의하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)   
 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)
---
title: "using 지시문(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e91cc4fea9fbe57b257e17915cd28b3b82f12f6e
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="using-directive-c-reference"></a>using 지시문(C# 참조)
`using` 지시문에는 다음 세 가지 용도가 있습니다.  
  
-   네임스페이스에서 형식 사용을 한정할 필요가 없도록 해당 네임스페이스에서 형식 사용을 허용합니다.  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스하도록 허용합니다. 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    자세한 내용은 [using 정적 지시문](using-static.md)을 참조하세요.

-   네임스페이스 또는 형식에 대한 별칭을 만듭니다. 이를 *using 별칭 지시문*이라고 합니다.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 `using` 키워드는 파일 및 글꼴과 같은 <xref:System.IDisposable> 개체가 제대로 처리될 수 있게 도와주는 *using 문*을 만드는 데도 사용됩니다. 자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.  
  
## <a name="using-static-type"></a>정적 형식 사용  
 형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스할 수 있습니다.  
  
```csharp  
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
  
## <a name="remarks"></a>설명  
 `using` 지시문의 범위는 지시문이 나타내는 파일로 제한됩니다.  
  
 `using` 별칭을 만들면 네임스페이스 또는 형식에 대한 식별자를 더 쉽게 한정할 수 있습니다. using alias 지시문의 오른쪽은 지시문 앞에 나오는 using 지시문과 관계없이 항상 정규화된 형식이어야 합니다.  
  
 `using` 지시문을 만들어서 네임스페이스를 지정할 필요 없이 네임스페이스에서 이 형식을 사용합니다. `using` 지시문은 지정한 네임스페이스에 중첩된 모든 네임스페이스에 대한 액세스 권한을 제공하지 않습니다.  
  
 네임스페이스는 두 가지 범주인 사용자 정의 및 시스템 정의로 구분됩니다. 사용자 정의 네임스페이스는 코드에서 정의된 네임스페이스입니다. 시스템 정의 네임스페이스 목록을 보려면 [.NET Framework 클래스 라이브러리](http://go.microsoft.com/fwlink/?LinkID=227195)를 참조하세요.  
  
 다른 어셈블리의 메서드를 참조하는 방법에 대한 자세한 내용은 [C# DLL 만들기 및 사용](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)을 참조하세요.  
  
## <a name="example-1"></a>예제 1  
  
 다음 예제에서는 `using` 네임스페이스에 대한 별칭을 정의 및 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 using alias 지시문의 오른쪽에는 공개 제네릭 형식이 포함될 수 없습니다. 예를 들어 List\<T>에 대해서는 using 별칭을 만들 수 없지만 List\<int>에 대해서는 만들 수 있습니다.  
  
## <a name="example-2"></a>예제 2  
  
 다음 예제에서는 클래스에 대한 `using` 지시문 및 `using` 별칭을 정의하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)   
 [using 문](../../../csharp/language-reference/keywords/using-statement.md)


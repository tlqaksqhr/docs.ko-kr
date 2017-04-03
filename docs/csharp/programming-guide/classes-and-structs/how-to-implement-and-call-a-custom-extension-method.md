---
title: "방법: 사용자 지정 확장 메서드 구현 및 호출(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
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
ms.openlocfilehash: 9ba08e55e3bc07c2ce6369e2b33ccbe632545d24
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>방법: 사용자 지정 확장명 메서드 구현 및 호출(C# 프로그래밍 가이드)
이 항목에서는 [.NET Framework 클래스 라이브러리](http://go.microsoft.com/fwlink/?LinkID=217856)의 형식 또는 확장하려는 다른 .NET 형식에 대한 고유한 확장 메서드를 구현하는 방법을 보여 줍니다. 클라이언트 코드는 확장 메서드를 포함하는 DLL에 대한 참조를 추가하고 확장 메서드가 정의된 네임스페이스를 지정하는 [using](../../../csharp/language-reference/keywords/using-directive.md) 지시문을 추가하여 확장 메서드를 사용할 수 있습니다.  
  
## <a name="to-define-and-call-the-extension-method"></a>확장 메서드를 정의하고 호출하려면  
  
1.  확장 메서드가 포함될 정적 [클래스](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 정의합니다.  
  
     클래스가 클라이언트 코드에 표시되어야 합니다. 액세스 가능성 규칙에 대한 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.  
  
2.  최소한 포함하는 클래스와 동일한 표시 유형으로 확장 메서드를 정적 메서드로 구현합니다.  
  
3.  메서드의 첫 번째 매개 변수는 메서드가 작동하는 형식을 지정합니다. [this](../../../csharp/language-reference/keywords/this.md) 한정자가 앞에 와야 합니다.  
  
4.  호출 코드에 `using` 지시문을 추가하여 확장 메서드 클래스를 포함하는 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md)를 지정합니다.  
  
5.  형식의 인스턴스 메서드인 것처럼 메서드를 호출합니다.  
  
     연산자가 적용되는 형식을 나타내기 때문에 첫 번째 매개 변수는 호출 코드에서 지정되지 않고 컴파일러가 개체 형식을 이미 알고 있습니다. 매개 변수 2 ~ `n`에 대한 인수만 제공하면 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CustomExtensions.StringExtension` 클래스에 `WordCount`라는 확장 메서드를 구현합니다. 이 메서드는 첫 번째 메서드 매개 변수로 지정된 <xref:System.String> 클래스에 대해 작동합니다. `CustomExtensions` 네임스페이스를 응용 프로그램 네임스페이스로 가져오고, `Main` 메서드 내부에서 메서드가 호출됩니다.  
  
 [!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 실행하려면 코드를 복사하여 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)]에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다. 기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 `using` 지시문을 포함합니다. 이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.   
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 확장 메서드는 특정 보안 취약성은 없습니다. 형식 자체에서 정의된 인스턴스 또는 정적 메서드를 기준으로 모든 이름 충돌이 해결되기 때문에 확장 메서드를 사용하여 형식의 기존 메서드를 가장할 수는 없습니다. 확장 메서드는 확장된 클래스의 개인 데이터에 액세스할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [this](../../../csharp/language-reference/keywords/this.md)   
 [namespace](../../../csharp/language-reference/keywords/namespace.md)

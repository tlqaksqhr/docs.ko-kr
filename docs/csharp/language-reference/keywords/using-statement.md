---
title: "using 문(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 587e50d5c81c19d75e9d8bf4779064947a373b71
ms.lasthandoff: 03/13/2017

---
# <a name="using-statement-c-reference"></a>using 문(C# 참조)
<xref:System.IDisposable> 개체의 올바른 사용을 보장하는 편리한 구문을 제공합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 using 문을 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>주의  
 <xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스에 액세스하는 관리되는 형식의 예입니다(이 경우 파일 핸들 및 장치 컨텍스트). 다른 많은 종류의 관리되지 않는 리소스 및 이를 캡슐화하는 클래스 라이브러리 형식이 있습니다. 그러한 모든 형식은 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.  
  
 일반적으로 `IDisposable` 개체를 사용할 경우 `using` 문에서 선언 및 인스턴스화해야 합니다. `using` 문은 올바른 방법으로 개체에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하며, (앞서 설명한 대로 사용하는 경우) <xref:System.IDisposable.Dispose%2A>가 호출되자마자 개체 자체가 범위를 벗어나도록 만듭니다. `using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.  
  
 `using` 문을 사용하면 개체에서 메서드를 호출하는 동안 예외가 발생하더라도 <xref:System.IDisposable.Dispose%2A>가 호출됩니다. try 블록 내부에 개체를 배치하고 finally 블록에서 <xref:System.IDisposable.Dispose%2A>를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 컴파일러는 이 방법으로 `using` 문을 변환합니다. 이전의 코드 예제는 컴파일 시 다음 코드로 확장됩니다(개체의 제한된 범위를 만드는 여분의 중괄호 참고).  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 다음 예제와 같이 `using` 문에서 한 형식의 여러 인스턴스를 선언할 수 있습니다.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 리소스 개체를 인스턴스화한 후 `using` 문에 변수를 전달할 수 있지만, 이 방법이 최선은 아닙니다. 이 경우 관리되지 않는 리소스에 더 이상 액세스할 수 없더라도 제어가 `using` 블록을 벗어나면 개체는 범위에 남아 있게 됩니다. 다시 말해, 더 이상 완전히 초기화되지 않습니다. `using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 위험이 있습니다. 따라서 일반적으로 `using` 문에서 개체를 인스턴스화하고 `using` 블록에서 범위를 제한하는 것이 좋습니다.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)   
 [가비지 수집](../../../standard/garbagecollection/index.md)   
 [Dispose 메서드 구현](http://msdn.microsoft.com/library/eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9)

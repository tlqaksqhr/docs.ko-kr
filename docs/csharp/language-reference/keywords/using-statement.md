---
title: "using 문(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fdf37e1bfc57bf850b332f167e57d3e05d23e78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-c-reference"></a>using 문(C# 참조)
<xref:System.IDisposable> 개체의 올바른 사용을 보장하는 편리한 구문을 제공합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 using 문을 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>설명  
 <xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스에 액세스하는 관리되는 형식의 예입니다(이 경우 파일 핸들 및 장치 컨텍스트). 다른 많은 종류의 관리되지 않는 리소스 및 이를 캡슐화하는 클래스 라이브러리 형식이 있습니다. 이러한 형식은 모두 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.  
  
때의 수명을 `IDisposable` 개체는 단일 메서드를 제한, 선언 하 고에서 인스턴스화하는 `using` 문. `using` 문은 올바른 방법으로 개체에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하며, (앞서 설명한 대로 사용하는 경우) <xref:System.IDisposable.Dispose%2A>가 호출되자마자 개체 자체가 범위를 벗어나도록 만듭니다. `using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.  
  
 `using` 문을 사용하면 개체에서 메서드를 호출하는 동안 예외가 발생하더라도 <xref:System.IDisposable.Dispose%2A>가 호출됩니다. try 블록 내부에 개체를 배치하고 finally 블록에서 <xref:System.IDisposable.Dispose%2A>를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 컴파일러는 이 방법으로 `using` 문을 변환합니다. 이전의 코드 예제는 컴파일 시 다음 코드로 확장됩니다(개체의 제한된 범위를 만드는 여분의 중괄호 참고).  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 다음 예제와 같이 `using` 문에서 한 형식의 여러 인스턴스를 선언할 수 있습니다.  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 리소스 개체를 인스턴스화한 후 `using` 문에 변수를 전달할 수 있지만, 이 방법이 최선은 아닙니다. 이 경우 관리되지 않는 리소스에 더 이상 액세스할 수 없더라도 제어가 `using` 블록을 벗어나면 개체는 범위에 남아 있게 됩니다. 다시 말해, 더 이상 완전히 초기화되지 않습니다. `using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 위험이 있습니다. 따라서 일반적으로 `using` 문에서 개체를 인스턴스화하고 `using` 블록에서 범위를 제한하는 것이 좋습니다.  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
삭제에 대 한 자세한 내용은 `IDisposable` 개체 참조 [IDisposable을 구현 하는 개체를 사용 하 여](../../../standard/garbage-collection/using-objects.md)합니다.

## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)  
 [가비지 수집](../../../standard/garbage-collection/index.md)  
 [IDisposable을 구현하는 개체 사용](../../../standard/garbage-collection/using-objects.md)  
 [IDisposable 인터페이스](xref:System.IDisposable)

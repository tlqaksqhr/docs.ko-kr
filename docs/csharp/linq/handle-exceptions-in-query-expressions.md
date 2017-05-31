---
title: "쿼리 식의 예외 처리"
description: "쿼리 식의 예외를 처리하는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: d13387c4468a5c89cbe838139c767f0f95ab418d
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="handle-exceptions-in-query-expressions"></a>쿼리 식의 예외 처리

쿼리 식의 컨텍스트에서 모든 메서드를 호출할 수 있습니다. 그러나 데이터 소스의 내용을 수정하거나 예외를 throw하는 것과 같은 부작용이 생길 수 있는 쿼리 식에서는 메서드를 호출하지 않는 것이 좋습니다. 이 예제에서는 예외 처리에 대한 일반적인 .NET Framework 지침을 위반하지 않고 쿼리 식에서 메서드를 호출할 때 예외 발생을 방지하는 방법을 보여 줍니다. 해당 지침에 의하면 특정 컨텍스트에서 예외가 throw된 이유를 이해할 경우 이 예외를 catch할 수 있습니다. 자세한 내용은 [최선의 예외 구현 방법](../../standard/exceptions/best-practices-for-exceptions.md)을 참조하세요.  
  
 마지막 예제에서는 쿼리 실행 중에 예외를 throw해야 할 경우 사례를 처리하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 예외 처리 코드를 쿼리 식 외부로 이동하는 방법을 보여 줍니다. 이 작업은 메서드가 쿼리에 로컬인 변수에 의존하지 않는 경우에만 가능합니다.  
  
 [!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a>예제 

 몇몇 경우에는 쿼리 내에서 throw된 예외에 대한 가장 좋은 응답은 쿼리 실행을 즉시 중지하는 것입니다. 다음 예제에서는 쿼리 본문 내부에서 throw된 예외를 처리하는 방법을 보여 줍니다. `SomeMethodThatMightThrow`가 잠재적으로 쿼리 실행을 중지해야 하는 예외를 일으킬 수 있다고 가정합니다.  
  
 `try` 블록은 쿼리 자체가 아니라 `foreach` 루프를 포함합니다. 이는 쿼리가 실제로 실행되는 지점이 `foreach` 루프이기 때문입니다. 자세한 내용은 [LINQ 쿼리 소개](../programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.  
  
 [!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)

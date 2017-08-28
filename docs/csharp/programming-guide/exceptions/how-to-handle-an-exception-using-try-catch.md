---
title: "방법: try-catch를 사용하여 예외 처리(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
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
ms.openlocfilehash: f6f714cd1b652845e77405ff74fbfc860e71dc21
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>방법: try/catch를 사용하여 예외 처리(C# 프로그래밍 가이드)
[try-catch](../../../csharp/language-reference/keywords/try-catch.md) 블록은 작업 코드에서 생성된 예외를 catch하고 처리하기 위한 것입니다. 일부 예외는 `catch` 블록에서 처리될 수 있으며, 예외가 다시 throw되지 않고 문제가 해결됩니다. 그러나 대체로 수행할 수 있는 작업은 적절한 예외가 throw되었는지 확인하는 것뿐입니다.  
  
## <a name="example"></a>예제  
 이 예제에서 <xref:System.IndexOutOfRangeException>은 가장 적합한 예외가 아닙니다. 호출자가 전달한 `index` 인수로 인해 오류가 발생하기 때문에 <xref:System.ArgumentOutOfRangeException>이 메서드에 더 적합합니다.  
  
 [!code-cs[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## <a name="comments"></a>설명  
 예외가 발생하는 코드는 `try` 블록으로 묶여 있습니다. `IndexOutOfRangeException`이 발생할 경우 처리하기 위해 `catch` 문이 바로 뒤에 추가됩니다. `catch` 블록은 `IndexOutOfRangeException`을 처리하고 더 적합한 `ArgumentOutOfRangeException` 예외를 대신 throw합니다. 호출자에게 최대한 많은 정보를 제공하기 위해 원래 예외를 새 예외의 <xref:System.Exception.InnerException%2A>으로 지정하는 것이 좋습니다. <xref:System.Exception.InnerException%2A> 속성은 [readonly](../../../csharp/language-reference/keywords/readonly.md)이기 때문에 새 예외의 생성자에 할당해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/index.md)   
 [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)


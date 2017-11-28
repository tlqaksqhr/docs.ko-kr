---
title: "#<a name=\"undef-c-reference\"></a>undef(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#undef'
helpviewer_keywords: '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7a3c162c0ecb8bb39cc13a34dcd15fa3ce96ebb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="undef-c-reference"></a>#undef(C# 참조)
`#undef`를 사용하면 기호의 정의를 해제할 수 있습니다. 그러면 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문에서 해당 기호를 식으로 사용하여 식이 `false`로 평가됩니다.  
  
 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 지시문 또는 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션을 사용하여 기호를 정의할 수 있습니다. `#undef` 지시문은 지시문이 아닌 문을 사용하기 전에 파일에 나와야 합니다.  
  
## <a name="example"></a>예제  
  
```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
 **디버그가 정의되어 있지 않습니다.**  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)

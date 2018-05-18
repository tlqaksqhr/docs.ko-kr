---
title: '#region(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 88632b04ec8932e22f5bf7a23b8f0edf14d89f27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="region-c-reference"></a>#region(C# 참조)
`#region`을 사용하면 Visual Studio Code 편집기의 [개요 기능](/visualstudio/ide/outlining)을 사용할 때 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다. 더 긴 코드 파일에서 현재 작업 중인 파일 부분에 집중할 수 있도록 하나 이상의 영역을 축소하거나 숨길 수 있습니다. 다음 예제에서는 영역을 정의하는 방법을 보여 줍니다.  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>설명  
 `#region` 블록은 [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) 지시문으로 종료해야 합니다.  
  
 `#region` 블록은 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 블록과 겹칠 수 없습니다. 그러나 `#region` 블록을 `#if` 블록에 중첩할 수 있고 `#if` 블록을 `#region` 블록에 중첩할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)

---
title: "#region(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
dev_langs:
- CSharp
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
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
ms.openlocfilehash: 2924daffcdc44c8f5ba5cf97c5b141c0dd07ca4a
ms.lasthandoff: 03/13/2017

---
# <a name="region-c-reference"></a>#region(C# 참조)
`#region`을 사용하면 Visual Studio Code 편집기의 [개요 기능](https://docs.microsoft.com/visualstudio/ide/outlining)을 사용할 때 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다. 더 긴 코드 파일에서 현재 작업 중인 파일 부분에 집중할 수 있도록 하나 이상의 영역을 축소하거나 숨길 수 있습니다. 다음 예제에서는 영역을 정의하는 방법을 보여 줍니다.  
  
```  
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>주의  
 `#region` 블록은 [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) 지시문으로 종료해야 합니다.  
  
 `#region` 블록은 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 블록과 겹칠 수 없습니다. 그러나 `#region` 블록을 `#if` 블록에 중첩할 수 있고 `#if` 블록을 `#region` 블록에 중첩할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)


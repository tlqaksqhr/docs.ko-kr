---
title: "checked(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-reference"></a>checked(C# 참조)
`checked` 키워드는 정수 형식 산술 연산 및 변환에 대한 오버플로 검사를 명시적으로 사용하도록 설정하는 데 사용됩니다.  
  
 상수 값만 포함된 식이 대상 형식의 범위를 벗어난 값을 생성할 경우 기본적으로 이 식에서는 컴파일러 오류가 발생합니다. 식에 하나 이상의 상수가 아닌 값이 포함된 경우 컴파일러에서는 오버플로를 감지하지 않습니다. 다음 예제에서 `i2`에 할당된 식을 계산하면 컴파일러 오류가 발생하지 않습니다.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 기본적으로 이러한 상수가 아닌 식은 런타임에 오버플로가 있는지 검사되지 않고 오버플로 예외를 일으키지 않습니다. 이전 예제는 양의 정수 2개의 합계로 -2,147,483,639를 표시합니다.  
  
 오버플로 검사는 컴파일러 옵션, 환경 구성 또는 `checked` 키워드 사용을 통해 사용하도록 설정될 수 있습니다. 다음 예제에서는 `checked` 식 또는 `checked` 블록을 사용하여 런타임에 이전 합계에 의해 생성되는 오버플로를 감지하는 방법을 보여 줍니다. 두 예제는 모두 오버플로 예외를 일으킵니다.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 키워드는 오버플로 검사를 피하는 데 사용될 수 있습니다.  
  
## <a name="example"></a>예제  
 이 샘플에서는 `checked`를 사용하여 런타임에 오버플로 검사를 사용하도록 설정하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)


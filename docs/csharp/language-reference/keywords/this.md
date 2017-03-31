---
title: "this(C# 참조) | Microsoft 문서"
description: "this 키워드(C# 참조)"
keywords: "this(C#), this 키워드(C#), this 키워드(C# 참조), this 키워드(C# 언어 참조)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
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
ms.openlocfilehash: 8e14a32f11b9661ae18fd718fb1a72385fa7f3a7
ms.lasthandoff: 03/13/2017

---
# <a name="this-c-reference"></a>this(C# 참조)
`this` 키워드는 클래스의 현재 인스턴스를 가리키며 확장 메서드의 첫 번째 매개 변수에 대한 한정자로도 사용됩니다.  
  
> [!NOTE]
>  이 문서에서는 클래스 인스턴스와 함께 `this`를 사용하는 방법을 설명합니다. 확장 메서드에서 사용하는 방법에 대한 자세한 내용은 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.  
  
 `this`의 일반적인 사용은 다음과 같습니다.  
  
-   비슷한 이름으로 숨겨진 멤버를 한정합니다. 예를 들면 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   개체를 다른 메서드에 매개 변수로 전달합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    CalcTax(this);  
    ```  
  
-   인덱서를 선언합니다. 예를 들면 다음과 같습니다.  
  
 [!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 정적 멤버 함수는 개체의 일부가 아니라 클래스 수준에 있기 때문에 `this` 포인터가 없습니다. 정적 메서드에서 `this`를 참조하면 오류가 발생합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `this`를 사용하여 유사한 이름으로 숨겨진 `Employee` 클래스 멤버 `name` 및 `alias`를 한정합니다. 다른 클래스에 속하는 `CalcTax` 메서드에 개체를 전달하는 데에도 사용됩니다.  
  
 [!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)

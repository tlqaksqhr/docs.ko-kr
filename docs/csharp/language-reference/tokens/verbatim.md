---
title: "@(C# 참조) | Microsoft 문서"
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: c32a3d83730c8e9ba5e74f74a436174294538d95
ms.contentlocale: ko-kr
ms.lasthandoff: 05/24/2017

---
# <a name="-c-reference"></a>@(C# 참조)

`@` 특수 문자는 축자 식별자로 사용됩니다. 다음과 같은 방법으로 사용할 수 있습니다.

1. C# 키워드를 식별자로 사용하도록 설정합니다. `@` 문자는 컴파일러가 C# 키워드가 아닌 식별자로 해석할 코드 요소의 접두사입니다. 다음 예제에서는 `@` 문자를 사용하여 `for` 루프에서 사용되는 `for`라는 이름의 식별자를 정의합니다.

   [!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. 문자열 리터럴이 축자로 해석될 것임을 나타냅니다. 이 인스턴스의 `@` 문자는 *축자 문자 문자열*을 정의합니다. 단순 이스케이프 시퀀스(예: 백슬래시에 `"\\"`), 16진수 이스케이프 시퀀스(예: 대문자 A에 `"\x0041"`), 유니코드 이스케이프 시퀀스(예: 대문자 A에 `"\u0041"`)는 문자 그대로 해석됩니다. 인용 부호 이스케이프 시퀀스(`""`)만 문자 그대로 해석되지 않고, 단일 작은따옴표를 생성합니다. 다음 예제에서는 각각 일반 문자열 리터럴 및 축자 문자열 리터럴을 사용하여 두 개의 동일한 파일 경로를 정의합니다. 이것은 축자 문자열 리터럴의 일반적인 사용법 중 하나입니다.

   [!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   다음 예제에서는 동일한 문자 시퀀스를 포함한 일반 문자열 리터럴 및 축자 문자열 리터럴의 효과를 보여 줍니다.

   [!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. 이름이 서로 충돌하는 경우 특성 간에 구분하기 위해 컴파일러를 사용합니다. 특성은 @System.Attribute 에서 파생되는 형식입니다. 컴파일러는 이 규칙을 적용하지 않지만, 형식 이름에는 일반적으로 **Attribute** 접미사가 포함됩니다. 전체 이름(예: `[InfoAttribute]`) 또는 약식 이름(예: `[Info]`)으로 코드에서 특성을 참조할 수 있습니다. 그러나 두 개의 약식 특성 유형 이름이 동일하고 한 유형 이름에만 **Attribute** 접미사가 포함된 경우 이름 충돌이 발생합니다. 다음 예에서는 컴파일러가 `Info` 및 `InfoAttribute` 특성 중 무엇을 `Main` 메서드에 적용할지 결정할 수 없으므로 코드가 컴파일되지 않습니다.

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   축자 식별자를 사용하여 `Info` 특성을 식별하는 경우에는 성공적으로 컴파일됩니다.

   [!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 특수 문자](../../../csharp/language-reference/tokens/index.md)


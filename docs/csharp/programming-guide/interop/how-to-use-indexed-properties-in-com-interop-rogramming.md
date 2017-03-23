---
title: "방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인덱싱된 속성[C#]"
  - "Office 프로그래밍[C#], 인덱싱된 속성"
  - "속성[C#], 인덱싱된 상태"
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# 방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용(C# 프로그래밍 가이드)
*인덱싱된 속성*은 C\# 프로그래밍에서 매개 변수 있는 COM 속성이 사용되는 방식을 향상시킵니다.  인덱싱된 속성은 Visual C\# 2010에서 도입된 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), 새로운 형식\([dynamic](../../../csharp/language-reference/keywords/dynamic.md)\), [포함된 형식 정보](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) 등의 다른 기능과 함께 작동하여 Microsoft Office 프로그래밍을 향상시킵니다.  
  
 이전 버전의 C\#에서는 `get` 메서드에 매개 변수가 없고 `set` 메서드의 매개 변수로 값 매개 변수 하나만 있는 경우에만 메서드를 속성으로 액세스할 수 있습니다.  그러나 모든 COM 속성이 이러한 제한 사항에 부합하는 것은 아닙니다.  예를 들어, Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) 속성에는 범위 이름에 대한 매개 변수가 필요한 `get` 접근자가 있습니다.  이전에는 `Range` 속성에 직접 액세스할 수 없었기 때문에 다음 예제와 같이 `get_Range` 메서드를 대신 사용해야 했습니다.  
  
 [!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 인덱싱된 속성을 사용하면 앞의 예제 대신 다음을 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  이전 예제에서는 `Type.Missing`을 생략할 수 있도록 Visual C\# 2010에 도입된 [선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)라는 기능도 사용합니다.  
  
 마찬가지로, Visual C\# 2008 및 이전 버전에서 [Range](http://go.microsoft.com/fwlink/?LinkId=179211) 개체의 `Value` 속성 값을 설정하려면 인수 두 개가 필요합니다.  한 인수는 범위 값의 형식을 지정하는 선택적 매개 변수에 대한 값을 제공하고,  다른 인수는 `Value` 속성에 대한 값을 제공합니다.  Visual C\# 2010 이전 버전의 C\# 에서는 인수 하나만 허용되었습니다.  따라서 일반적인 set 메서드를 사용하는 대신 `set_Value` 메서드를 사용하거나 다른 속성인 [Value2](http://go.microsoft.com/fwlink/?LinkId=166050)를 사용해야 합니다.  다음 예제에서는 이 방법을 보여 줍니다.  두 예제에서는 모두 A1 셀의 값을 `Name`에 설정합니다.  
  
 [!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 인덱싱된 속성을 사용하면 앞의 예제 대신 다음 코드를 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 인덱싱된 속성을 직접 만들 수 없습니다.  이 기능으로는 기존의 인덱싱된 속성만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 전체 예제를 보여 줍니다.  Office API에 액세스하는 프로젝트를 설정하는 방법에 대한 자세한 내용은 [방법: Visual C\# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)를 참조하십시오.  
  
 [!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## 참고 항목  
 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [동적](../../../csharp/language-reference/keywords/dynamic.md)   
 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [방법: Visual C\# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)   
 [연습: Office 프로그래밍](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
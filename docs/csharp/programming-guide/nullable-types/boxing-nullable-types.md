---
title: "Nullable 형식 boxing(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: e4ff2e8a31ca5a59494f80597460e90107e78c8a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/24/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a>Nullable 형식 boxing(C# 프로그래밍 가이드)
Nullable 형식을 기반으로 하는 개체는 개체가 null이 아닌 경우에만 boxing됩니다. <xref:System.Nullable%601.HasValue%2A>가 `false`이면 boxing 대신 개체 참조가 `null`에 할당됩니다. 예를 들면 다음과 같습니다.  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 개체가 null이 아닌 경우(<xref:System.Nullable%601.HasValue%2A>가 `true`인 경우) boxing이 발생하지만 nullable 개체의 기반이 되는 기본 형식만 boxing됩니다. null이 아닌 nullable 값 형식을 boxing하면 값 형식을 래핑하는 <xref:System.Nullable%601?displayProperty=fullName>이 아니라 값 형식 자체가 boxing됩니다. 예를 들면 다음과 같습니다.  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 두 boxed 개체는 nullable이 아닌 형식을 boxing하여 만들어진 개체와 동일합니다. 또한 nullable이 아닌 boxed 형식과 마찬가지로, 다음 예제와 같이 nullable 형식으로 unboxed할 수 있습니다.  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>설명  
 boxed 시 nullable 형식의 동작은 다음 두 가지 이점을 제공합니다.  
  
1.  nullable 개체 및 boxed 상대 항목이 null인지 테스트할 수 있습니다.  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  boxed nullable 형식은 기본 형식의 기능을 완벽하게 지원합니다.  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)   
 [방법: Nullable 형식 식별](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)

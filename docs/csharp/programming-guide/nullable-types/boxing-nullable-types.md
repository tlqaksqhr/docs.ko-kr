---
title: "Nullable 형식 boxing(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "boxing[C#], nullable 형식"
  - "nullable 형식[C#], boxing 및 unboxing"
  - "unboxing[C#], nullable 형식"
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Nullable 형식 boxing(C# 프로그래밍 가이드)
nullable 형식을 기반으로 한 개체는 이 개체가 null이 아닌 경우에만 boxing됩니다.  <xref:System.Nullable%601.HasValue%2A>가 `false`인 경우 boxing하는 대신 개체 참조가 `null`에 할당됩니다.  예를 들면 다음과 같습니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 개체가 null이 아닌 경우, 즉 <xref:System.Nullable%601.HasValue%2A>가 `true`인 경우 boxing이 수행되지만 이 경우에도 nullable 개체의 기반이 되는 내부 형식만 boxing됩니다.  null이 아닌 nullable 값 형식을 boxing하면 값 형식을 래핑하는 <xref:System.Nullable%601?displayProperty=fullName>이 아니라 값 형식 자체가 boxing됩니다.  예를 들면 다음과 같습니다.  
  
```  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 boxing된 두 개체는 nullable 이외의 형식을 boxing하여 만든 개체와 동일합니다.  이 개체는 nullable이 아닌 boxed 형식과 마찬가지로 nullable 형식으로 unboxing할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## 설명  
 nullable 형식을 boxing하는 경우 그 동작에 두 가지 이점이 있습니다.  
  
1.  nullable 개체와 boxing된 상응하는 개체가 null인지 테스트할 수 있습니다.  
  
    ```  
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
  
2.  boxing된 nullable 형식은 내부 형식의 기능을 완전히 지원합니다.  
  
    ```  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)   
 [방법: Nullable 형식 식별](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
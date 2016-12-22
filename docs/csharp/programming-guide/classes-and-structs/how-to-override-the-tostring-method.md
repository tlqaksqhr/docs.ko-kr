---
title: "방법: ToString 메서드 재정의(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "상속[C#], OnPaint 및 ToString 재정의"
  - "ToString 메서드, C#의 재정의"
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: ToString 메서드 재정의(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\#의 모든 클래스나 구조체는 <xref:System.Object> 클래스를 암시적으로 상속합니다.  따라서 C\#의 모든 개체는 해당 개체에 대한 문자열 표현을 반환하는 <xref:System.Object.ToString%2A> 메서드를 가집니다.  예를 들어, `int` 형식의 모든 변수에는 그 내용을 문자열로 반환하는 데 사용할 수 있는 `ToString` 메서드가 있습니다.  
  
 [!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 사용자 지정 클래스나 구조체를 만들 때 클라이언트 코드에 해당 형식에 대한 정보를 제공하려면 <xref:System.Object.ToString%2A> 메서드를 재정의해야 합니다.  
  
 형식 문자열의 함께 사용자 지정 서식을 사용 하는 방법에 대 한 정보는 `ToString`메서드를 참조 하십시오 [형식 서식 지정](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  
  
> [!IMPORTANT]
>  이 메서드를 통해 제공할 정보를 결정할 때는 클래스나 구조체가 신뢰할 수 없는 코드에서 사용될지를 고려합니다.  악성 코드에서 악용될 수 있는 정보는 제공하지 마십시오.  
  
### 클래스나 구조체에서 ToString 메서드를 재정의하려면  
  
1.  다음 한정자와 반환 형식을 사용하여 `ToString` 메서드를 선언합니다.  
  
    ```c#  
    public override string ToString(){}  
    ```  
  
2.  문자열이 반환되도록 메서드를 구현합니다.  
  
     다음 예제에서는 클래스의 이름뿐 아니라 클래스의 특정 인스턴스와 관련된 데이터도 반환합니다.  
  
     [!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     다음 코드 예제와 같이 `ToString` 메서드를 테스트할 수 있습니다.  
  
     [!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## 참고 항목  
 <xref:System.IFormattable>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)   
 [string](../../../csharp/language-reference/keywords/string.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [형식 서식 지정](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)
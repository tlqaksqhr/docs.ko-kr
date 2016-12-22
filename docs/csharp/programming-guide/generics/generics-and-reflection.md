---
title: "제네릭 및 리플렉션(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "제네릭[C#], 리플렉션"
  - "리플렉션[C#], 제네릭 형식"
ms.assetid: 162fd9b4-dd5b-4abb-8c9b-e44e21e2f451
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 제네릭 및 리플렉션(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

CLR\(공용 언어 런타임\)에서는 런타임에 제네릭 형식 정보에 액세스할 수 있으므로 리플렉션을 사용하면 제네릭이 아닌 형식에 대해서와 동일한 방식으로 제네릭 형식에 대한 정보를 얻을 수 있습니다.  자세한 내용은 [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)를 참조하십시오.  
  
 [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)]에서는 제네릭 형식에 대한 런타임 정보를 사용할 수 있도록 여러 가지 새로운 멤버가 <xref:System.Type> 클래스에 추가되었습니다.  이러한 메서드와 속성의 사용 방법에 대한 자세한 내용은 해당 클래스에 대한 문서를 참조하십시오. <xref:System.Reflection.Emit> 네임스페이스에도 제네릭을 지원하는 새 멤버가 추가되었습니다.  자세한 내용은 [방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의](../Topic/How%20to:%20Define%20a%20Generic%20Type%20with%20Reflection%20Emit.md)를 참조하십시오.  
  
 제네릭 리플렉션에 사용되는 용어에 대한 고정 조건 목록은 <xref:System.Type.IsGenericType%2A> 속성 설명을 참조하십시오.  
  
|System.Type 멤버 이름|설명|  
|-----------------------|--------|  
|<xref:System.Type.IsGenericType%2A>|형식이 제네릭인 경우 true를 반환합니다.|  
|<xref:System.Type.GetGenericArguments%2A>|제네릭 형식 정의의 형식 매개 변수 또는 생성된 형식에 대해 제공되는 형식 인수를 나타내는 `Type` 개체의 배열을 반환합니다.|  
|<xref:System.Type.GetGenericTypeDefinition%2A>|현재 생성된 형식의 내부 제네릭 형식 정의를 반환합니다.|  
|<xref:System.Type.GetGenericParameterConstraints%2A>|현재 제네릭 형식 매개 변수에 대한 제약 조건을 나타내는 `Type` 개체의 배열을 반환합니다.|  
|<xref:System.Type.ContainsGenericParameters%2A>|특정 형식이 지정되지 않은 형식 매개 변수가 형식 또는 형식의 바깥쪽 형식이나 메서드에 포함되어 있는 경우 true를 반환합니다.|  
|<xref:System.Type.GenericParameterAttributes%2A>|현재 제네릭 형식 매개 변수의 특수 제약 조건을 설명하는 `GenericParameterAttributes` 플래그의 조합을 가져옵니다.|  
|<xref:System.Type.GenericParameterPosition%2A>|형식 매개 변수를 나타내는 `Type` 개체에 대해 형식 매개 변수를 선언한 제네릭 메서드 정의 또는 제네릭 형식 정의의 형식 매개 변수 목록에서 형식 매개 변수가 차지하는 위치를 가져옵니다.|  
|<xref:System.Type.IsGenericParameter%2A>|현재 `Type`이 제네릭 형식이나 메서드 정의의 형식 매개 변수를 표시하는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Type.IsGenericTypeDefinition%2A>|현재 <xref:System.Type>이 다른 제네릭 형식을 생성하는 데 사용할 수 있는 제네릭 형식 정의를 표시하는지 여부를 나타내는 값을 가져옵니다.  형식이 제네릭 형식의 정의를 표시하는 경우 true를 반환합니다.|  
|<xref:System.Type.DeclaringMethod%2A>|현재 제네릭 형식 매개 변수를 정의한 제네릭 메서드를 반환합니다. 형식 매개 변수가 제네릭 메서드를 통해 정의되지 않은 경우 null을 반환합니다.|  
|<xref:System.Type.MakeGenericType%2A>|현재 제네릭 형식 정의의 형식 매개 변수에 대한 형식 배열의 요소를 대체하고, 생성된 결과 형식을 나타내는 <xref:System.Type> 개체를 반환합니다.|  
  
 또한 제네릭 메서드에 대한 런타임 정보를 사용할 수 있도록 새로운 멤버가 <xref:System.Reflection.MethodInfo> 클래스에 추가되었습니다.  제네릭 메서드 리플렉션에 사용되는 용어에 대한 고정 조건의 목록을 보려면 <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> 속성 설명을 참조하십시오.  
  
|System.Reflection.MemberInfo 멤버 이름|설명|  
|----------------------------------------|--------|  
|<xref:System.Reflection.MethodInfo.IsGenericMethod%2A>|메서드가 제네릭인 경우 true를 반환합니다.|  
|<xref:System.Reflection.MethodInfo.GetGenericArguments%2A>|생성된 제네릭 메서드의 형식 인수나 제네릭 메서드 정의의 형식 매개 변수를 나타내는 Type 개체의 배열을 반환합니다.|  
|<xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A>|현재 생성된 메서드의 내부 제네릭 메서드 정의를 반환합니다.|  
|<xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A>|특정 형식이 지정되지 않은 형식 매개 변수가 메서드 또는 메서드의 바깥쪽 형식에 포함되어 있는 경우 true를 반환합니다.|  
|<xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A>|현재 <xref:System.Reflection.MethodInfo>가 제네릭 메서드의 정의를 나타내는 경우 true를 반환합니다.|  
|<xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>|현재 제네릭 메서드 정의의 형식 매개 변수를 형식 배열의 요소로 대체하고, 생성된 메서드를 나타내는 <xref:System.Reflection.MethodInfo> 개체를 반환합니다.|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../visual-basic/reference/command-line-compiler/index.md)   
 [리플렉션 및 제네릭 형식](../Topic/Reflection%20and%20Generic%20Types.md)   
 [제네릭](../Topic/Generics%20in%20the%20.NET%20Framework.md)
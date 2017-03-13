---
title: "전용 생성자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 전용 생성자"
  - "전용 생성자[C#]"
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# 전용 생성자(C# 프로그래밍 가이드)
전용 생성자는 특수 인스턴스 생성자입니다.  이것은 정적 멤버만 포함하는 클래스에서 일반적으로 사용됩니다.  클래스에 전용 생성자만 한 개 이상 있고 공용 생성자는 없을 경우 중첩 클래스를 제외한 다른 클래스는 이 클래스의 인스턴스를 만들 수 없습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 빈 생성자를 선언하면 기본 생성자가 자동으로 생성되지 않습니다.  액세스 한정자를 생성자와 함께 사용하지 않을 경우에는 기본적으로 전용 생성자가 됩니다.  그러나 클래스가 인스턴스화될 수 없음을 분명히 하려면 대개 [private](../../../csharp/language-reference/keywords/private.md) 한정자를 명시적으로 사용합니다.  
  
 전용 생성자는 <xref:System.Math> 클래스처럼 인스턴스 필드나 메서드가 없는 경우 또는 클래스의 인스턴스를 가져오기 위해 메서드가 호출되는 경우에 클래스의 인스턴스가 생성되지 않도록 방지하는 데 사용됩니다.  클래스의 메서드가 모두 정적 메서드이면 전체 클래스를 정적 클래스로 만드는 것이 좋습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하십시오.  
  
## 예제  
 다음은 전용 생성자를 사용하는 클래스의 예제입니다.  
  
 [!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 예제에서 다음 문을 주석으로 처리하지 않으면 보호 수준 때문에 이 생성자에 액세스할 수 없어서 오류가 발생합니다.  
  
 [!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)
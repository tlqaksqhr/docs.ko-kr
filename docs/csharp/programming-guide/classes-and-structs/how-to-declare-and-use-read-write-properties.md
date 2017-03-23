---
title: "방법: 읽기/쓰기 속성 선언 및 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "get 접근자[C#], 속성 선언"
  - "set 접근자[C#]"
  - "속성[C#], 선언"
  - "읽기/쓰기 속성[C#]"
  - "접근자[C#], 속성 선언"
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# 방법: 읽기/쓰기 속성 선언 및 사용(C# 프로그래밍 가이드)
속성을 사용하면 개체의 데이터에 보호되거나 제어되지 않고 확인되지 않은 방식으로 액세스하는 데 따른 위험 없이 공용 데이터 멤버의 이점을 누릴 수 있습니다.  이 과정에는 내부 데이터 멤버에서 값을 할당 및 검색하기 위한 특별한 메서드인 *접근자*가 사용됩니다.  [set](../../../csharp/language-reference/keywords/set.md) 접근자를 사용하면 데이터 멤버를 할당할 수 있고 [get](../../../csharp/language-reference/keywords/get.md) 접근자를 사용하면 데이터 멤버 값을 검색할 수 있습니다.  
  
 이 샘플에서는 문자열인 `Name` 및 정수인 `Age`라는 두 속성이 있는 `Person` 클래스를 보여 줍니다.  두 속성은 모두 `get` 및 `set` 접근자를 제공하므로 이는 모두 읽기\/쓰기 속성으로 간주됩니다.  
  
## 예제  
 [!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## 강력한 프로그래밍  
 위 예제에서 `Name`과 `Age` 속성은 [public](../../../csharp/language-reference/keywords/public.md)이며 `get` 및 `set` 접근자를 모두 포함합니다.  이렇게 하면 임의의 개체가 이들 속성을 읽고 쓸 수 있습니다.  그러나 때로는 이러한 접근자 중 하나를 제외해야 할 수도 있습니다.  예를 들어, `set` 접근자를 생략하면 속성을 읽기 전용으로 만들 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 또는 접근자 하나만 공용으로 노출시키고 다른 접근자는 전용 또는 보호된 상태로 만들 수 있습니다.  자세한 내용은 [비대칭 접근자 액세스 가능성](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)을 참조하십시오.  
  
 일단 속성이 선언되면 클래스의 필드처럼 사용할 수 있습니다.  다음 문에서와 같이 속성 값을 구하고 설정할 때 기본 구문을 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 속성의 `set` 메서드에서 특수한 `value` 변수를 사용할 수 있습니다.  이 변수에는 사용자가 지정한 값이 포함됩니다. 예를 들어 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 `Person` 개체의 `Age` 속성을 증분하는 데 필요한 clean 구문에 주의하십시오.  
  
 [!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 속성을 모델링할 때 `set` 및 `get` 메서드를 각각 사용한 경우에는 다음과 같은 코드를 사용해도 결과가 동일합니다.  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 다음 예제에서는 `ToString` 메서드를 재정의합니다.  
  
 [!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 `ToString`은 프로그램에서 명시적으로 사용되지 않으며  `WriteLine` 호출에서 기본적으로 호출됩니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)
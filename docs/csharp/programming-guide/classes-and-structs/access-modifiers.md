---
title: "액세스 한정자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "액세스 한정자[C#], 정보"
  - "C# 언어, 액세스 한정자"
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# 액세스 한정자(C# 프로그래밍 가이드)
모든 형식 및 형식 멤버에는 현재 어셈블리나 다른 어셈블리에서 사용할 수 있는지 여부를 제어하는 액세스 수준이 있습니다.  다음 액세스 한정자 중 하나를 사용하여 형식이나 멤버를 선언할 때 액세스 수준을 지정할 수 있습니다.  
  
 [public](../../../csharp/language-reference/keywords/public.md)  
 동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.  
  
 [private](../../../csharp/language-reference/keywords/private.md)  
 동일한 클래스 또는 구조체의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.  
  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 동일한 클래스나 구조체의 코드 또는 파생 클래스의 클래스에서만 형식이나 멤버에 액세스할 수 있습니다.  
  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.  
  
 `protected internal`  
 형식 또는 멤버는 선언되는 어셈블리의 모든 코드에 액세스하거나 다른 어셈블리의 파생 클래스 내에서 액세스할 수 있습니다.   다른 어셈블리의 액세스는 보호된 내부 요소가 선언되는 클래스에서 파생되는 클래스 선언 내에서 발생해야 하며 파생된 클래스 형식의 인스턴스를 통해 발생해야 합니다.  
  
 다음 예제에서는 형식 및 멤버에 대한 액세스 한정자를 지정하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/access-modifiers_1.cs)]  
  
 모든 컨텍스트의 모든 형식 또는 멤버에서 모든 액세스 한정자를 사용할 수 있는 것은 아닙니다. 일부 경우에는 멤버를 포함하는 형식의 액세스 가능성에 의해 형식 멤버의 액세스 가능성이 제한됩니다.  다음 단원에서는 액세스 가능성에 대해 자세히 설명합니다.  
  
## 클래스 및 구조체 액세스 가능성  
 네임스페이스 내부에서 직접 선언되어 다른 클래스나 구조체에 중첩되지 않은 클래스와 구조체는 public 또는 internal일 수 있습니다.  액세스 한정자가 지정되지 않으면 internal이 기본적으로 사용됩니다.  
  
 중첩된 클래스 및 구조체를 포함하는 구조체 멤버는 일반, 내부 또는 개인으로 선언할 수 있습니다.  중첩된 클래스 및 구조체를 포함한 클래스 멤버는 공용, 보호된 내부, 보호, 내부 또는 개인이 될 수 있습니다.  클래스 멤버 및 중첩된 클래스 및 구조체를 포함하는 구조체 멤버에 대한 액세스 수준은 기본적으로 private입니다.  private으로 선언된 중첩된 형식은 포함하는 형식 외부에서 액세스할 수 없습니다.  
  
 파생 클래스의 액세스 가능성이 해당 기본 형식보다 좋을 수 없습니다.  예를 들어 내부 클래스 `A`에서 공용 클래스 `B`를 파생시킬 수 없습니다.  이러한 선언이 허용되면 파생 클래스에서 `A`의 모든 protected 또는 internal 멤버에 액세스할 수 있으므로 `A`를 public으로 만드는 것이나 마찬가지입니다.  
  
 InternalsVisibleToAttribute를 사용하면 다른 특정 어셈블리에서 internal 형식에 액세스하도록 허용할 수 있습니다.  자세한 내용은 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 클래스 및 구조체 멤버 액세스 가능성  
 다섯 가지 액세스 형식 중 하나로 클래스 멤버\(중첩된 클래스와 구조체 포함\)를 선언할 수 있습니다.  구조체는 상속을 지원하지 않으므로 구조체 멤버는 protected로 선언할 수 없습니다.  
  
 일반적으로 멤버의 액세스 가능성은 멤버가 포함된 형식의 액세스 가능성보다 크지 않습니다.  그러나 내부 클래스의 공용 구성원은 구성원이 인터페이스 메서드를 구현하거나 공용 기본 클래스에 정의된 가상 메서드를 재정의하는 경우 어셈블리 외부에서 액세스할 수 있습니다.  
  
 필드, 속성 또는 이벤트는 최소한 멤버 자체로 액세스할 수 있어야 합니다.  마찬가지로, 반환 형식과, 메서드, 인덱서 또는 대리자인 모든 멤버의 매개 변수 형식은 멤버 자체만큼 액세스할 수 있어야 합니다.  예를 들어 public 메서드 `M`에서 클래스 `C`를 반환하려면 `C`도 public이어야 합니다.  마찬가지로 형식 `A`가 private으로 선언된 경우 `A`의 protected 속성이 존재할 수 없습니다.  
  
 사용자 정의 연산자는 항상 public으로 선언되어야 합니다.  자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  
  
 소멸자에는 액세스 한정자를 사용할 수 없습니다.  
  
 클래스나 구조체 멤버의 액세스 수준을 설정하려면 다음 예제와 같이 멤버 선언에 적절한 키워드를 추가합니다.  
  
 [!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/access-modifiers_2.cs)]  
  
> [!NOTE]
>  보호된 내부 액세스 가능성 수준은 protected AND internal이 아니라 protected OR internal을 나타냅니다.  즉, 보호되는 내부 멤버는 파생 클래스를 포함하여 동일한 어셈블리의 모든 클래스에서 액세스할 수 있습니다.  동일한 어셈블리의 파생 클래스에서만 액세스할 수 있도록 제한하려면 클래스 자체를 internal로 선언하고 클래스의 멤버를 protected로 선언합니다.  
  
## 기타 형식  
 네임스페이스 안에 직접 선언된 인터페이스는 public 또는 internal로 선언할 수 있으며, 클래스 및 구조체와 마찬가지로 인터페이스는 기본적으로 internal 액세스입니다.  인터페이스의 용도는 다른 형식이 클래스 또는 구조체에 액세스할 수 있게 하는 것이므로 인터페이스 멤버는 항상 public입니다.  인터페이스 멤버에는 액세스 한정자를 적용할 수 없습니다.  
  
 열거형 멤버는 항상 public이고 액세스 한정자를 적용할 수 없습니다.  
  
 대리자는 클래스 및 구조체와 같이 동작합니다.  기본적으로 네임스페이스 내에서 직접 선언하면 내부 액세스할 수 있으며 중첩되면 private 액세스 권한을 갖습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [클래스](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [interface](../../../csharp/language-reference/keywords/interface.md)
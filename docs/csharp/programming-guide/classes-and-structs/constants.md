---
title: "상수(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 상수"
  - "상수[C#]"
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# 상수(C# 프로그래밍 가이드)
상수는 컴파일 타임에 인식되고 프로그램 수명 기간 중 변경할 수 없는 불변 값입니다.  상수는 [const](../../../csharp/language-reference/keywords/const.md) 한정자를 사용하여 선언합니다.  C\# 기본 제공 형식\(<xref:System.Object?displayProperty=fullName> 제외\)만 `const`로 선언할 수 있습니다.  기본 제공 형식의 목록을 보려면 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)를 참조하십시오.  클래스, 구조체, 배열을 비롯한 사용자 정의 형식은 `const`가 될 수 없습니다.  런타임에 생성자 내부 등에서 한 번 초기화되고 그 이후로는 변경할 수 없는 클래스, 구조체 또는 배열을 만들려면 [readonly](../../../csharp/language-reference/keywords/readonly.md) 한정자를 사용하십시오.  
  
 C\#에서는 `const` 메서드, 속성 또는 이벤트를 사용할 수 없습니다.  
  
 열거형을 사용하면 정수 계열 기본 제공 형식\(예: `int`, `uint`, `long`\)에 대해 명명된 상수를 정의할 수 있습니다.  자세한 내용은 [enum](../../../csharp/language-reference/keywords/enum.md)을 참조하십시오.  
  
 상수를 선언할 때 이를 초기화해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]  
  
 이 예제에서 상수 `months`는 항상 12입니다. 이 값은 클래스 자체에서도 변경할 수 없습니다.  컴파일러는 C\# 소스 코드에서 상수 식별자\(예: `months`\)를 만나면 이 리터럴 값을 직접 컴파일러에서 생성하는 IL\(Intermediate Language\) 코드로 바꿉니다.  런타임에 상수에 연결된 변수 주소가 없으므로 `const` 필드를 참조로 전달하거나 식의 l\-value로 사용할 수 없습니다.  
  
> [!NOTE]
>  DLL과 같은 다른 코드에 정의된 상수 값을 참조할 때는 매우 주의해야 합니다.  DLL 새 버전에서 해당 상수에 대해 새로운 값을 정의하는 경우 사용자 프로그램에서는 새 버전을 사용하여 다시 컴파일하기 전까지 이전 리터럴 값을 보유하게 됩니다.  
  
 동일한 형식의 상수 여러 개를 동시에 선언할 수 있습니다. 예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]  
  
 순환 참조 문제가 발생하지 않는 한 상수를 초기화하는 데 사용되는 식에서 다른 상수를 참조할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]  
  
 상수는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected` `internal`로 표시할 수 있습니다.  이러한 액세스 한정자는 클래스 사용자가 상수에 액세스하는 방식을 정의합니다.  자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
 상수의 값은 해당 형식의 모든 인스턴스에서 동일하므로 상수는 [static](../../../csharp/language-reference/keywords/static.md) 필드처럼 액세스됩니다.  상수는 `static` 키워드를 사용하여 선언하지 않습니다.  상수를 정의하는 클래스에 포함되지 않은 식에서 상수에 액세스하려면 클래스 이름, 마침표 및 상수 이름을 사용해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [형식](../../../csharp/programming-guide/types/index.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)   
 [Immutability in C\# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379)
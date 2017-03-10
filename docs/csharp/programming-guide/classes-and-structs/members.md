---
title: "멤버(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 형식 멤버"
  - "형식[C#], 중첩 형식"
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# 멤버(C# 프로그래밍 가이드)
클래스와 구조체에는 해당 데이터와 동작을 나타내는 멤버가 있습니다.  클래스 멤버에는 클래스에서 선언된 모든 멤버와 클래스 상속 계층 구조에 있는 모든 클래스에서 선언된 모든 멤버\(생성자와 소멸자는 제외\)가 포함됩니다.  기본 클래스의 private 멤버는 상속되지만 파생 클래스에서 액세스할 수 없습니다.  
  
 다음 표에서는 클래스나 구조체에 포함될 수 있는 멤버의 종류를 보여 줍니다.  
  
|멤버|설명|  
|--------|--------|  
|[필드](../../../csharp/programming-guide/classes-and-structs/fields.md)|필드는 클래스 범위에 선언된 변수입니다.  필드는 기본 제공 숫자 형식일 수도 있고 다른 클래스의 인스턴스일 수도 있습니다.  예를 들어, 달력 클래스에는 현재 날짜가 들어 있는 필드가 포함될 수 있습니다.|  
|[상수](../../../csharp/programming-guide/classes-and-structs/constants.md)|상수는 컴파일 타임에 값이 설정되는 필드 또는 속성이므로 변경될 수 없습니다.|  
|[속성](../../../csharp/programming-guide/classes-and-structs/properties.md)|속성은 해당 클래스의 필드처럼 액세스할 수 있는 클래스의 메서드입니다.  속성을 사용하면 개체에 알리지 않은 채 클래스 필드가 변경되지 않도록 보호할 수 있습니다.|  
|[메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)|메서드는 클래스가 수행할 수 있는 작업을 정의합니다.  메서드에는 입력 데이터를 제공하는 매개 변수를 사용할 수 있고, 메서드에서 매개 변수를 통해 출력 데이터를 반환할 수 있습니다.  메서드는 매개 변수를 사용하지 않고 직접 값을 반환할 수도 있습니다.|  
|[이벤트](../../../csharp/programming-guide/events/index.md)|이벤트를 사용하면 단추 클릭, 메서드 작업 완료 등과 같은 사건에 대한 정보를 다른 개체에 알릴 수 있습니다.  이벤트는 대리자를 사용하여 정의되고 트리거됩니다.|  
|[연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|오버로드된 연산자는 클래스 멤버로 간주됩니다.  연산자를 오버로드할 때 클래스에서 해당 연산자를 public static 메서드로 정의합니다.  미리 정의된 연산자\(`+`, `*`, `<` 등\)는 멤버로 간주되지 않습니다.  자세한 내용은 [오버로드할 수 있는 연산자](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)을 참조하십시오.|  
|[인덱서](../../../csharp/programming-guide/indexers/index.md)|인덱서를 사용하면 배열과 비슷한 방식으로 개체를 인덱싱할 수 있습니다.|  
|[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)|생성자는 개체를 처음 만들 때 호출되는 메서드입니다.  생성자는 일반적으로 개체의 데이터를 초기화하는 데 사용됩니다.|  
|[소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)|소멸자는 C\#에서 매우 드물게 사용됩니다.  소멸자는 개체를 메모리에서 제거하려 할 때 런타임 실행 엔진을 통해 호출되는 메서드입니다.  일반적으로 소멸자는 해제해야 할 리소스가 모두 올바르게 처리되도록 하는 데 사용됩니다.|  
|[중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)|중첩 형식은 다른 형식의 내부에 선언된 형식입니다.  중첩 형식은 일반적으로 이를 포함하는 형식에서만 사용하는 개체를 설명하는 데 사용됩니다.|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [필드](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)   
 [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [오버로드할 수 있는 연산자](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)
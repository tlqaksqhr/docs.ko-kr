---
title: 멤버(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], nested types
- C# language, type members
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
ms.openlocfilehash: 61818b153bb74c5c0da053f381fd1ed9132c066b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318226"
---
# <a name="members-c-programming-guide"></a>멤버(C# 프로그래밍 가이드)
클래스 및 구조체에는 해당 데이터와 동작을 나타내는 멤버가 있습니다. 클래스의 멤버에는 클래스에서 선언된 모든 멤버가 상속 계층 구조의 모든 클래스에서 선언된 모든 멤버(생성자 및 종료자 제외)와 함께 포함됩니다. 기본 클래스의 private 멤버는 상속되지만 파생 클래스에서 액세스할 수 없습니다.  
  
 다음 표에는 클래스 또는 구조체에 포함될 수 있는 멤버 종류가 나와 있습니다.  
  
|멤버|설명|  
|------------|-----------------|  
|[필드](../../../csharp/programming-guide/classes-and-structs/fields.md)|필드는 클래스 범위에서 선언된 변수입니다. 필드는 기본 제공 숫자 형식 또는 다른 클래스의 인스턴스일 수 있습니다. 예를 들어 달력 클래스에는 현재 날짜를 포함하는 필드가 있을 수 있습니다.|  
|[상수](../../../csharp/programming-guide/classes-and-structs/constants.md)|상수는 해당 값이 컴파일 시간에 설정되며 변경할 수 없는 필드 또는 속성입니다.|  
|[속성](../../../csharp/programming-guide/classes-and-structs/properties.md)|속성은 해당 클래스의 필드처럼 액세스되는 클래스의 메서드입니다. 속성은 클래스 필드에 대한 보호를 제공하여 개체 모르게 필드가 변경되지 않도록 할 수 있습니다.|  
|[메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)|메서드는 클래스가 수행할 수 있는 작업을 정의합니다. 메서드는 입력 데이터를 제공하는 매개 변수를 사용할 수 있으며, 매개 변수를 통해 출력 데이터를 반환할 수 있습니다. 메서드가 매개 변수를 사용하지 않고 직접 값을 반환할 수도 있습니다.|  
|[이벤트](../../../csharp/programming-guide/events/index.md)|이벤트는 단추 클릭, 성공적인 메서드 완료 등의 발생에 대한 알림을 다른 개체에 제공합니다. 이벤트는 대리자를 사용하여 정의 및 트리거됩니다.|  
|[연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|오버로드된 연산자는 클래스 멤버로 간주됩니다. 연산자를 오버로드하는 경우 클래스에서 공용 정적 메서드로 정의합니다. 미리 정의된 연산자(`+`, `*`, `<` 등)는 멤버로 간주되지 않습니다. 자세한 내용은 [오버로드할 수 있는 연산자](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)를 참조하세요.|  
|[인덱서](../../../csharp/programming-guide/indexers/index.md)|인덱서를 사용하면 배열과 유사한 방식으로 개체를 인덱싱할 수 있습니다.|  
|[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)|생성자는 개체를 처음 만들 때 호출되는 메서드입니다. 대체로 개체의 데이터를 초기화하는 데 사용됩니다.|  
|[종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)|종료자는 C#에서 매우 드물게 사용됩니다. 메모리에서 개체를 제거할 때 런타임 실행 엔진이 호출하는 메서드입니다. 일반적으로 해제해야 하는 리소스가 적절하게 처리되도록 하는 데 사용됩니다.|  
|[중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)|중첩 형식은 다른 형식 내에서 선언된 형식입니다. 중첩 형식은 대체로 개체를 포함하는 형식에서만 사용되는 개체를 설명하는 데 사용됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [필드](../../../csharp/programming-guide/classes-and-structs/fields.md)  
 [인덱서](../../../csharp/programming-guide/indexers/index.md)  
 [이벤트](../../../csharp/programming-guide/events/index.md)  
 [중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)  
 [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
 [오버로드할 수 있는 연산자](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)

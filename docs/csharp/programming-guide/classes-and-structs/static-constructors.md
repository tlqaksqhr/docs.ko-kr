---
title: "정적 생성자(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ee5448095cf06c2473c94bae542c02557918271a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="static-constructors-c-programming-guide"></a>정적 생성자(C# 프로그래밍 가이드)
정적 생성자는 [정적](../../../csharp/language-reference/keywords/static.md) 데이터를 초기화하거나 한 번만 수행해야 하는 특정 작업을 수행하는 데 사용됩니다. 첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출됩니다.  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 정적 생성자에는 다음과 같은 속성이 있습니다.  
  
-   정적 생성자는 액세스 한정자를 사용하거나 매개 변수를 갖지 않습니다.  
  
-   정적 생성자는 첫 번째 인스턴스가 만들어지거나 정적 멤버가 참조되기 전에 자동으로 호출되어 [클래스](../../../csharp/language-reference/keywords/class.md)를 초기화합니다.  
  
-   정적 생성자는 직접 호출할 수 없습니다.  
  
-   사용자는 프로그램에서 정적 생성자가 실행되는 시기를 제어할 수 없습니다.  
  
-   정적 생성자는 일반적으로 클래스가 로그 파일을 사용하고, 생성자를 사용하여 이 파일에 항목을 쓰는 경우에 사용됩니다.  
  
-   정적 생성자는 생성자가 `LoadLibrary` 메서드를 호출할 수 있을 때 비관리 코드에 대한 래퍼 클래스를 만드는 경우에도 유용합니다.  
  
-   정적 생성자가 예외를 throw하는 경우 런타임에서 생성자를 다시 호출하지 않으며, 프로그램을 실행 중인 응용 프로그램 도메인의 수명 동안 형식이 초기화되지 않은 상태로 유지됩니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `Bus` 클래스에는 정적 생성자가 있습니다. `Bus`의 첫 번째 인스턴스를 만들 때(`bus1`) 정적 생성자가 호출되어 클래스를 초기화합니다. 샘플 출력은 `Bus`의 두 인스턴스가 생성된 경우에도 정적 생성자가 한 번만 실행되고, 인스턴스 생성자를 실행하기 전에 실행되는지 확인합니다.  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)

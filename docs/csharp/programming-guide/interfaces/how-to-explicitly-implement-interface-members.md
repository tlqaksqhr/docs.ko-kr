---
title: "방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 88b96c15f724ee5961c72917308138a045988225
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)
이 예제에서는 [interface](../../../csharp/language-reference/keywords/interface.md) `IDimensions` 및 `Box` 클래스를 선언합니다. 이 클래스는 인터페이스 멤버 `getLength` 및 `getWidth`를 명시적으로 구현합니다. 멤버는 인터페이스 인스턴스 `dimensions`를 통해 액세스합니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
-   `Main` 메서드의 다음 줄은 컴파일 오류를 생성하므로 주석으로 처리되었습니다. 명시적으로 구현된 인터페이스 멤버는 [class](../../../csharp/language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.  
  
     [!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   또한 `Main` 메서드의 다음 줄은 메서드가 인터페이스 인스턴스에서 호출되기 때문에 상자 크기를 성공적으로 출력합니다.  
  
     [!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)   
 [방법: 두 인터페이스의 멤버를 명시적으로 구현](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)


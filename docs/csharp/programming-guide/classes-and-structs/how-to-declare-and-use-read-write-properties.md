---
title: "방법: 읽기/쓰기 속성 선언 및 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5e4ca1feff203dc2ab88c0d1dfae8098508fec7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>방법: 읽기/쓰기 속성 선언 및 사용(C# 프로그래밍 가이드)
속성은 개체 데이터에 대한 액세스가 보호, 제어, 확인되지 않을 위험 없이 공용 데이터 멤버의 편리함을 제공합니다. 이를 위해 기본 데이터 멤버의 값을 할당하고 검색하는 특수 메서드인 *접근자*가 사용됩니다. [set](../../../csharp/language-reference/keywords/set.md) 접근자를 통해 데이터 멤버를 할당할 수 있으며, [get](../../../csharp/language-reference/keywords/get.md) 접근자는 데이터 멤버 값을 검색합니다.  
  
 이 샘플에서는 `Name`(string) 및 `Age`(int)의 두 속성이 있는 `Person` 클래스를 보여 줍니다. 두 속성 모두 `get` 및 `set` 접근자를 제공하므로 읽기/쓰기 속성으로 간주됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이전 예제에서 `Name` 및 `Age` 속성은 [public](../../../csharp/language-reference/keywords/public.md)이며, `get` 및 `set` 접근자를 모두 포함합니다. 이 경우 모든 개체가 이러한 속성을 읽고 쓸 수 있습니다. 그러나 때로는 접근자 중 하나를 제외하는 것이 좋습니다. 예를 들어 `set` 접근자를 생략하면 속성은 읽기 전용이 됩니다.  
  
 [!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 또는 하나의 접근자를 공개적으로 노출하고 다른 접근자를 private 또는 protected로 설정할 수 있습니다. 자세한 내용은 [비대칭 접근자 접근성](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)을 참조하세요.  
  
 속성이 선언되면 클래스의 필드처럼 사용할 수 있습니다. 이 경우 다음 문과 같이 속성의 값을 가져오고 설정할 때 자연스러운 구문을 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 속성 `set` 메서드에 특수 `value` 변수를 사용할 수 있습니다. 이 변수에는 사용자가 지정한 값이 포함됩니다. 예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 `Person` 개체의 `Age` 속성을 증가하기 위한 정리된 구문은 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 개별 `set` 및 `get` 메서드를 사용하여 속성을 모델링한 경우 동등한 코드가 다음과 같이 표시될 수 있습니다.  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 다음 예제에서는 `ToString` 메서드가 재정의되었습니다.  
  
 [!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 `ToString`이 프로그램에서 명시적으로 사용되지 않고 기본적으로 `WriteLine` 호출에 의해 호출됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)


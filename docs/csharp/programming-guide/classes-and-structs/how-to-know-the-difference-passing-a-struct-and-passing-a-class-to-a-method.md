---
title: "방법: 메서드에 대한 구조체 전달과 클래스 참조 전달 간의 차이점 이해(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
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
ms.openlocfilehash: 1a4508c8765ac678fd371180cb0c3ece3e1d9a44
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>방법: 메서드에 대한 구조체 전달과 클래스 참조 전달 간의 차이점 이해(C# 프로그래밍 가이드)
다음 예제에서는 [struct](../../../csharp/language-reference/keywords/struct.md)를 메서드에 전달하는 것과 [class](../../../csharp/language-reference/keywords/class.md) 인스턴스를 메서드에 전달하는 것이 어떻게 다른지를 보여 줍니다. 예제에서 두 인수(구조체와 클래스 인스턴스)는 모두 값으로 전달되며, 두 메서드 모두 인수의 한 필드 값을 변경합니다. 그러나 구조체를 전달할 때 전달되는 내용과 클래스 인스턴스를 전달할 때 전달되는 내용이 다르기 때문에 두 메서드의 결과는 서로 다릅니다.  
  
 구조체는 [value type](../../../csharp/language-reference/keywords/value-types.md)이므로 메서드에 [구조체를 값으로 전달](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)하는 경우 메서드가 구조체 인수의 복사본을 받아서 작동합니다. 메서드가 호출 메서드의 원래 구조체에 액세스할 수 없으므로 어떤 방식으로든 변경할 수 없습니다. 메서드는 복사본만 변경할 수 있습니다.  
  
 클래스 인스턴스는 값 형식이 아니라 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)입니다. 메서드에 [참조 형식을 값으로 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)하는 경우 메서드가 클래스 인스턴스에 대한 참조의 복사본을 받습니다. 즉, 메서드는 인스턴스 자체의 복사본이 아니라 인스턴스 주소의 복사본을 받습니다. 호출 메서드의 클래스 인스턴스에 주소가 있고, 호출된 메서드의 매개 변수에 주소의 복사본이 있으며, 두 주소가 모두 동일한 개체를 참조합니다. 매개 변수에 주소의 복사본만 포함되므로 호출된 메서드는 호출 메서드의 클래스 인스턴스 주소를 변경할 수 없습니다. 그러나 호출된 메서드는 주소를 사용하여 원래 주소와 복사본이 모두 참조하는 클래스 멤버에 액세스할 수 있습니다. 호출된 메서드가 클래스 멤버를 변경하는 경우 호출 메서드의 원래 클래스 인스턴스도 변경됩니다.  
  
 다음 예제의 출력에서 차이점을 보여 줍니다. `ClassTaker` 메서드가 매개 변수의 주소를 사용하여 클래스 인스턴스의 지정된 필드를 찾기 때문에 클래스 인스턴스의 `willIChange` 필드 값은 해당 메서드 호출에 의해 변경됩니다. 인수 값이 해당 주소의 복사본이 아니라 구조체 자체의 복사본이기 때문에 호출 메서드의 구조체 `willIChange` 필드는 `StructTaker` 메서드 호출에 의해 변경되지 않습니다. `StructTaker`는 복사본을 변경하고, `StructTaker` 호출이 완료되면 복사본이 손실됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)


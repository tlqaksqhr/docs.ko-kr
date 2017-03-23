---
title: "방법: 메서드에 대한 구조체 전달과 클래스 참조 전달 간의 차이점 이해(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "메서드[C#], 클래스와 구조체의 전달 비교"
  - "매개 변수 전달[C#], 구조체와 클래스 비교"
  - "구조체[C#], 메서드 매개 변수로 전달"
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# 방법: 메서드에 대한 구조체 전달과 클래스 참조 전달 간의 차이점 이해(C# 프로그래밍 가이드)
전달 하는 방법 다음 예제는  [구조체](../../../csharp/language-reference/keywords/struct.md) 메서드전달에서 다릅니다는  [클래스](../../../csharp/language-reference/keywords/class.md) 인스턴스메서드.  예제에서 인수 \(인스턴스구조체와클래스모두 값으로 전달 되 고 두 메서드 모두인수한필드의 값을 변경 합니다.  그러나구조체를 전달할 때 전달 된클래스의 인스턴스를 전달 하면 어떻게 전달 됩니다에서 다릅니다 때문에 두 메서드의 결과가 다릅니다.  
  
 구조체이므로  [값 형식](../../../csharp/language-reference/keywords/value-types.md), 시기를  [값으로구조체를 전달](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) 메서드메서드는 수신 하 고인수를구조체복사본에 작동 합니다.   메서드는메서드호출 된 원래구조체에 액세스할 수 없습니다 있습니다 및 따라서 어떤 방법으로 변경할 수 없습니다.  메서드는 복사본을 변경할 수 있습니다.  
  
 클래스인스턴스는  [참조 형식](../../../csharp/language-reference/keywords/reference-types.md),값 형식입니다.  때  [참조 형식값으로 전달 된](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) 메서드를메서드는 복사본을 참조 하는클래스인스턴스를 받습니다.  즉,메서드주소 인스턴스의 인스턴스 자체의 복사본이 복사본을 받습니다.  클래스인스턴스메서드호출 주소가 있습니다, 그리고 호출된 된메서드매개 변수복사본을 해당 주소를 있으며 두 주소가 동일한개체를 참조 하십시오.  매개 변수주소의 복사본만 포함 되어 있기 때문에 호출된 되는메서드클래스인스턴스메서드호출 주소를 변경할 수 없습니다.  그러나 호출된 되는메서드주소 원래 주소와 복사본을 참조 하는클래스멤버에 액세스할 수 있습니다.  원래클래스인스턴스메서드호출메서드호출된 되는클래스멤버를 변경 하는 경우에 변경 됩니다.  
  
 다음 예제에서는 출력 차이 보여 줍니다.  값은 `willIChange`필드클래스인스턴스의메서드를 호출 하 여 변경`ClassTaker` 는메서드주소가매개 변수에서클래스인스턴스의 지정 된필드를 사용 하기 때문에.    `willIChange`메서드호출에서구조체의필드메서드를 호출 하 여 변경 된`StructTaker`인수값은구조체자체 복사본을 해당 주소 않은 복사본이 있기 때문에.    `StructTaker`손실의 복사본 및 복사 되었을 때 변경 내용을 호출을 `StructTaker` 완료 됩니다.  
  
## 예제  
 [!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)
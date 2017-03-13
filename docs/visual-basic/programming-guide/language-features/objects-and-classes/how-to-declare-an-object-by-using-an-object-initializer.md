---
title: "How to: Declare an Object by Using an Object Initializer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring objects using object initializer"
  - "object initializers [Visual Basic]"
  - "initializers [Visual Basic]"
  - "Video How tos, Visual Basic"
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Declare an Object by Using an Object Initializer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체 이니셜라이저를 사용하여 단일 문에서 클래스의 인스턴스를 선언하고 인스턴스화할 수 있습니다.  또한 매개 변수화된 생성자를 호출하지 않고 동시에 하나 이상의 인스턴스 멤버를 초기화할 수 있습니다.  
  
 개체 이니셜라이저를 사용하여 명명된 형식의 인스턴스를 만드는 경우 클래스의 기본 생성자가 호출되고 지정하는 순서로 지정된 멤버의 초기화가 수행됩니다.  
  
 다음 절차에서는 세 가지 방식으로 `Student` 클래스의 인스턴스를 만드는 방법을 보여 줍니다.  클래스에는 이름, 성, 학년 속성 등이 포함됩니다.  세 가지 선언 각각은 `First` 속성이 "Michael"로 설정된 `Student`의 새 인스턴스를 만들고 `Last` 속성은 "Tucker"로 설정되며 다른 모든 멤버는 해당 기본값으로 설정됩니다.  절차에서 각 선언의 결과는 다음 예제와 동일하며 개체 이니셜라이저를 사용하지 않습니다.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 `Student` 클래스의 구현은 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)를 참조하십시오.  해당 항목에서 코드를 복사하여 클래스를 설정하고 작업할 `Student` 개체의 목록을 만들 수 있습니다.  
  
### 개체 이니셜라이저를 사용하여 명명된 클래스의 개체를 만들려면  
  
1.  생성자를 사용하려고 계획한 경우처럼 선언을 시작합니다.  
  
     `Dim student1 As New Student`  
  
2.  `With` 키워드와 중괄호로 묶은 초기화 목록을 입력합니다.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  초기화 목록에 초기화할 각 속성을 포함하고 초기 값을 해당 속성에 할당합니다.  속성 이름은 마침표 뒤에 옵니다.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     하나 이상의 클래스 멤버를 초기화할 수 있습니다.  
  
4.  또는 클래스의 새 인스턴스를 선언하고 값을 할당할 수 있습니다.  먼저 `Student`의 인스턴스를 선언합니다.  
  
     `Dim student2 As Student`  
  
5.  일반적인 방법으로 `Student`의 인스턴스 생성을 시작합니다.  
  
     `Dim student2 As Student = New Student`  
  
6.  `With`를 입력한 다음 개체 이니셜라이저를 입력하여 새 인스턴스의 하나 이상의 멤버를 초기화합니다.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  `As Student`를 생략하여 이전 단계에서 정의를 단순화할 수 있습니다.  이 작업을 수행하는 경우 컴파일러는 지역 형식 유추를 사용하여 `student3`이 `Student`의 인스턴스인지 확인합니다.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     자세한 내용은 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조하십시오.  
  
## 참고 항목  
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)   
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
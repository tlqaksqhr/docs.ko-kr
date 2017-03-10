---
title: "Key (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AnonymousKey"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "anonymous types [Visual Basic], key"
  - "Key [Visual Basic]"
  - "Key keyword [Visual Basic]"
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Key (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Key` 키워드를 사용하면 익명 형식의 속성에 대한 동작을 지정할 수 있습니다.  키 속성으로 지정하는 속성만 익명 형식 인스턴스 간 같음 테스트나 해시 코드 값 계산에 참여합니다.  키 속성의 값은 변경할 수 없습니다.  
  
 `Key` 키워드를 초기화 목록의 익명 형식 선언 앞에 배치하여 해당 익명 형식의 속성을 키 속성으로 지정합니다.  다음 예제에서 `Airline` 및 `FlightNo`는 키 속성이지만 `Gate`는 키 속성이 아닙니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/key_1.vb)]  
  
 새 익명 형식이 만들어질 때 <xref:System.Object>에서 직접 상속됩니다.  컴파일러는 세 개의 상속된 멤버인 <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>을 재정의합니다.  <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A>에 대해 생성되는 재정의 코드는 키 속성을 기반으로 합니다.  형식에 키 속성이 없는 경우 <xref:System.Object.GetHashCode%2A> 및 <xref:System.Object.Equals%2A>가 재정의되지 않습니다.  
  
## 같음  
 두 개의 익명 형식 인스턴스는 같은 형식의 인스턴스이고 해당 키 속성의 값이 같은 경우 같습니다.  다음 예제에서 `flight2`는 이전 예제의 `flight1`과 같은데 그 이유는 이 두 인스턴스가 동일한 익명 형식의 인스턴스이고 키 속성의 값이 일치하기 때문입니다.  하지만 `flight3`은 `flight1`과 같지 않은데 그 이유는 키 속성인 `FlightNo`의 값이 다르기 때문입니다.  인스턴스 `flight4`는 `flight1`과 다른 속성을 키 속성으로 지정하므로 두 인스턴스는 동일한 형식이 아닙니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/key_2.vb)]  
  
 두 인스턴스의 이름, 형식, 순서 및 값이 같더라도 키가 아닌 속성으로만 선언된 경우 이 두 인스턴스는 같지 않습니다.  키 속성이 없는 인스턴스는 자신하고만 같습니다.  
  
 두 익명 형식 인스턴스가 동일한 익명 형식의 인스턴스가 되는 조건에 대한 자세한 내용은 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하십시오.  
  
## 해시 코드 계산  
 <xref:System.Object.Equals%2A>와 마찬가지로 익명 형식에 대해 <xref:System.Object.GetHashCode%2A>에 정의되는 해시 함수도 해당 형식의 키 속성을 기반으로 합니다.  다음 예제에서는 키 속성과 해시 코드 값 사이의 상호 작용을 보여 줍니다.  
  
 모든 키 속성 값이 같은 익명 형식 인스턴스는 키 속성이 아닌 속성의 값이 일치하지 않는 경우에도 동일한 해시 코드 값을 가집니다.  다음 문에서는 `True`를 반환합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/key_3.vb)]  
  
 하나 이상의 키 속성 값이 다른 익명 형식 인스턴스는 서로 다른 해시 코드 값을 가집니다.  다음 문에서는 `False`를 반환합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/key_4.vb)]  
  
 서로 다른 속성을 키 속성으로 지정하는 익명 형식 인스턴스는 동일한 형식의 인스턴스가 아닙니다.  이러한 인스턴스는 모든 속성의 이름과 값이 같은 경우에도 서로 다른 해시 코드 값을 가집니다.  다음 문에서는 `False`를 반환합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/key_5.vb)]  
  
## 읽기 전용 값  
 키 속성의 값은 변경할 수 없습니다.  예를 들어 앞 예제의 `flight1`에서 `Airline` 및 `FlightNo` 필드는 읽기 전용이지만 `Gate`는 변경할 수 있습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/key_6.vb)]  
  
## 참고 항목  
 [Anonymous Type Definition](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
---
title: "End &lt;keyword&gt; Statement (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.EndDefinition"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "End keyword"
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# End &lt;keyword&gt; Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

추가 키워드가 이어질 경우 해당 키워드로 시작된 문 블록의 정의를 종료합니다.  
  
## 구문  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## 요소  
 `End`  
 필수 요소.  프로그래밍 요소의 정의를 종료합니다.  
  
 `AddHandler`  
 사용자 지정 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)에서 짝이 되는 `AddHandler` 문으로 시작된 `AddHandler` 접근자를 종료하는 데 필요합니다.  
  
 `Class`  
 짝이 되는 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)으로 시작된 클래스 정의를 종료하는 데 필요합니다.  
  
 `Enum`  
 짝이 되는 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)으로 시작된 열거형 정의를 종료하는 데 필요합니다.  
  
 `Event`  
 짝이 되는 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)으로 시작된 `Custom` 이벤트 정의를 종료하는 데 필요합니다.  
  
 `Function`  
 짝이 되는 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)으로 시작된 `Function` 프로시저 정의를 종료하는 데 필요합니다.  실행 중에 `End` `Function` 문을 만나게 되면 호출 코드로 제어가 반환됩니다.  
  
 `Get`  
 짝이 되는 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)으로 시작된 `Property` 프로시저 정의를 종료하는 데 필요합니다.  실행 중에 `End` `Get` 문을 만나게 되면 속성 값을 요청하는 문으로 제어가 반환됩니다.  
  
 `If`  
 짝이 되는 `If` 문으로 시작된 `If`...`Then`...`Else` 블록 정의를 종료하는 데 필요합니다.  자세한 내용은 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)를 참조하십시오.  
  
 `Interface`  
 짝이 되는 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)으로 시작된 인터페이스 정의를 종료하는 데 필요합니다.  
  
 `Module`  
 짝이 되는 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)으로 시작된 모듈 정의를 종료하는 데 필요합니다.  
  
 `Namespace`  
 짝이 되는 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)으로 시작된 네임스페이스 정의를 종료하는 데 필요합니다.  
  
 `Operator`  
 짝이 되는 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)으로 시작된 연산자 정의를 종료하는 데 필요합니다.  
  
 `Property`  
 짝이 되는 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)으로 시작된 속성 정의를 종료하는 데 필요합니다.  
  
 `RaiseEvent`  
 사용자 지정 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)에서 짝이 되는 `RaiseEvent` 문으로 시작된 `RaiseEvent` 접근자를 종료하는 데 필요합니다.  
  
 `RemoveHandler`  
 사용자 지정 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)에서 짝이 되는 `RemoveHandler` 문으로 시작된 `RemoveHandler` 접근자를 종료하는 데 필요합니다.  
  
 `Select`  
 짝이 되는 `Select` 문으로 시작된 `Select`...`Case` 블록 정의를 종료하는 데 필요합니다.  자세한 내용은 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md)를 참조하십시오.  
  
 `Set`  
 짝이 되는 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)으로 시작된 `Property` 프로시저 정의를 종료하는 데 필요합니다.  실행 중에 `End` `Set` 문을 만나게 되면 속성 값을 설정하는 문으로 제어가 반환됩니다.  
  
 `Structure`  
 짝이 되는 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)으로 시작된 구조체 정의를 종료하는 데 필요합니다.  
  
 `Sub`  
 짝이 되는 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)으로 시작된 `Sub` 프로시저 정의를 종료하는 데 필요합니다.  실행 중에 `End` `Sub` 문을 만나게 되면 호출 코드로 제어가 반환됩니다.  
  
 `SyncLock`  
 짝이 되는 `SyncLock` 문으로 시작된 `SyncLock` 블록 정의를 종료하는 데 필요합니다.  자세한 내용은 [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md)를 참조하십시오.  
  
 `Try`  
 짝이 되는 `Try` 문으로 시작된 `Try`...`Catch`...`Finally` 블록 정의를 종료하는 데 필요합니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)를 참조하십시오.  
  
 `While`  
 짝이 되는 `While` 문으로 시작된 `While` 루프 정의를 종료하는 데 필요합니다.  자세한 내용은 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)를 참조하십시오.  
  
 `With`  
 짝이 되는 `With` 문으로 시작된 `With` 블록 정의를 종료하는 데 필요합니다.  자세한 내용은 [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)를 참조하십시오.  
  
## 설명  
 키워드가 더 없으면 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md) 실행이 바로 종료됩니다.  
  
 `End` 키워드 앞에 숫자 기호\(`#`\)가 올 경우 해당 지시문으로 시작된 전처리 블록이 종료됩니다.  
  
 `#End`  
 필수 요소.  전처리 블록의 정의를 종료합니다.  
  
 `#ExternalSource`  
 짝이 되는 [\#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md)으로 시작된 외부 소스 블록을 종료하는 데 필요합니다.  
  
 `#If`  
 짝이 되는 `#If` 지시문으로 시작된 조건부 컴파일 블록을 종료하는 데 필요합니다.  자세한 내용은 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)를 참조하십시오.  
  
 `#Region`  
 짝이 되는 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)으로 시작된 소스 영역 블록을 종료하는 데 필요합니다.  
  
## 스마트 장치 개발자 참고 사항  
 추가 키워드를 사용해야 `End` 문을 사용할 수 있습니다.  
  
## 참고 항목  
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)
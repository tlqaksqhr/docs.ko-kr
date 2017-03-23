---
title: "Differences Between Properties and Variables in Visual Basic | Microsoft Docs"
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
  - "property values"
  - "variables [Visual Basic]"
  - "Visual Basic code, procedures"
  - "values, properties"
  - "variables [Visual Basic], definition"
  - "Visual Basic code, variables"
  - "Visual Basic code, properties"
  - "properties [Visual Basic], values"
  - "properties [Visual Basic], defined"
  - "variables [Visual Basic], and properties"
  - "properties [Visual Basic], and variables"
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Differences Between Properties and Variables in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수와 속성은 모두 액세스할 수 있는 값을 나타내지만  저장소와 구현에 있어 차이가 납니다.  
  
## 변수  
 *변수*는 메모리 위치에 직접적으로 해당합니다.  단일 선언문을 사용하여 변수를 정의합니다.  변수는 프로시저 내에 정의되어 해당 프로시저 내에서만 사용할 수 있는 *지역 변수*이거나 모듈, 클래스 또는 구조체에 정의되지만 프로시저 내에 정의되지 않는 *멤버 변수*일 수 있습니다.  멤버 변수를 *필드*라고도 합니다.  
  
## 속성  
 *속성*은 모듈, 클래스 또는 구조체에 정의되는 데이터 요소입니다.  `Property` 및 `End Property` 문 사이의 코드 블록을 사용하여 속성을 정의합니다.  코드 블록에는 `Get` 프로시저 또는 `Set` 프로시저가 포함되어 있거나 두 프로시저가 모두 포함되어 있습니다.  이러한 프로시저를 *속성 프로시저* 또는 *속성 접근자*라고 합니다.  이러한 프로시저는 속성 값을 검색 또는 저장하는 것 외에 액세스 카운터를 업데이트하는 등의 사용자 지정 작업을 수행할 수도 있습니다.  
  
## 차이점  
 다음 표에서는 변수와 속성의 몇 가지 중요한 차이점을 보여 줍니다.  
  
|차이점|변수|Property|  
|---------|--------|--------------|  
|선언|단일 선언문|코드 블록에 있는 일련의 문|  
|구현|단일 저장소 위치|실행 코드\(속성 프로시저\)|  
|저장소|변수 값과 직접 연결됨|일반적으로 속성의 포함하는 클래스 또는 모듈의 외부에서 사용할 수 없는 내부 저장소를 가짐<br /><br /> 속성 값은 저장된 요소로 존재하거나 존재하지 않을 수 있음<sup>1</sup>|  
|실행 코드|없음|적어도 하나 이상의 프로시저를 가져야 함|  
|읽기 및 쓰기 권한|읽기\/쓰기 또는 읽기 전용|읽기\/쓰기, 읽기 전용 또는 쓰기 전용|  
|사용자 지정 작업\(값 수락 또는 반환 외\)|불가능|속성 값 설정 또는 검색의 일부로 수행 가능|  
  
 <sup>1</sup> 변수와 달리 속성 값은 저장소의 단일 항목에 직접 해당되지 않을 수 있습니다.  편의상 또는 보안을 위해 저장소를 여러 부분으로 분할하거나 값을 암호화된 형식으로 저장할 수 있습니다.  이러한 경우에 `Get` 프로시저는 분할된 부분을 조합하거나 저장된 값을 해독하고 `Set` 프로시저는 새 값을 암호화하거나 이러한 값을 여러 저장소로 분할하여 저장합니다.  속성 값은 시간과 같이 순간적일 수 있으며 이 경우에는 속성에 액세스할 때마다 `Get` 프로시저가 속성 값을 즉시 계산합니다.  
  
## 참고 항목  
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)
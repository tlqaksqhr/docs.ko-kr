---
title: "Ansi (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Ansi"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Declare statement, marshaling strings"
  - "ANSI, Visual Basic"
  - "ANSI"
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Ansi (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic에서 선언되는 외부 프로시저의 이름에 관계없이 모든 문자열을 ANSI\(American National Standards Institute\) 값으로 마샬링하도록 지정합니다.  
  
 프로젝트 외부에서 정의된 프로시저를 호출하면 Visual Basic 컴파일러가 해당 프로시저를 제대로 호출하는 데 필요한 정보에 액세스할 수 없습니다.  이 정보에는 프로시저의 위치, 식별 방법, 호출 시퀀스 및 반환 형식, 사용한 문자열 문자 집합 등이 포함됩니다.  [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)은 외부 프로시저에 대한 참조를 만들고 이와 같은 필요한 정보를 제공합니다.  
  
 `Declare` 문의 `charsetmodifier` 부분은 외부 프로시저를 호출하는 동안 문자열을 마샬링하는 데 사용할 문자 집합 정보를 제공합니다.  또한 외부 파일에서 외부 프로시저 이름을 검색하는 방법에도 영향을 줍니다.  `Ansi` 한정자는 Visual Basic에서 모든 문자열을 ANSI 값으로 마샬링하고 검색 중 이름을 수정하지 않은 채 프로시저를 조회하도록 지정합니다.  
  
 문자 집합 한정자가 지정되어 있지 않으면 `Ansi`가 기본값입니다.  
  
## 설명  
 `Ansi` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## 스마트 장치 개발자 참고 사항  
 이 키워드는 지원되지 않습니다.  
  
## 참고 항목  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
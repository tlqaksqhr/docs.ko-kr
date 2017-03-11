---
title: "Auto (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Auto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Auto keyword, external references"
  - "Declare statement, marshaling strings"
  - "Auto keyword"
  - "Auto keyword, marshaling strings"
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Auto (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언되는 외부 프로시저의 외부 이름을 기반으로 .NET Framework 규칙에 따라 Visual Basic에서 문자열을 마샬링하도록 지정합니다.  
  
 프로젝트 외부에서 정의된 프로시저를 호출하면 Visual Basic 컴파일러가 해당 프로시저를 제대로 호출하는 데 필요한 정보에 액세스할 수 없습니다.  이 정보에는 프로시저의 위치, 식별 방법, 호출 시퀀스 및 반환 형식, 사용한 문자열 문자 집합 등이 포함됩니다.  [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)은 외부 프로시저에 대한 참조를 만들고 이와 같은 필요한 정보를 제공합니다.  
  
 `Declare` 문의 `charsetmodifier` 부분은 외부 프로시저를 호출하는 동안 문자열을 마샬링하는 데 사용할 문자 집합 정보를 제공합니다.  또한 외부 파일에서 외부 프로시저 이름을 검색하는 방법에도 영향을 줍니다.  `Auto` 한정자는 Visual Basic에서 .NET Framework 규칙에 따라 문자열을 마샬링하도록 지정하며, 런타임 플랫폼의 기본 문자 집합을 결정하고 초기 검색이 실패할 경우 외부 프로시저 이름을 수정하도록 지정합니다.  자세한 내용은 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)의 "문자 집합"을 참조하십시오.  
  
 문자 집합 한정자가 지정되어 있지 않으면 `Ansi`가 기본값입니다.  
  
## 설명  
 `Auto` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## 스마트 장치 개발자 참고 사항  
 이 키워드는 지원되지 않습니다.  
  
## 참고 항목  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)   
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
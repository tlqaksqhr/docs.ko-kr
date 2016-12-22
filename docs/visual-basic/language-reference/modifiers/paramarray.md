---
title: "ParamArray (Visual Basic) | Microsoft Docs"
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
  - "vb.ParamArray"
  - "ParamArray"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ParamArray keyword"
  - "ParamArray keyword, syntax"
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ParamArray (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

프로시저 매개 변수가 지정된 데이터 형식의 선택적 요소 배열임을 지정합니다.  `ParamArray`는 매개 변수 목록의 마지막 매개 변수에만 사용할 수 있습니다.  
  
## 설명  
 `ParamArray`를 사용하면 프로시저에 원하는 개수만큼 인수를 전달할 수 있습니다.  `ParamArray` 매개 변수는 항상 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)을 사용하여 선언됩니다.  
  
 적절한 데이터 형식의 배열이나 쉼표로 구분된 값 목록을 전달하거나 아무런 값도 전달하지 않아 `ParamArray` 매개 변수에 하나 이상의 인수를 제공할 수 있습니다.  자세한 내용은 [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)의 "ParamArray 호출"을 참조하십시오.  
  
> [!IMPORTANT]
>  무제한으로 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량에 오버런이 발생할 위험이 있습니다.  호출 코드로부터 매개 변수 배열을 받는 경우에는 해당 길이를 테스트해야 합니다. 이때 길이가 너무 길어서 해당 배열을 응용 프로그램에 사용할 수 없을 때는 적절한 조치를 취합니다.  
  
 `ParamArray` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
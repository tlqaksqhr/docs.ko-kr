---
title: "Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths | Microsoft Docs"
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
  - "bc42105"
  - "vbc42105"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42105"
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<procedurename\>' 함수가 일부 코드 경로에 대해서만 값을 반환합니다.'Return' 문이 있는지 확인하십시오.  
  
 `Function` 프로시저의 코드에 값을 반환하지 않는 경로가 하나 이상 있습니다.  
  
 다음 중 한 가지 방법으로 `Function` 프로시저에서 값을 반환할 수 있습니다.  
  
-   [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)에 값을 포함합니다.  
  
-   `Function` 프로시저 이름에 값을 할당한 다음 `Exit Function` 문을 수행합니다.  
  
-   `Function` 프로시저 이름에 값을 할당한 다음 `End Function` 문을 수행합니다.  
  
 제어가 `Exit Function` 또는 `End Function`으로 전달되고 프로시저 이름에 값을 할당하지 않은 경우 프로시저는 반환 데이터 형식의 기본값을 반환합니다.  자세한 내용은 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)의 "동작"을 참조하십시오.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42105  
  
### 이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사하고 반환의 원인이 되는 모든 문 앞에 값을 할당해야 합니다.  
  
     항상 `Return` 문을 사용하는 경우에는 프로시저의 모든 반환에서 값을 반환하게 하는 것이 더 간단합니다.  이렇게 하려면 `End Function` 앞에 오는 마지막 문이 `Return` 문이어야 합니다.  
  
## 참고 항목  
 [Function 프로시저](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)
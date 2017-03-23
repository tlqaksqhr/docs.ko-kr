---
title: "Alias Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Alias"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Alias keyword"
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Alias Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

키워드는 외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.  
  
## 설명  
 `Alias` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 다음 예제에서는 `Alias` 키워드를 사용하여 advapi32.dll의 함수 이름인 `GetUserNameA`를 제공합니다. 이 예제에서는 대신 함수 이름으로 `getUserName`이 사용됩니다.  `getUserName` 함수는 현재 사용자의 이름을 표시하는 하위 `getUser`에서 호출됩니다.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## 참고 항목  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
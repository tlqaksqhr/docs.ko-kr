---
title: "Mid Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.MidB"
  - "vb.Mid"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "substrings, Mid statement"
  - "strings [Visual Basic], substrings"
  - "Mid statement"
  - "strings [Visual Basic], replacing"
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Mid Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`String` 변수에 있는 지정한 수의 문자를 다른 문자열의 문자로 바꿉니다.  
  
## 구문  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## 요소  
 `Target`  
 필수 요소.  수정할 `String` 변수의 이름입니다.  
  
 `Start`  
 필수 요소.  `Integer` 식입니다.  `Target`에서 텍스트 교체를 시작할 문자 위치입니다.  `Start`는 1부터 시작하는 인덱스를 사용합니다.  
  
 `Length`  
 선택적 요소.  `Integer` 식입니다.  바꿀 문자의 개수입니다.  문자의 개수를 생략하면 `String` 전체가 사용됩니다.  
  
 `StringExpression`  
 필수 요소.  `Target`의 일부를 바꾸는 `String` 식입니다.  
  
## 예외  
  
|예외 형식|조건|  
|-----------|--------|  
|<xref:System.ArgumentException>|`Start`가 0보다 작거나 같거나 `Length`가 0보다 작습니다.|  
  
## 설명  
 바뀐 문자 수는 항상 `Target`의 문자 수보다 작거나 같습니다.  
  
 Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수와 `Mid` 문이 있습니다.  이 두 요소는 모두 문자열 중 지정한 개수의 문자에 대해 작동하지만 `Mid` 함수는 해당 문자를 반환하고 `Mid` 문은 해당 문자를 바꿉니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>를 참조하십시오.  
  
> [!NOTE]
>  이전 Visual Basic 버전의 `MidB` 문은 문자가 아니라 바이트로 된 부분 문자열을 바꿉니다.  이 함수는 주로 DBCS\(더블바이트 문자 집합\) 응용 프로그램의 문자열을 변환하는 데 사용됩니다.  모든 Visual Basic 문자열은 유니코드이며 `MidB`는 이제 지원되지 않습니다.  
  
## 예제  
 다음 예제에서는 `Mid` 문을 사용하여 문자열 변수에 있는 지정한 수의 문자를 다른 문자열의 문자로 바꿉니다.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## 요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **모듈:** `Strings`  
  
 **어셈블리:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime-md.md)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Introduction to Strings in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
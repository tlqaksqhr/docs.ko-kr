---
title: "Optional (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Optional"
  - "vb.optional"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Optional keyword, contexts"
  - "Optional keyword"
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Optional (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저를 호출할 때 프로시저 인수를 생략할 수 있도록 지정합니다.  
  
## 설명  
 각 선택적 매개 변수에 대해 해당 매개 변수의 기본값으로 상수 식을 지정 해야 합니다.  식에서 계산 하는 경우  [아무것도](../../../visual-basic/language-reference/nothing.md), 기본값 데이터 형식의 값 매개 변수의 기본 값으로 사용 됩니다.  
  
 선택적 매개 변수 매개 변수 목록을 포함 하는 경우에 오는 모든 매개 변수에 선택적 이어야 합니다.  
  
 `Optional` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
-   [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  함께 또는 선택적 매개 변수 없이 프로시저를 호출 하는 경우에 위치 또는 이름 인수를 전달할 수 있습니다.  자세한 내용은 [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)를 참조하십시오.  
  
> [!NOTE]
>  선택적 매개 변수를 사용 하는 프로시저 오버 로드를 사용 하 여 정의할 수도 있습니다.  하나의 선택적 매개 변수가 있는 경우 프로시저 매개 변수를 받아들이는, 하나 하나 하지 않는 두 개의 오버 로드 된 버전을 정의할 수 있습니다.  자세한 내용은 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 선택적 매개 변수가 있는 프로시저를 정의 합니다.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## 예제  
 다음 예제에서는 인수는 위치로 전달 인수를 이름으로 전달 하 고 프로시저를 호출 하는 방법을 보여 줍니다.  프로시저는 두 개의 선택적 매개 변수가 있습니다.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## 참고 항목  
 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
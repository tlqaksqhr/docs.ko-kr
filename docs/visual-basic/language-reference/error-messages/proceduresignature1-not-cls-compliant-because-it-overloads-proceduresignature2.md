---
title: "&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40035"
  - "bc40035"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40035"
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다른 프로시저나 속성을 재정의하고 각각의 매개 변수 목록의 유일한 차이점이 가변 배열의 중첩 수준 또는 차수가 지정된 배열인 프로시저나 속성이 `<CLSCompliant(True)>`로 표시되어 있습니다.  
  
 아래 선언에서 첫째와 셋째 선언은 이 오류를 생성합니다.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 둘째 선언은 원래의 1차원 매개 변수를 `arrayParam` 배열의 배열로 변경합니다.  셋째 선언은 `arrayParam`을 2차원 배열\(차수 2\)로 변경합니다.  Visual Basic을 사용하면 오버로드가 이러한 변경 방법 중 하나에 의해서만 달라질 수 있지만 오버로딩은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격을 준수하지 않습니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 이 특성의 `isCompliant` 매개 변수를 `True`나 `False`로 설정하여 규격 준수 여부를 나타내야 합니다.  이 매개 변수의 기본값이 없으므로 값을 제공해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 요소에 적용하지 않으면 이 요소는 CLS 규격이 아닌 것으로 간주됩니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40035  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요한 경우 이 도움말 페이지에 언급된 변경 방법만이 아닌 여러 가지 방법으로 서로 다르게 오버로드를 정의합니다.  
  
-   오버로드가 이 도움말 페이지에 언급된 변경 사항만 다르게 해야 할 경우 <xref:System.CLSCompliantAttribute>를 해당 정의에서 제거하거나 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
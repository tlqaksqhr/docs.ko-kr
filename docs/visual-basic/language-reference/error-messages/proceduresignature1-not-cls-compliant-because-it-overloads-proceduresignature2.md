---
title: "&lt;proceduresignature1&gt; 는 오버 로드 하므로 CLS 규격이 아닙니다 &lt;proceduresignature2&gt; 에서 배열 매개 변수 형식 배열의 또는 배열 매개 변수 형식의 차수만 다른 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
dev_langs:
- VB
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 984c04a107444036b980439b231d27a8a81656c1
ms.lasthandoff: 03/13/2017

---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; 는 오버 로드 하므로 CLS 규격이 아닙니다 &lt;proceduresignature2&gt; 에서 배열 매개 변수 형식 배열의 또는 배열 매개 변수 형식의 차수만 다른
프로시저 또는 속성으로 표시 되어 `<CLSCompliant(True)>` 때 다른 프로시저 또는 속성을 재정의 하 고 매개 변수 목록은 간의 유일한 차이점은 가변 배열의 중첩 수준 또는 배열의 차수입니다.  
  
 두 번째 및 세 번째 선언 다음 선언에이 오류를 생성합니다.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 원래&1; 차원 매개 변수를 변경 하는 두 번째 선언 `arrayParam` 배열의 배열에 있습니다. 세 번째 선언 변경 내용 `arrayParam` 를 2 차원 배열 (순위 2). Visual Basic만 달라 서는 이러한 변경 중 하나를 오버 로드를 허용 하는 동안 이러한 오버 로드와 호환 되지 않는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) (CLS).  
  
 적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute> 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute>  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40035  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격을 필요한 경우이 도움말 페이지에 언급 된 변경만 보다 많은 방법으로 서로 다를 오버 로드를 정의 합니다.  
  
-   오버 로드 다를 사용 해야 하는 경우이 도움말에 언급 된 변경만 하 여 페이지에서 제거 된 <xref:System.CLSCompliantAttribute>해당 정의에서 표시 하거나 `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>참고 항목  
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [프로시저 오버 로드](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)

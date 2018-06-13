---
title: '&lt;proceduresignature1&gt; 는 오버 로드 하므로 CLS 규격이 아닙니다 &lt;proceduresignature2&gt; 에서 배열 매개 변수 형식의 배열 또는 배열 매개 변수 형식의 차수만 다른'
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 0d150dad8d32b4bfa2b9e549e068ef24382d0eba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594730"
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; 는 오버 로드 하므로 CLS 규격이 아닙니다 &lt;proceduresignature2&gt; 에서 배열 매개 변수 형식의 배열 또는 배열 매개 변수 형식의 차수만 다른
프로시저 또는 속성으로 표시 되어 `<CLSCompliant(True)>` 때 다른 프로시저 또는 속성을 재정의 하 고 매개 변수 목록은 간의 유일한 차이점은 중첩 수준의 가변된 배열 또는 배열의 차수입니다.  
  
 다음 선언에 두 번째 및 세 번째 선언이이 오류를 생성합니다.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 두 번째 선언에는 원래 1 차원 매개 변수 변경 `arrayParam` 배열의 배열에 있습니다. 세 번째 선언 변경 내용 `arrayParam` 를 2 차원 배열 (rank 2). Visual Basic에서는 이러한 변경 중 하나에 의해서만 달라를 오버 로드를 허용 하는 동안 이러한 오버 로드와 호환 되지 않는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40035  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격이 필요 하면 다양 한 방법으로이 도움말 페이지에 언급 된 변경만 보다는 서로 다르게 오버 로드를 정의 합니다.  
  
-   이 도움말에 언급 된 변경에 의해서만 페이지에서 제거 하는 오버 로드 다 필요한 경우는 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다.  
  
## <a name="see-also"></a>참고 항목  
   
 [프로시저 오버로딩](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)

---
title: 함수 &#39; &lt;procedurename&gt; &#39; 대상이&#39;모든 코드 경로 에서만 값을 반환 하는 t
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 4c18c6229eb170e8a688aaa2734ae8fbfa081061
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>함수 &#39; &lt;procedurename&gt; &#39; 대상이&#39;모든 코드 경로 에서만 값을 반환 하는 t
함수 '\<procedurename >' 모든 코드 경로 대해서만 값을 반환 합니다. 'Return' 문은 없습니다?  
  
 A `Function` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.  
  
 값을 반환할 수는 `Function` 절차는 다음과 같은 방법 중 하나:  
  
-   에 대 한 값이 포함 된 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
-   값을 할당는 `Function` 프로시저 이름을 지정 하 고 다음을 수행할는 `Exit Function` 문.  
  
-   값을 할당는 `Function` 프로시저 이름을 지정 하 고 다음을 수행할는 `End Function` 문.  
  
 컨트롤을 전달 하는 경우 `Exit Function` 또는 `End Function` 및 프로시저 이름에 값을 할당 하지 않은, 프로시저가 반환 데이터 형식의 기본값을 반환 합니다. 자세한 내용은의 "동작" 참조 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42105  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.  
  
     항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문. 이렇게 하면, 앞의 마지막 문이 `End Function` 이어야 합니다는 `Return` 문.  
  
## <a name="see-also"></a>참고 항목  
 [Function 프로시저](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)

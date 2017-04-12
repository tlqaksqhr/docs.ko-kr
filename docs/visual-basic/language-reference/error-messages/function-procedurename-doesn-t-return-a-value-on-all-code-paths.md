---
title: "함수 &quot;&lt;procedurename&gt;&quot; 모든 코드 경로에서 값을 반환 하지 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
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
ms.openlocfilehash: 288fdf7c4845b20283681d9eb3504ac314f1ddd2
ms.lasthandoff: 03/13/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>함수 '&lt;procedurename&gt;' 모든 코드 경로 대해서만 값을 반환
함수 '\<procedurename > ' 모든 코드 경로 대해서만 값을 반환 합니다. '에 Return' 문이 없습니다?  
  
 A `Function` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.  
  
 값을 반환할 수는 `Function` 절차는 다음 방법 중 하나:  
  
-   값을 포함 한 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
-   에 값을 할당은 `Function` 프로시저 이름을 지정 하 고 다음을 수행는 `Exit Function` 문입니다.  
  
-   에 값을 할당은 `Function` 프로시저 이름을 지정 하 고 다음을 수행는 `End Function` 문입니다.  
  
 컨트롤을 전달 하는 경우 `Exit Function` 또는 `End Function` 및 프로시저 이름에 값을 할당 하지 않은, 프로시저의 반환 데이터 형식이 기본 값을 반환 합니다. 자세한 내용은 "동작"의 참조 [Function 문의](../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42105  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.  
  
     항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문입니다. 이렇게 하면, 앞의 마지막 문이 `End Function` 있어야는 `Return` 문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Function 프로시저](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)   
 [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)

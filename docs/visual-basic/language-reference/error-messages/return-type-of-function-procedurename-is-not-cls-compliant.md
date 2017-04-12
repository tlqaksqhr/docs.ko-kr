---
title: "함수의 반환 형식이 &quot;&lt;procedurename&gt;&quot; CLS 규격이 아닌 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
dev_langs:
- VB
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
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
ms.openlocfilehash: 99a07393d976dc99998b29d2ba2cd7d554ec1bad
ms.lasthandoff: 03/13/2017

---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>함수의 반환 형식이 '&lt;procedurename&gt;'는 CLS 규격이 아닙니다
A `Function` 절차로 표시 되어 `<CLSCompliant(True)>` 로 표시 된 형식을 반환 하지만 `<CLSCompliant(False)>`표시 되지 않은, 또는 호환 되지 않는 형식 이므로 한정 하지 않습니다.  
  
 프로시저가 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다. 이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.  
  
 다음 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute> 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute>  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40027  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   하는 경우는 `Function` 프로시저가 특정 형식을 반환 해야, <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute> 제거 프로시저는 CLS 규격일 수 없습니다.  
  
-   하는 경우는 `Function` 프로시저 CLS 규격 이어야, 가장 가까운 CLS 규격 형식으로 반환 형식을 변경 해야 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소에는 16 비트 정수를 반환 하는 경우로 선언 `Short` 대신 `Integer` 관리 되는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

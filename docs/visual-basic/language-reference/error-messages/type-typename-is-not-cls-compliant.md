---
title: "형식 &lt;typename&gt; CLS 규격이 아닌 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
dev_langs:
- VB
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b28ae4ff4a4665040f3e97477d6197065762654a
ms.lasthandoff: 03/13/2017

---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a>형식 &lt;typename&gt; CLS 규격이 아닙니다
변수, 속성 또는 함수 반환 CLS 호환 되지 않는 데이터 형식으로 선언 됩니다.  
  
 와 호환 되도록 응용 프로그램은 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS ()를 CLS 규격 형식에만 사용 해야 합니다.  
  
 다음 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **오류 ID:** BC40041  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   응용 프로그램 CLS 규격 이어야 하는 경우 가장 가까운 CLS 규격 형식으로이 요소의 데이터 형식을 변경 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   응용 프로그램에서는 CLS 규격 필요가 없는 경우 아무 것도 변경할 필요가 없습니다. 그러나 비 호환성 인식 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

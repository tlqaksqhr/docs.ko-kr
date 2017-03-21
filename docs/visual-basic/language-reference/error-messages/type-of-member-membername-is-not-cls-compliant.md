---
title: "형식의 멤버 &quot;&lt;membername&gt;&quot; CLS 규격이 아닌 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
dev_langs:
- VB
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
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
ms.openlocfilehash: 3ea35f54cf8f0fb5a11148b8017456feb8d3524a
ms.lasthandoff: 03/13/2017

---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>형식의 멤버 '&lt;membername&gt;'는 CLS 규격이 아닙니다
이 멤버는 없습니다에 대해 지정 된 데이터 형식을의 일부는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) (CLS). 이 오류가 사용자 구성 요소에서 때문에 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 및 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 이 데이터 형식을 지원 합니다. 그러나 CLS 규격 코드로 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않습니다. 이러한 구성 요소를 성공적으로 구성 요소와 상호 작용할 못할 수도 있습니다.  
  
 다음 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC40025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   구성 요소가 다른만 상호 작용 하는 경우 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 구성 요소 또는 다른 구성 요소와 인터페이스 하지, 아무 것도 변경할 필요가 없습니다.  
  
-   하지 않고 작성 된 구성 요소와 같이 하는 경우는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]리플렉션을 통해를 확인할 수 있습니다, 또는 문서에서 지원 여부이 데이터 형식입니다. 그렇지 않으면 아무 것도 변경할 필요가 없습니다.  
  
-   이 데이터 형식을 지원 하지 않는 구성 요소와 같이 하는 경우 가장 가까운 CLS 규격 형식으로 대체 해야 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소에 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [리플렉션](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)   
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

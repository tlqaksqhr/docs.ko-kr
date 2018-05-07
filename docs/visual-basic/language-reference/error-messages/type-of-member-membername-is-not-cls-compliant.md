---
title: 형식의 멤버 &#39; &lt;membername&gt; &#39; CLS 규격이 아닙니다
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 5735b5104884a702a649a029116be7446424ec67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>형식의 멤버 &#39; &lt;membername&gt; &#39; CLS 규격이 아닙니다
이 멤버는 없습니다에 대해 지정 된 데이터 형식에 속하지는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS). 때문에 사용자 구성 요소에서 오류는는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 및 Visual Basic에는이 데이터 형식을 지원 합니다. 그러나 엄격 하 게 CLS 규격 코드 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않습니다. 이러한 구성 요소를 성공적으로 구성 요소와 상호 작용할 수 수 있습니다.  
  
 다음 Visual Basic 데이터 형식 CLS 호환 되지 않습니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC40025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   구성 요소가 다른만 상호 작용 하는 경우 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 구성 요소 또는 다른 모든 구성 요소와 인터페이스 하지, 아무 것도 변경할 필요가 없습니다.  
  
-   대해 작성 되지 않은 구성 요소와 조작 하는 경우는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], 결정, 리플렉션을 통해 수 있습니다 또는 문서에서 지원 하는지 여부이 데이터 형식입니다. 그렇지 않으면 아무 것도 변경할 필요가 없습니다.  
  
-   이 데이터 형식을 지원 하지 않는 구성 요소와 같이 하는 경우에 가장 가까운 CLS 규격 형식으로 대체 해야 있습니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소를 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 Visual Basic 코드에서.  
  
## <a name="see-also"></a>참고 항목  
 [리플렉션](../../../framework/reflection-and-codedom/reflection.md)  
 

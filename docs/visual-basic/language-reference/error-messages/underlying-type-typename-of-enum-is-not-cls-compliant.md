---
title: "내부 형식 &lt;typename&gt; 열거형의는 CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e054f8d992154f66ab1d48a477a7e04900aa5b4d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a>내부 형식 &lt;typename&gt; 열거형의는 CLS 규격이 아닙니다
이 열거형은 하지에 대해 지정 된 데이터 형식에 속하지는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS). 때문에 사용자 구성 요소에서 오류는는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 및 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 이 데이터 형식을 지원 합니다. 그러나 엄격 하 게 CLS 규격 코드 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않습니다. 이러한 구성 요소를 성공적으로 구성 요소와 상호 작용할 수 수 있습니다.  
  
 다음 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC40032  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   구성 요소가 다른만 상호 작용 하는 경우 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 구성 요소 또는 다른 모든 구성 요소와 인터페이스 하지, 아무 것도 변경할 필요가 없습니다.  
  
-   대해 작성 되지 않은 구성 요소와 조작 하는 경우는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], 결정, 리플렉션을 통해 수 있습니다 또는 문서에서 지원 하는지 여부이 데이터 형식입니다. 그렇지 않으면 아무 것도 변경할 필요가 없습니다.  
  
-   이 데이터 형식을 지원 하지 않는 구성 요소와 같이 하는 경우에 가장 가까운 CLS 규격 형식으로 대체 해야 있습니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소를 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [리플렉션(Visual Basic)](../../programming-guide/concepts/reflection.md)  
 [리플렉션](../../../framework/reflection-and-codedom/reflection.md)  
 

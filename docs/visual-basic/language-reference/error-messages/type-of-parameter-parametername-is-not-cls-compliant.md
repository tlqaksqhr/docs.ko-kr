---
title: 매개 변수 형식의 &#39; &lt;parametername&gt; &#39; CLS 규격이 아닙니다
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d34de9e5914b02a0e878b87e786b81a5940a6d85
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a>매개 변수 형식의 &#39; &lt;parametername&gt; &#39; CLS 규격이 아닙니다
프로시저로 표시 되어 `<CLSCompliant(True)>` 로 표시 된 형식으로 매개 변수를 선언 하지만 `<CLSCompliant(False)>`은 표시 되지 않았거나, 비규격 형식 이므로 사용할 수 없는 합니다.  
  
 프로시저가 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다. 이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.  
  
 다음 Visual Basic 데이터 형식 CLS 호환 되지 않습니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40028  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   프로시저 해야이 특정 형식의 매개 변수를 사용 하는 경우 제거 된 <xref:System.CLSCompliantAttribute>합니다. 프로시저는 CLS 규격일 수 없습니다.  
  
-   프로시저가 CLS 규격 이어야,이 매개 변수 형식을 가장 가까운 CLS 규격 형식 변경. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소에서 16 비트 정수를 수락 하는 경우로 선언 `Short` 대신 `Integer` 관리 되는 Visual Basic 코드에서.
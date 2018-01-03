---
title: "함수 &#39;의 반환 형식 &lt;procedurename&gt;&#39; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords: BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 866c0001d51a2eff75409c3918a6b6189ca294d8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>함수 &#39;의 반환 형식 &lt;procedurename&gt;&#39; CLS 규격이 아닙니다
A `Function` 절차로 표시 되어 `<CLSCompliant(True)>` 로 표시 된 형식을 반환 하지만 `<CLSCompliant(False)>`은 표시 되지 않았거나, 비규격 형식 이므로 사용할 수 없는 합니다.  
  
 프로시저가 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다. 이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.  
  
 다음 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40027  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   경우는 `Function` 프로시저 해야이 특정 형식 반환, 제거는 <xref:System.CLSCompliantAttribute>합니다. 프로시저는 CLS 규격일 수 없습니다.  
  
-   경우는 `Function` 프로시저 CLS 규격을 준수 해야, 가장 가까운 CLS 규격 형식으로 반환 형식을 변경 해야 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소에는 16 비트 정수를 반환 하는 경우로 선언 `Short` 대신 `Integer` 관리 되는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드입니다.
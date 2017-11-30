---
title: "XAML의 xml:space 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a5048cbad1d2ea914d041ac3c87a43223b208c3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xmlspace-handling-in-xaml"></a>XAML의 xml:space 처리
`xml:space` 특성은 object 요소 내에서 공백 처리 동작을 선언 하는 XML로 정의 된 특성입니다. 이 동작은 요소 내에 포함 된 모든 콘텐츠 (내부 텍스트)와 관련이 있는 `xml:space` 선언 되 고 범위 자식 요소를 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- 또는 -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>설명  
 에 대 한 정의 `xml:space` 가능한 두 값을 포함 하 여 XAML의 특성에서 파생 된 `xml:space` XML에 대 한 W3C 사양에 "특수 특성"으로 정의 된 대로 합니다.  
  
 기본값은 `xml:space` 특성은 리터럴 값 `"default"`합니다. 값에 대 한 `"default"`, if 또는 `xml:space` 항목에 정의 된 공백을 구문 분석의 동작은 기본 처리 전혀 표시 되지 않습니다 [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.  
  
 개체 요소 콘텐츠 내에서 공백을 유지 하기 위해 지정 `xml:space="preserve"` 개체 요소의 해당 합니다.  
  
 대부분의 해석 된 `xml:space` 특성 효과 및 특성의 값을 자식 요소 범위가 지정 됩니다.  
  
 XAML의 공백 처리에 대 한 자세한 내용은 참조 하십시오. [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [XAML 개요(WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)

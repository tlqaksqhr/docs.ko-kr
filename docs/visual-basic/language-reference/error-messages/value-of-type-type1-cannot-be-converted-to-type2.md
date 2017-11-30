---
title: "값 형식 &#39; type1 &#39; 변환할 수 없습니다 &#39; 유형 2 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords: BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>값 형식 &#39; type1 &#39; 변환할 수 없습니다 &#39; 유형 2 &#39;
'Type1' 형식의 값을 'type2'로 변환할 수 없습니다. 'Value' 속성을 사용 하 여 첫 번째 요소의 문자열 값을 가져올 '\<parentElement >'입니다.  
  
 XML 리터럴을 특정 형식으로 암시적으로 캐스팅하려고 했습니다. XML 리터럴은 지정된 형식으로 암시적으로 캐스팅할 수 없습니다.  
  
 **오류 ID:** BC31194  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   XML 리터럴의 `Value` 속성을 사용하여 해당 값을 `String`으로 참조합니다. `CType` 함수, 다른 형식 변환 함수 또는 <xref:System.Convert> 클래스를 사용하여 지정된 형식으로 값을 캐스팅합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Convert>  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)

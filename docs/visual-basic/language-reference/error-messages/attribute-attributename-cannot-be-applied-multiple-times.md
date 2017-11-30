---
title: "특성 &#39; &lt;attributename&gt;&#39; 여러 번 사용할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords: BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 216cf54fd164ca95b6378517a679b5b54183559f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>특성 &#39; &lt;attributename&gt;&#39; 여러 번 사용할 수 없습니다.
특성은 한 번만 적용할 수 있습니다. `AttributeUsage` 특성 특성을 두 번 이상 적용할 수 있는지 여부를 결정 합니다.  
  
 **오류 ID:** BC30663  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  특성은 한 번만 적용 해야 합니다.  
  
2.  개발한 사용자 지정 특성을 사용 하는 경우으로 바꾸어 보십시오 자신의 `AttributeUsage` 다음 예제와 같이 여러 특성 사용을 허용 하는 특성입니다.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.AttributeUsageAttribute>  
 [사용자 지정 특성 만들기](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)

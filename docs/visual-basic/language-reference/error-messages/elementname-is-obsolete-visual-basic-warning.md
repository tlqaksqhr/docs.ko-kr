---
title: "&quot;&lt;elementname&gt;&quot;은 (는) 사용 되지 않습니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
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
ms.openlocfilehash: ccec3b2659502c84dd4db9c9c4d796362958030b
ms.lasthandoff: 03/13/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>'&lt;elementname&gt;'은 (는) 사용 되지 않습니다.
문이 있는 것으로 표시 된 프로그래밍 요소에 액세스 하려고 시도 <xref:System.ObsoleteAttribute>특성 및 경고로 처리 하는 지시문.</xref:System.ObsoleteAttribute>  
  
 모든 프로그래밍 요소에 <xref:System.ObsoleteAttribute>합니다.</xref:System.ObsoleteAttribute> 적용 하 여 더 이상 사용 중인 것으로 표시할 수 없습니다. 이 작업을 수행 하는 경우에 특성을 설정할 수 있습니다 <xref:System.ObsoleteAttribute.IsError%2A>속성을 `True` 또는 `False`.</xref:System.ObsoleteAttribute.IsError%2A> `True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다. `False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.  
  
 기본적으로이 메시지는 경고, 때문에 <xref:System.ObsoleteAttribute.IsError%2A>속성 <xref:System.ObsoleteAttribute>는 `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A> 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC40008  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   소스 코드 참조에서 요소 이름의 철자가 맞는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)


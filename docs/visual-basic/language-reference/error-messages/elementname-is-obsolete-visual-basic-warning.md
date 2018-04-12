---
title: '&#39; &lt;elementname&gt;&#39;은 (는) 사용 되지 않습니다.'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bd6580da794255a3324021a284816ef9700beee7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>&#39; &lt;elementname&gt;&#39;은 (는) 사용 되지 않습니다.
문에서 경고로 처리하는 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시된 프로그래밍 요소에 액세스하려고 합니다.  
  
 프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다. 이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다. `True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다. `False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.  
  
 <xref:System.ObsoleteAttribute.IsError%2A> 의 <xref:System.ObsoleteAttribute> 속성이 `False`이므로 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC40008  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   소스 코드 참조에서 요소 이름의 철자가 맞는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)

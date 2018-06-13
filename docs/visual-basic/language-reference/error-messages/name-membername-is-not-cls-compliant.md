---
title: 이름 &lt;membername&gt; CLS 규격이 아닙니다
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 26ff13de461d5a96724868b7928129a326cdf1d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593344"
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>이름 &lt;membername&gt; CLS 규격이 아닙니다
로 어셈블리 표시 되어 `<CLSCompliant(True)>` 밑줄로 시작 하는 이름 가진 멤버를 노출 하지만 (`_`).  
  
 프로그래밍 요소를 준수 해야 하지만 하나 이상의 밑줄을 포함할 수 있습니다는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS) 시작 하지 않아야 밑줄로 합니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40031  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   소스 코드를 제어할 경우 밑줄로 시작 하지 않는 멤버 이름을 변경 합니다.  
  
-   멤버 이름은 변경 되지 않고 유지, 필요한 경우 제거 된 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다. 어셈블리도 표시할 수 있습니다 `<CLSCompliant(True)>`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  


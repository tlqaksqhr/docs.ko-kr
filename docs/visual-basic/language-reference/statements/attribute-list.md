---
title: 특성 목록(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 35d031722a5eddd6adce5e32df62b86c500d305b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604076"
---
# <a name="attribute-list-visual-basic"></a>특성 목록(Visual Basic)
선언된 된 프로그래밍 요소에 적용할 특성을 지정 합니다. 여러 특성은 쉼표로 구분합니다. 다음은 하나의 특성에 대 한 구문입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>요소  
 `attributemodifier`  
 소스 파일의 시작 부분에 적용 되는 특성에 필요 합니다. 수 [어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md) 또는 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md)합니다.  
  
 `attributename`  
 필수. 특성의 이름입니다.  
  
 `attributearguments`  
 선택 사항입니다. 이 특성에 대 한 위치 인수 목록입니다. 인수가 여러 개이면 쉼표로 구분 됩니다.  
  
 `attributeinitializer`  
 선택 사항입니다. 이 특성에 대 한 이니셜라이저를 변수 또는 속성의 목록입니다. 여러 이니셜라이저는 쉼표로 구분 합니다.  
  
## <a name="remarks"></a>설명  
 거의 모든 프로그래밍 요소 (형식, 프로시저, 속성, 등)에 하나 이상의 특성을 적용할 수 있습니다. 특성은 어셈블리의 메타 데이터에 나타날 있고 수 코드 주석을 추가 하거나 특정 프로그래밍 요소를 사용 하는 방법을 지정 합니다. Visual Basic 및.NET Framework에 정의 된 특성을 적용할 수 있으며 사용자 지정 특성을 정의할 수 있습니다.  

 특성을 사용 하는 시점에 대 한 자세한 내용은 참조 하십시오. [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다. 특성 이름에 대 한 자세한 내용은 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **배치 합니다.** 가장 선언 된 프로그래밍 요소와 특성을 적용할 수 있습니다. 하나 이상의 특성을 적용 하려면 배치는 *특성 블록* 요소 선언의 시작 부분에 있습니다. 특성 목록의 각 항목에에서는 한정자를 적용할 특성 및 특성의이 호출을 위해 사용 하는 인수를 지정 합니다.  
  
-   **꺾쇠 괄호입니다.** 특성 목록을 제공 하는 경우 묶어야 꺾쇠 괄호에서 ("`<`"및"`>`").  
  
-   **선언의 일부입니다.** 특성은 별도 문이 요소 선언의 속해야 합니다. 줄 연속 시퀀스를 사용할 수 있습니다 (" `_`") 여러 소스 코드 줄에 선언문을 확장할 수 있습니다.  
  
-   **한정자입니다.** 특성 한정자 (`Assembly` 또는 `Module`) 소스 파일의 시작 부분에 프로그래밍 요소에 적용 된 모든 특성에 필요 합니다. 소스 파일의 시작 부분에 없는 요소에 적용 된 특성에 특성 한정자를 사용할 수 없습니다.  
  
-   **인수입니다.** 모든 위치 인수는 특성에 대 한 모든 변수 또는 속성 이니셜라이저가 앞에 야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 적용는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성의 기본 정의에 `Function` 프로시저입니다.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성 사용된 하는 프로시저는 관리 되지 않는 동적 연결 라이브러리 (DLL)의 진입점을 나타낸다는 것을 의미 합니다. 특성에서 DLL 이름으로 위치 인수 및 변수 이니셜라이저로 기타 정보를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [모듈 \<키워드>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

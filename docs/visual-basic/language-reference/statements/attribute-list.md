---
title: "특성 목록 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e360794ad217784e2358967bfbcc03959cd043b1
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

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
 필수 요소. 특성의 이름입니다.  
  
 `attributearguments`  
 선택적 요소. 이 특성에 대 한 인수를 위치 인수 목록이 있습니다. 인수가 여러 개이면 쉼표로 구분 됩니다.  
  
 `attributeinitializer`  
 선택적 요소. 이 특성에 대 한 이니셜라이저를 변수 또는 속성의 목록입니다. 여러 이니셜라이저는 쉼표로 구분 됩니다.  
  
## <a name="remarks"></a>설명  
 거의 모든 프로그래밍 요소 (형식, 프로시저, 속성 및 등)에 하나 이상의 특성을 적용할 수 있습니다. 특성 어셈블리의 메타 데이터에 나타나며 사용자 코드 주석을 추가 하거나 특정 프로그래밍 요소를 사용 하는 방법을 지정 보시기 바랍니다. Visual Basic과.NET Framework에서 정의 된 특성을 적용할 수 및 사용자 지정 특성을 정의할 수 있습니다.  

 특성을 사용 하는 경우에 대 한 자세한 내용은 참조 하십시오. [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다. 특성 이름에 대 한 자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **배치 합니다.** 프로그래밍 요소와 가장 선언 된 특성을 적용할 수 있습니다. 하나 이상의 특성을 적용 하려면 배치는 *특성 블록* 요소 선언의 시작 부분에 있습니다. 특성 목록에 있는 각 항목 한정자를 적용 하려는 특성 및 특성의이 호출을 위해 사용 하는 인수를 지정 합니다.  
  
-   **꺾쇠 괄호입니다.** 특성 목록을 제공 하는 경우 묶어야 꺾쇠 괄호에서 ("`<`"및"`>`").  
  
-   **선언의 일부입니다.** 특성에는 별도 문이 아닌 요소 선언의 포함 되어야 합니다. 줄 연속 시퀀스를 사용할 수 있습니다 (" `_`") 여러 소스 코드 줄에 선언문을 확장할 수 있습니다.  
  
-   **한정자입니다.** 특성 한정자 (`Assembly` 또는 `Module`)는 소스 파일의 시작 부분에 있는 프로그래밍 요소에 적용 된 모든 특성에 필요 합니다. 한정자 특성은 소스 파일의 시작 부분에 포함 되지 않는 요소에 적용 된 특성에 허용 되지 않습니다.  
  
-   **인수입니다.** 모든 위치 인수는 특성에 대 한 모든 변수 또는 속성 이니셜라이저 앞에 야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 적용는 <xref:System.Runtime.InteropServices.DllImportAttribute>특성의 기본 정의에 `Function` 절차.</xref:System.Runtime.InteropServices.DllImportAttribute>  
  
 [!code-vb[VbVbalrStatements #&1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>특성 사용된 하는 절차는 관리 되지 않는 동적 연결 라이브러리 (DLL)의 진입점을 나타낸다는 것을 나타냅니다.</xref:System.Runtime.InteropServices.DllImportAttribute> 특성 위치 인수로 DLL 이름과 변수 이니셜라이저, 다른 정보를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [모듈 \<키워드 >](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)


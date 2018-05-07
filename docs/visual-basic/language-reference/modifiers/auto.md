---
title: Auto(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 414998b4bef526060e7ba4f584fa071fbd0acaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="auto-visual-basic"></a>Auto(Visual Basic)
Visual Basic 선언 되는 외부 프로시저의 외부 이름을 기반으로 하는.NET Framework 규칙에 따라 문자열을 마샬링하고 있는지를 지정 합니다.  
  
 프로젝트 외부에 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러는 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없는 경우 문자열 문자 집합 및이 정보에는 프로시저의 위치, 식별 되는 방법, 호출 시퀀스 및 반환 형식으로 포함 됩니다. [선언 문의](../../../visual-basic/language-reference/statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.  
  
 `charsetmodifier` 부분은 `Declare` 문은 외부 프로시저를 호출 하는 동안 문자열을 마샬링 한 문자 집합 정보를 제공 합니다. Visual Basic에서 외부 프로시저 이름에 대 한 외부 파일을 검색 하는 방법도 적용 됩니다. `Auto` 한정자는 Visual Basic.NET Framework 규칙에 따라 문자열을 마샬링할 하 고 기본 문자 및 런타임 플랫폼의 집합을 결정 하는 초기 검색 하는 경우 외부 프로시저 이름을 수정 해야 하도록 지정 오류가 발생합니다. 자세한 내용은의 "문자 집합" 참조 [선언 문의](../../../visual-basic/language-reference/statements/declare-statement.md)합니다.  
  
 문자 집합 자가 지정 된 경우 `Ansi` 값이 기본값입니다.  
  
## <a name="remarks"></a>설명  
 `Auto` 한정자는이 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>스마트 장치 개발자 노트  
 이 키워드는 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)

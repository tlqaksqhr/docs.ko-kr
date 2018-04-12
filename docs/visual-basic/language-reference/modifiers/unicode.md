---
title: Unicode(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 042908b8427de2de0de96bbb32df7be018bb915c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unicode-visual-basic"></a>Unicode(Visual Basic)
Visual Basic을 선언 되는 외부 프로시저의 이름에 관계 없이 유니코드 값으로 모든 문자열을 마샬링하고 있는지를 지정 합니다.  
  
 프로젝트 외부에 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러 올바르게 프로시저를 호출 하기 위해 필요한 정보에 액세스할 수 없는 경우 문자열 문자 집합 및이 정보에는 프로시저의 위치, 식별 되는 방법, 호출 시퀀스 및 반환 형식으로 포함 됩니다. [선언 문의](../../../visual-basic/language-reference/statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.  
  
 `charsetmodifier` 부분은 `Declare` 문은 외부 프로시저를 호출 하는 동안 문자열 마샬링을 문자 집합 정보를 제공 합니다. Visual Basic에서 외부 프로시저 이름에 대 한 외부 파일을 검색 하는 방법도 적용 됩니다. `Unicode` 한정자는 Visual Basic에서 모든 문자열을 유니코드 값으로 마샬링하고 이름을 검색 하는 동안 수정 하지 않고 프로시저를 조회 하도록 지정 합니다.  
  
 문자 집합 자가 지정 된 경우 `Ansi` 값이 기본값입니다.  
  
## <a name="remarks"></a>설명  
 `Unicode` 한정자는이 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>스마트 장치 개발자 노트  
 이 키워드는 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [자동](../../../visual-basic/language-reference/modifiers/auto.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)

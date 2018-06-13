---
title: 오류 없이 계속됩니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 5e45f713a433365b4bbc8286154a3b877b08ec59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597877"
---
# <a name="resume-without-error"></a>오류 없이 계속됩니다.
A `Resume` 문의 오류 처리 코드 외부에 있거나 오류가 있습니다. 경우에 오류 처리기로 코드 점프 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  이동의 `Resume` 오류 처리기로 문의 하거나, 삭제 합니다.  
  
2.  프로시저에 대 한 오류 처리기를 식별 하는 레이블 검색 레이블로 이동할 때 프로시저를 통해 발생할 수 없습니다. 대상으로 지정 된 중복 레이블과 경우는 `GoTo` 문이 아닌는 `On Error GoTo` 문, 원하는 대상에 대 한 동의를 줄 레이블을 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Resume 문](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)

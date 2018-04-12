---
title: 오류 없이 계속됩니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a>오류 없이 계속됩니다.
A `Resume` 문의 오류 처리 코드 외부에 있거나 오류가 있습니다. 경우에 오류 처리기로 코드 점프 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  이동의 `Resume` 오류 처리기로 문의 하거나, 삭제 합니다.  
  
2.  프로시저에 대 한 오류 처리기를 식별 하는 레이블 검색 레이블로 이동할 때 프로시저를 통해 발생할 수 없습니다. 대상으로 지정 된 중복 레이블과 경우는 `GoTo` 문이 아닌는 `On Error GoTo` 문, 원하는 대상에 대 한 동의를 줄 레이블을 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Resume 문](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)

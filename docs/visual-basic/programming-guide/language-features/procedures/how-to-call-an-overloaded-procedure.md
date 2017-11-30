---
title: "방법: 오버로드된 프로시저 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff5967c1b09ad59f249297b1cf0a4ed900faf4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>방법: 오버로드된 프로시저 호출(Visual Basic)
프로시저 오버 로드의 장점은 호출의 유연성에서입니다. 호출 코드 프로시저에 전달 하 고 전달 하는 인수에 관계 없이 하나의 프로시저 이름을 호출 하는 데 필요한 정보를 얻을 수 있습니다.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>정의 된 버전이 둘 이상 있는 프로시저를 호출 하려면  
  
1.  호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.  
  
2.  인수 목록에 데이터를 제공 하 여 정상적인 방식에서 프로시저 호출을 작성 합니다. 인수는 프로시저에 정의 된 버전 중 하나에 매개 변수 목록과 일치 해야 합니다.  
  
3.  호출할 프로시저의 버전을 결정 필요가 없습니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]인수 목록과 일치 하는 버전으로 제어가 전달 됩니다.  
  
     다음 예제에서는 `post` 에 선언 된 프로시저 [하는 방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)합니다. 고객 id를 받아 인지 확인 한 `String` 또는 `Integer`, 한 다음 두 경우 모두 같은 프로시저를 호출 합니다.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [프로시저 문제 해결](./troubleshooting-procedures.md)  
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)  
 [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)  
 [오버로드 확인](./overload-resolution.md)  
 [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)

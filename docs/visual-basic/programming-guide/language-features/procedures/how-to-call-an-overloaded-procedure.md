---
title: "방법: 오버 로드 된 프로시저 (Visual Basic)를 호출 합니다. | Microsoft 문서"
ms.custom: 
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
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 0da83aa63bf013d841f2a01a535726f3b03497a1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>방법: 오버로드된 프로시저 호출(Visual Basic)
프로시저 오버 로드의 장점은 호출의 유연성에서입니다. 호출 코드에서 프로시저에 전달 하는 하나의 프로시저 이름을 전달 하는 인수에 관계 없이 다음 호출 하는 데 필요한 정보를 얻을 수 있습니다.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>둘 이상의 버전이 정의 된 프로시저를 호출 하려면  
  
1.  호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.  
  
2.  인수 목록에서 데이터를 표시 합니다. 일반적인 방법으로 프로시저 호출을 작성 합니다. 인수에는 프로시저에 대해 정의 된 버전 중 하나에 매개 변수 목록과 일치 해야 합니다.  
  
3.  호출할 프로시저의 버전을 확인 하 고 필요가 없습니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]인수 목록과 일치 하는 버전으로 제어가 전달 됩니다.  
  
     다음 예제에서는 `post` 프로시저에서 선언 [하는 방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)합니다. 고객 id를 받아 인지 확인 한 `String` 또는 `Integer`, 다음 두 경우 모두 같은 프로시저를 호출 합니다.  
  
     [!code-vb[VbVbcnProcedures #&56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures #&57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [프로시저 오버 로드](./procedure-overloading.md)   
 [문제 해결 절차](./troubleshooting-procedures.md)   
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)   
 [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)   
 [오버 로드 확인](./overload-resolution.md)   
 [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)

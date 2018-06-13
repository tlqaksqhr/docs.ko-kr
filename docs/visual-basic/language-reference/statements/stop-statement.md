---
title: Stop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599137"
---
# <a name="stop-statement-visual-basic"></a>Stop 문(Visual Basic)
실행을 일시 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Stop  
```  
  
## <a name="remarks"></a>설명  
 배치할 수 `Stop` 실행이 일시 중단 하는 절차에는 문입니다. 사용 하 여 `Stop` 문이 코드에 중단점을 설정 하는 것과 비슷합니다.  
  
 `Stop` 문을 달리 하지만 실행을 일시 중단 `End`, 파일을 모두 닫고 하거나 컴파일된 실행 파일 (.exe) 파일에서 발생 하지 않는 모든 변수를 선택 취소 하지 않습니다.  
  
> [!NOTE]
>  경우는 `Stop` (IDE) 통합된 개발 환경 외부에서 실행 되는 코드에서 문이 실행 될, 디버거가 호출 됩니다. 이 일반 정품 또는 디버그 모드에서 컴파일된 코드 여부에 관계 없이 적용 합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `Stop` 문을 통해 반복 실행을 일시 중지는 `For...Next` 루프입니다.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [End 문](../../../visual-basic/language-reference/statements/end-statement.md)

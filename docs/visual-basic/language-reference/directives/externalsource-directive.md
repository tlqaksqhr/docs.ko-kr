---
title: '#ExternalSource 지시문'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 146ab41d74b45acc4063e2463baca26c7caa4652
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="externalsource-directive"></a>#ExternalSource 지시문
소스 코드의 특정 줄과 소스 외부에 있는 텍스트 간의 매핑을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>요소  
 `StringLiteral`  
 외부 원본에 대 한 경로입니다.  
  
 `IntLiteral`  
 외부 소스의 첫 번째 줄의 줄 번호입니다.  
  
 `LogicalLine`  
 외부 소스에서 오류가 발생 하는 선입니다.  
  
 `#End ExternalSource`  
 `#ExternalSource` 블록을 종료합니다.  
  
## <a name="remarks"></a>설명  
 이 지시문은 컴파일러와 디버거에 의해서만 사용 됩니다.  
  
 소스 파일을 소스 파일에 코드의 특정 줄과.aspx 파일과 같이 소스 외부에 텍스트 간의 매핑을 나타내는 외부 원본 지시문이 포함 될 수 있습니다. 지정된 된 소스 코드에서 컴파일하는 동안 오류가 발생 하면 외부 원본에서 오는 것으로 식별 됩니다.  
  
 외부 소스 지시문 컴파일에 영향을 주 및 중첩 될 수 없습니다. 응용 프로그램에서 내부 사용에 대 한 것은.  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

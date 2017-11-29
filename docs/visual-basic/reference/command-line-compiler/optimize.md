---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a>/optimize
컴파일러 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. `/optimize-` 컴파일러 최적화 옵션을 해제 합니다. `/optimize+` 옵션 최적화할 수 있습니다. 최적화는 기본적으로 사용되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 컴파일러 최적화 작고, 빠르며, 더 효율적인 출력 파일을 확인합니다. 그러나 최적화로 인해 출력 파일에서 코드가 다시 정렬 되기 때문에, `/optimize+` 디버깅이 어려워질 수 있습니다.  
  
 생성 된 모든 모듈 `/target:module` 동일한 어셈블리를 사용 해야 `/optimize` 어셈블리로 설정 합니다. 자세한 내용은 참조 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다.  
  
 결합할 수는 `/optimize` 및 `/debug` 옵션입니다.  
  
|Visual Studio 통합된 개발 환경에서 최적화 / 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.<br />     자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  수정 된 **최적화를 활성화** 확인란 합니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 하 고 컴파일러 최적화를 활성화 합니다.  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)

---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8da27ea2f9f0a4d370928d70cda1a796b822d97c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nowarn"></a>/nowarn
컴파일러에서 경고를 생성하지 않도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`numberList`|선택 사항입니다. 쉼표로 구분 된 목록 컴파일러 표시 되지 않아야 하는 경고 ID 번호입니다. 경고 Id를 지정 하지 않은 모든 경고가 표시 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 `/nowarn` 옵션을 사용 하면 경고가 생성 되지 않습니다. 개별 경고를 표시 하지 않으려면 경고 ID를 제공는 `/nowarn` 콜론 뒤 옵션입니다. 여러 경고 번호를 쉼표로 구분 합니다.  
  
 경고 식별자의 숫자 부분만 지정 해야 합니다. BC42024, 사용 하지 않는 지역 변수에 대 한 경고를 표시 하지 않으려는 경우 지정 하는 예를 들어 `/nowarn:42024`합니다.  
  
 경고 ID 번호에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
|Visual Studio에서 /nowarn을 설정 하려면 통합 개발 환경|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  선택 된 **모든 경고를 해제** 확인란 모든 경고를 비활성화 합니다.<br />     또는<br />     특정 경고를 사용 하지 않으려면 **None** 경고 옆의 드롭다운 목록에서 합니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 모든 경고를 표시 하지 않습니다.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 를 사용 하지 않는 지역 변수 (42024)에 대 한 경고를 표시 하지 않습니다.  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)

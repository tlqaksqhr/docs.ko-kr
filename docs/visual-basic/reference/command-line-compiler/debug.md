---
title: "/debug (Visual Basic) | Microsoft 문서"
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
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 7384e69f066022e861a4277f418df3f4d094c3be
ms.lasthandoff: 03/13/2017

---
# <a name="debug-visual-basic"></a>/debug(Visual Basic)
컴파일러가 디버깅 정보를 생성 하 여 출력 파일에 배치 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택적 요소. 지정 `+` 또는 `/debug` 컴파일러가 디버깅 정보를 생성 하는.pdb 파일에 저장 합니다. 지정 `-` 지정 하지 않는 것과 동일한 결과가 `/debug`합니다.|  
|`full` &#124; `pdbonly`|선택적 요소. 컴파일러에서 생성되는 디버깅 정보 형식을 지정합니다. 지정 하지 않으면 `/debug:pdbonly`, 기본값은 `full`, 실행 중인 프로그램에 디버거를 연결할 수 있습니다. `pdbonly` 인수를 사용 하면 디버거에서 프로그램을 시작 하지만 실행 중인 프로그램을 디버거에 연결 된 경우에 어셈블리 언어 코드를 표시 하는 경우 소스 코드에서 디버깅 합니다.|  
  
## <a name="remarks"></a>설명  
 디버그 빌드를 만들려면이 옵션을 사용 합니다. 지정 하지 않으면 `/debug`, `/debug+`, 또는 `/debug:full`, 프로그램의 출력 파일을 디버깅할 수 없습니다.  
  
 기본적으로 디버깅 정보는 내보내지지 않습니다 (`/debug-`). 디버깅 정보로 내보냅니다 지정 `/debug` 또는 `/debug+`합니다.  
  
 응용 프로그램의 디버그 성능을 구성하는 방법에 대한 자세한 내용은 [쉽게 디버깅할 수 있도록 이미지 만들기](http://msdn.microsoft.com/library/7d90ea7a-150f-4f97-98a7-f9c26541b9a3)를 참조하세요.  
  
|Visual Studio에서 /debug을 설정 하려면 통합 개발 환경|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  클릭 하 고 **컴파일** 탭 합니다.<br />3.  클릭 **고급 컴파일 옵션**합니다.<br />4.  값을 수정 된 **디버그 정보 생성** 상자입니다.|  
  
## <a name="example"></a>예제  
 출력 파일에 디버깅 정보를 저장 하는 다음 예제에서는 `App.exe`합니다.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

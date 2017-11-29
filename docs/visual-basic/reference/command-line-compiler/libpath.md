---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2be2c460fddf2e8ea4fe1239ec073f208c072d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="libpath"></a>/libpath
참조 된 어셈블리의 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`dirList`|필수 요소. 세미콜론으로 구분 된 컴파일러가 참조 된 어셈블리에서에서 찾는 대 한 디렉터리의 없는 목록에서 현재 작업 디렉터리 (컴파일러를 호출 하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리입니다. 디렉터리 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").|  
  
## <a name="remarks"></a>설명  
 `/libpath` 에서 참조 어셈블리의 위치를 지정 하는 옵션은 [/참조](../../../visual-basic/reference/command-line-compiler/reference.md) 옵션입니다.  
  
 컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.  
  
1.  현재 작업 디렉터리입니다. 컴파일러가 호출되는 디렉터리입니다.  
  
2.  공용 언어 런타임 시스템 디렉터리입니다.  
  
3.  지정 된 경로 `/libpath`합니다.  
  
4.  LIB 환경 변수로 지정된 디렉터리입니다.  
  
 `/libpath` 옵션은 가산적; 지정 하 여 모든 이전 값에 추가 하는 한 번 이상 것입니다.  
  
 사용 하 여 `/reference` 어셈블리 참조를 지정할 수 있습니다.  
  
|Visual Studio에서 /libpath를 설정 하려면 통합 개발 환경|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  **참조** 탭을 클릭합니다.<br />3.  클릭는 **참조 경로 중...**  단추입니다.<br />4.  에 **참조 경로** 대화 상자에서 디렉터리 이름을 입력 합니다는 **폴더:** 상자입니다.<br />5.  클릭 **폴더 추가**합니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` .exe 파일을 만듭니다. 컴파일러는 어셈블리 참조에 대 한 작업 디렉터리, c: 드라이브의 루트 디렉터리 및 c: 드라이브의 새 어셈블리 디렉터리를 찾습니다.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

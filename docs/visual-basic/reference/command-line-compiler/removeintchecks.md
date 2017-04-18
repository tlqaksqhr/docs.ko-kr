---
title: "/removeintchecks | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 8e50200b8755ccc6b1c173024856955f5075b67e
ms.lasthandoff: 03/13/2017

---
# <a name="removeintchecks"></a>/removeintchecks
오버플로 오류 또는 해제 하는 정수 연산에 대 한 검사를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택적 요소. `/removeintchecks-` 옵션을 사용 하면 모든 정수 연산 오버플로 오류를 확인 합니다. 기본값은 `/removeintchecks-`입니다.<br /><br /> 지정 `/removeintchecks` 또는 `/removeintchecks+` 오류 검사를 차단 하 고 정수 계산을 더욱 빠르게 만들 수 있습니다. 그러나 오류 검사 없이 및 잘못 된 결과 데이터 형식 용량을 오버플로 하는 경우 오류를 일으키지 않고 저장 될 수 있습니다.|  
  
|Visual Studio에서 /removeintchecks를 설정 하려면 통합 개발 환경|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  클릭 하 고 **컴파일** 탭 합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  값을 수정 된 **정수 오버플로 검사 해제** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Test.vb` 정수 오버플로 오류 검사를 끕니다.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

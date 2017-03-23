---
title: "/out (Visual Basic) | Microsoft 문서"
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
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
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
ms.openlocfilehash: e3eb7af88869e4fb161a12914c02f2bc2f41864e
ms.lasthandoff: 03/13/2017

---
# <a name="out-visual-basic"></a>/out(Visual Basic)
출력 파일의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. 컴파일러 생성 하는 출력 파일의 이름입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").|  
  
## <a name="remarks"></a>주의  
 전체 이름 및 만들 파일의 확장명을 지정 합니다. .Exe 파일은 포함 하는 소스 코드 파일에서 이름을 사용 하지 않으면는 `Sub Main` 프로시저 및.dll 파일의 첫 번째 소스 코드 파일에서 이름을 가져옵니다.  
  
 .Exe 또는.dll 확장명 없이 파일 이름을 지정 하면 컴파일러가 자동으로 확장을 추가 대해 지정 된 값에 따라는 `/target` 컴파일러 옵션입니다.  
  
|Visual Studio 통합된 개발 환경에서 /out 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  값을 수정 된 **어셈블리 이름** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 출력 파일을 만들고 `T2.exe`합니다.  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

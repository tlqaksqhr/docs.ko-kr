---
title: "/warnaserror (Visual Basic) | Microsoft 문서"
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
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
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
ms.openlocfilehash: 28f232b1ad8200455550f2f4c1204818c8b143ab
ms.lasthandoff: 03/13/2017

---
# <a name="warnaserror-visual-basic"></a>/warnaserror(Visual Basic)
컴파일러에서 맨 처음 발견 되는 경고를 오류로 처리 하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|+ &#124; -|선택적 요소. 기본적으로 `/warnaserror-` 는 사실; 경고 되지 않더라도 컴파일러에서 출력 파일을 생성 합니다. `/warnaserror` 동일한 옵션으로 `/warnaserror+`, 경고가 오류로 처리 되도록 하 합니다.|  
|`numberList`|선택적 요소. 경고 ID의 쉼표로 구분 된 목록에 있는 번호는 `/warnaserror` 옵션은 적용 됩니다. 경고 ID를 지정 하는 경우는 `/warnaserror` 옵션은 모든 경고에 적용 됩니다.|  
  
## <a name="remarks"></a>설명  
 `/warnaserror` 옵션 모든 경고를 오류로 처리 합니다. 일반적으로 보고 되는 대로 경고 대신 오류로 보고 되는 모든 메시지입니다. 컴파일러는 이후에 나오는 동일한 경고를 경고로 보고합니다.  
  
 기본적으로 `/warnaserror-` 만 정보 제공 용으로 경고를 일으키는 적용 합니다. `/warnaserror` 동일한 옵션으로 `/warnaserror+`, 경고가 오류로 처리 되도록 하 합니다.  
  
 특정 경고만 오류로 처리를 하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분 된 목록을 지정할 수 있습니다.  
  
> [!NOTE]
>  `/warnaserror` 옵션에 경고가 표시 되는 방식을 제어 하지 않습니다. 사용 된 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 경고를 비활성화 하는 옵션입니다.  
  
|/Warnaserror 모든 경고를 Visual Studio IDE에서 오류로 처리 하도록 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  클릭 하 고 **컴파일** 탭 합니다.<br />3.  있는지는 **모든 경고를 해제** 확인란이 선택 되지 않습니다.<br />4.  확인 된 **모든 경고를 오류로 처리** 확인란입니다.|  
  
|/Warnaserror 특정 경고 Visual Studio IDE에서 오류를 처리 하도록 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.<br />2.  클릭 하 고 **컴파일** 탭 합니다.<br />3.  있는지는 **모든 경고를 해제** 확인란이 선택 되지 않습니다.<br />4.  있는지는 **모든 경고를 오류로 처리** 확인란이 선택 되지 않습니다.<br />5.  선택 **오류** 에서 **알림** 옆에 경고를 오류로 처리 해야 하는 열입니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 를 처음 발견 된 모든 경고에 대 한 오류를 표시 하도록 컴파일러에 지시 합니다.  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 만 사용 하지 않는 지역 변수 (42024)에 대 한 경고를 오류로 취급 하 고 있습니다.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)

---
title: "/nowarn | Microsoft 문서"
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
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
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
ms.openlocfilehash: 61b145a9eb95f5357c7aa2983a96c31e8f2cef6a
ms.lasthandoff: 03/13/2017

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
|`numberList`|선택적 요소. 쉼표로 구분 된 목록 컴파일러를 표시 하지 않아야 하는 경고 ID 번호입니다. 경고 Id를 지정 하지 않은 모든 경고가 표시 되지 않습니다.|  
  
## <a name="remarks"></a>주의  
 `/nowarn` 옵션을 사용 하면 경고가 생성 되지 않습니다. 개별 경고를 표시 하지 않으려면 경고 ID를 제공 된 `/nowarn` 콜론 뒤 옵션입니다. 여러 경고 번호를 쉼표로 구분 합니다.  
  
 경고 식별자의 숫자 부분만 지정 해야 합니다. B c&42024;를 사용 하지 않는 지역 변수에 대 한 경고를 표시 하지 않으려는 경우 지정 하는 예를 들어 `/nowarn:42024`합니다.  
  
 경고 ID 번호에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
|Visual Studio에서 /nowarn을 설정 하려면 통합 개발 환경|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  클릭 하 고 **컴파일** 탭 합니다.<br />3.  선택은 **모든 경고를 해제** 확인란 모든 경고를 비활성화 합니다.<br />     또는<br />     특정 경고를 비활성화 하려면 클릭 **None** 경고 옆의 드롭다운 목록에서.|  
  
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
 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)

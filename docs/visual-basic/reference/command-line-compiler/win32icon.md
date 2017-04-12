---
title: "/win32icon | Microsoft 문서"
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
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
ms.openlocfilehash: 110a3861d6628dc2c3fb251aaa31762fb94f04c9
ms.lasthandoff: 03/13/2017

---
# <a name="win32icon"></a>/win32icon
.Ico 파일을 출력 파일에 삽입합니다. 이.ico 파일에 출력 파일을 나타냅니다 **파일 탐색기**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|출력 파일에 추가 하려면.ico 파일입니다. 파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.|  
  
## <a name="remarks"></a>주의  
 Microsoft Windows 리소스 컴파일러 (RC)으로.ico 파일을 만들 수 있습니다. 리소스 컴파일러를 호출 하는 Visual c + + 프로그램을 컴파일하는 경우 .ico 파일.rc 파일에서 만들어집니다. `/win32icon` 및 `/win32resource` 옵션은 함께 사용할 수 없습니다.  
  
 참조 [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 참조에는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일 또는 [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 연결 하는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일입니다. 참조 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .res 파일을 가져옵니다.  
  
|Visual Studio IDE에서 /win32icon을 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  값을 수정 된 **아이콘** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` .ico 파일을 연결 하 고 `Rf.ico`합니다.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

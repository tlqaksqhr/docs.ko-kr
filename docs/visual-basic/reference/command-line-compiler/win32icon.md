---
title: "/win32icon | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "win32icon compiler option [Visual Basic]"
  - "-win32icon compiler option [Visual Basic]"
  - "/win32icon compiler option [Visual Basic]"
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /win32icon
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

.ico 파일을 출력 파일에 삽입합니다.  출력 파일에.ico 파일을 나타내는  **파일 탐색기**.  
  
## 구문  
  
```  
/win32icon:filename  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`filename`|출력 파일에 추가할 .ico 파일입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.|  
  
## 설명  
 Microsoft Windows RC\(리소스 컴파일러\)를 사용하여 .ico 파일을 만들 수 있습니다.  리소스 컴파일러는 Visual C\+\+ 프로그램을 컴파일할 때 호출되며 .rc 파일에서 .ico 파일이 만들어집니다.  `/win32icon` 옵션과 `/win32resource` 옵션은 함께 사용할 수 없습니다.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 리소스 파일을 참조하려면 [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)를 참조하고, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 리소스 파일을 연결하려면 [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)를 참조하십시오.  .res 파일을 가져오려면 [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)를 참조하십시오.  
  
||  
|-|  
|Visual Studio IDE에서 \/win32icon을 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  **아이콘** 상자의 값을 수정합니다.|  
  
## 예제  
 다음 코드에서는 `In.vb`를 컴파일하고 .ico 파일 `Rf.ico`를 연결합니다.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
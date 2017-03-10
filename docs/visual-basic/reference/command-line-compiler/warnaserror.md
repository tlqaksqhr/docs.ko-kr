---
title: "/warnaserror (Visual Basic) | Microsoft Docs"
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
  - "warnaserror compiler option [Visual Basic]"
  - "/warnaserror compiler option [Visual Basic]"
  - "-warnaserror compiler option [Visual Basic]"
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /warnaserror (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러가 처음으로 나타나는 경고를 오류로 처리하도록 합니다.  
  
## 구문  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|\+ &#124; \-|선택적 요소.  `/warnaserror-`가 기본값으로 사용되며, 경고가 발생해도 컴파일러가 출력 파일을 생성합니다.  `/warnaserror` 옵션은 `/warnaserror+`와 같으며 경고가 오류로 처리되도록 합니다.|  
|`numberList`|선택적 요소.  `/warnaserror` 옵션이 적용되는 경고 ID 번호를 쉼표로 구분한 목록입니다.  경고 ID를 지정하지 않으면 `/warnaserror` 옵션이 모든 경고에 적용됩니다.|  
  
## 설명  
 `/warnaserror` 옵션을 사용하면 모든 경고가 오류로 처리됩니다.  보통 경고로 보고되는 메시지가 대신 오류로 보고됩니다.  같은 경고가 계속해서 발생하면 컴파일러에서 경고로 보고합니다.  
  
 경고를 알림으로 전환하는 `/warnaserror-`가 기본값으로 사용됩니다.  `/warnaserror` 옵션은 `/warnaserror+`와 같으며 경고가 오류로 처리되도록 합니다.  
  
 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호를 쉼표로 구분하여 지정할 수도 있습니다.  
  
> [!NOTE]
>  `/warnaserror` 옵션은 경고를 표시하는 방법에 영향을 주지 않습니다.  경고를 사용하지 않으려면 [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 옵션을 사용합니다.  
  
||  
|-|  
|Visual Studio IDE에서 모든 경고를 오류로 처리하도록 \/warnaserror를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **모든 경고 사용 안 함** 확인란을 선택하지 않았는지 확인합니다.<br />4.  **모든 경고를 오류로 처리** 확인란을 선택합니다.|  
  
||  
|-|  
|Visual Studio IDE에서 특정 경고를 오류로 처리하도록 \/warnaserror를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **모든 경고 사용 안 함** 확인란을 선택하지 않았는지 확인합니다.<br />4.  **모든 경고를 오류로 처리** 확인란을 선택하지 않았는지 확인합니다.<br />5.  오류로 처리해야 할 경고 옆의 **알림** 열에서 **오류**를 선택합니다.|  
  
## 예제  
 다음 코드에서는 `In.vb`를 컴파일하고, 컴파일러에서 경고가 처음 발생할 때마다 오류 메시지를 표시하도록 지시합니다.  
  
```  
vbc /warnaserror in.vb  
```  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하고, 사용하지 않는 지역 변수에 대한 경고\(42024\)만 오류로 처리합니다.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)
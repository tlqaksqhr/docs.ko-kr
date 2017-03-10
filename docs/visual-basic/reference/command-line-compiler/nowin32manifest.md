---
title: "/nowin32manifest (Visual Basic) | Microsoft Docs"
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
  - "/nowin32manifest compiler option [Visual Basic]"
  - "nowin32manifest compiler option [Visual Basic]"
  - "-nowin32manifest compiler option [Visual Basic]"
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# /nowin32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

응용 프로그램 매니페스트를 실행 파일에 포함하지 않도록 컴파일러에 지시합니다.  
  
## 구문  
  
```  
/nowin32manifest  
```  
  
## 설명  
 이 옵션을 사용할 때 Win32 리소스 파일이나 이후 빌드 단계에서 응용 프로그램 매니페스트를 제공하지 않으면 응용 프로그램이 Windows Vista에서 가상화됩니다.  가상화에 대한 자세한 내용은 [Windows Vista의 ClickOnce 배포](/visual-studio/deployment/clickonce-deployment-on-windows-vista)를 참조하십시오.  
  
 매니페스트 생성에 대한 자세한 내용은 [\/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)를 참조하십시오.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)
---
title: "/langversion (Visual Basic) | Microsoft Docs"
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
  - "/langversion compiler option [Visual Basic]"
  - "langversion compiler option [Visual Basic]"
  - "-langversion compiler option [Visual Basic]"
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# /langversion (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러에서 지정된 Visual Basic 언어 버전에 포함된 구문만 허용하도록 합니다.  
  
## 구문  
  
```  
/langversion:version  
```  
  
## 인수  
 `version`  
 필수 요소.  컴파일 중에 사용할 언어 버전입니다.  사용 가능한 값은 `9`, `9.0`, `10` 및 `10.0`입니다.  
  
## 설명  
 `/langversion` 옵션을 사용하여 컴파일러에 허용되는 구문을 지정할 수 있습니다.  예를 들어, 언어 버전을 9.0으로 지정하는 경우 컴파일러에서 버전 10.0 이상에서만 유효한 구문이라는 오류가 생성됩니다.  
  
 다른 .NET Framework 버전을 대상으로 하는 응용 프로그램을 개발할 때 이 옵션을 사용할 수 있습니다.  예를 들어 .NET Framework 3.5를 대상으로 하는 경우 언어 버전 10.0의 구문을 사용하지 않도록 하기 위해 이 옵션을 사용할 수 있습니다.  
  
 `/langversion`은 명령줄에서만 직접 설정할 수 있습니다.  자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visual-studio/ide/targeting-a-specific-dotnet-framework-version)을 참조하십시오.  
  
## 예제  
 다음 코드에서는 Visual Basic 9.0의 `sample.vb`를 컴파일합니다.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [특정 대상 .NET Framework 버전 지정](/visual-studio/ide/targeting-a-specific-dotnet-framework-version)
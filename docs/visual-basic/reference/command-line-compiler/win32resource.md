---
title: "/win32resource | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/win32resource"
  - "win32resource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32resource compiler option [Visual Basic]"
  - "-win32resource compiler option [Visual Basic]"
  - "win32resource compiler option [Visual Basic]"
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /win32resource
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Win32 리소스 파일을 출력 파일에 삽입합니다.  
  
## 구문  
  
```  
/win32resource:filename  
```  
  
## 인수  
 `filename`  
 출력 파일에 추가할 리소스 파일의 이름입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.  
  
## 설명  
 Microsoft Windows RC\(리소스 컴파일러\)를 사용하여 Win32 리소스 파일을 만들 수 있습니다.  
  
 버전 Win32 리소스를 포함 하거나 수 있는 비트맵 \(아이콘\) 정보 확인 응용 프로그램에서  **파일 탐색기**.  `/win32resource`를 지정하지 않으면 컴파일러는 어셈블리 버전을 기반으로 버전 정보를 생성합니다.  `/win32resource` 옵션과 `/win32icon` 옵션은 함께 사용할 수 없습니다.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 리소스 파일을 참조하려면 [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)를 참조하고, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 리소스 파일을 연결하려면 [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)를 참조하십시오.  
  
> [!NOTE]
>  `/win32resource` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드는 `In.vb`를 컴파일하고 Win32 리소스 파일 `Rf.res`를 연결합니다.  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
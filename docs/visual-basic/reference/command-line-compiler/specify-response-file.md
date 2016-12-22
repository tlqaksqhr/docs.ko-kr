---
title: "@ (Specify Response File) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "@ (Specify Response File) compiler option [Visual Basic]"
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# @ (Specify Response File) (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컴파일러 옵션과 컴파일할 소스 코드 파일을 포함하는 파일을 지정합니다.  
  
## 구문  
  
```  
@response_file  
```  
  
## 인수  
 `response_file`  
 필수 요소.  컴파일러 옵션이나 컴파일할 소스 코드 파일 목록이 들어 있는 파일입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.  
  
## 설명  
 컴파일러는 지시 파일에 지정된 컴파일러 옵션과 소스 코드 파일을 명령줄에 지정된 것처럼 처리합니다.  
  
 컴파일할 때 지시 파일을 두 개 이상 지정하려면 다음과 같이 지시 파일 옵션을 여러 개 지정합니다.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 지시 파일에 여러 컴파일러 옵션과 소스 코드 파일을 한 줄로 나타낼 수 있습니다.  하나의 컴파일러 옵션 지정은 여러 줄로 나타낼 수 없으며 반드시 한 줄로 지정해야 합니다.  지시 파일에는 `#` 기호로 시작하는 주석을 포함할 수 있습니다.  
  
 명령줄에 지정된 옵션과 하나 이상의 지시 파일에 지정된 옵션을 결합할 수 있습니다.  컴파일러는 명령 옵션을 발견하면 처리합니다.  따라서 명령줄 인수로 지시 파일에 있는 이전의 옵션 목록을 재정의할 수 있습니다.  반대로 지시 파일에 있는 옵션으로 명령줄이나 다른 지시 파일에 있는 이전의 옵션 목록을 재정의할 수 있습니다.  
  
 Visual Basic에서는 Vbc.rsp 파일을 제공합니다. 이 파일은 Vbc.exe 파일과 같은 디렉터리에 있습니다.  `/noconfig` 옵션을 사용하지 않으면 Vbc.rsp 파일은 기본적으로 포함됩니다.  자세한 내용은 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)를 참조하십시오.  
  
> [!NOTE]
>  `@` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음은 샘플 지시 파일의 일부입니다.  
  
```  
# build the first output file  
/target:exe   
/out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## 예제  
 다음 예제에서는 `File1.rsp`라는 이름의 지시 파일과 함께 `@` 옵션을 사용하는 방법을 보여 줍니다.  
  
```  
vbc @file1.rsp  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
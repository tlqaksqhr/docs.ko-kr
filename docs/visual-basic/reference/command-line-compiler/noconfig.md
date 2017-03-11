---
title: "/noconfig | Microsoft Docs"
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
  - "noconfig compiler option [Visual Basic]"
  - "-noconfig compiler option [Visual Basic]"
  - "/noconfig compiler option [Visual Basic]"
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /noconfig
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러가 일반적으로 사용되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 어셈블리를 자동으로 참조하거나 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져오지 않도록 지정합니다.  
  
## 구문  
  
```  
/noconfig  
```  
  
## 설명  
 `/noconfig` 옵션을 사용하면 컴파일러에서 Vbc.exe 파일과 같은 디렉터리에 있는 Vbc.rsp 파일을 사용하여 컴파일하지 않습니다.  Vbc.rsp 파일은 일반적으로 사용되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 어셈블리를 참조하고 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져옵니다.  `/nostdlib` 옵션이 지정되지 않으면 컴파일러는 System.dll 어셈블리를 암시적으로 참조합니다.  `/nostdlib` 옵션을 사용하면 컴파일러에서 Vbc.rsp를 사용하여 컴파일하거나 자동으로 System.dll 어셈블리를 참조하지 않습니다.  
  
> [!NOTE]
>  Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조됩니다.  
  
 모든 Vbc.exe 컴파일마다\(`/noconfig` 옵션을 지정하는 경우는 제외\) 포함되어야 할 추가 컴파일러 옵션을 지정하도록 Vbc.rsp 파일을 수정할 수 있습니다.  자세한 내용은 [@ \(Specify Response File\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)를 참조하십시오.  
  
 컴파일러에서는 `vbc` 명령에 전달된 옵션을 마지막으로 처리합니다.  따라서 명령줄에서 지정한 옵션은 Vbc.rsp 파일에 있는 같은 옵션의 설정을 재정의합니다.  
  
> [!NOTE]
>  `/noconfig` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 참고 항목  
 [\/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ \(Specify Response File\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)
---
title: "/codepage (Visual Basic) | Microsoft Docs"
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
  - "/codepage compiler option [Visual Basic]"
  - "codepage compiler option [Visual Basic]"
  - "-codepage compiler option [Visual Basic]"
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /codepage (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.  
  
## 구문  
  
```  
/codepage:id  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`id`|필수 요소.  컴파일러에서는 `id`로 지정된 코드 페이지를 사용하여 소스 파일의 인코딩을 해석합니다.|  
  
## 설명  
 특정 인코딩으로 저장된 소스 코드를 컴파일하려면 `/codepage`를 사용하여 사용할 코드 페이지를 지정합니다.  `/codepage` 옵션은 컴파일에 사용되는 모든 소스 코드 파일에 적용됩니다.  자세한 내용은 [.NET Framework의 문자 인코딩](../Topic/Character%20Encoding%20in%20the%20.NET%20Framework.md)을 참조하십시오.  
  
 소스 코드 파일이 현재 ANSI 코드 페이지, 유니코드 또는 서명이 포함된 UTF\-8을 사용하여 저장된 경우 `/codepage` 옵션이 필요 없습니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서는 사용자가 **인코딩** 대화 상자에서 다른 인코딩을 지정하지 않는 경우 모든 소스 코드 파일을 기본적으로 현재 ANSI 코드 페이지로 저장합니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서는 다른 코드 페이지로 저장된 소스 코드 파일을 열 때 **인코딩** 대화 상자를 사용합니다.  
  
> [!NOTE]
>  `/codepage` 옵션은 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)
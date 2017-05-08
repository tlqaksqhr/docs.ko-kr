---
title: "Interop 프로젝트 컴파일 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, 컴파일"
  - "COM interop, COM 구성 요소 게시"
  - "interop 프로젝트 컴파일"
  - ".NET Framework에 COM 구성 요소 게시"
  - "비관리 코드와의 상호 운용, 컴파일"
  - "비관리 코드와의 상호 운용, COM 구성 요소 게시"
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Interop 프로젝트 컴파일
가져온 COM 형식이 포함된 어셈블리를 하나 이상 참조하는 COM interop 프로젝트는 다른 모든 관리되는 프로젝트와 마찬가지로 컴파일됩니다.  interop 어셈블리는 Visual Studio 같은 개발 환경에서 참조하거나 명령줄 컴파일러를 사용할 때 참조할 수 있습니다.  둘 중 어느 방법을 사용하든지, interop 어셈블리가 다른 모든 프로젝트 파일과 동일한 디렉터리에 위치해야 컴파일 작업이 제대로 수행됩니다.  
  
 Interop 어셈블리는 두 가지 방법으로 참조할 수 있습니다.  
  
-   포함된 interop 형식. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]와 [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] 및 이후 버전에서는 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다.  이것이 권장되는 방법입니다.  
  
-   interop 어셈블리 배포. interop 어셈블리에 대한 표준 참조를 만들 수 있습니다.  이 경우 interop 어셈블리가 응용 프로그램과 함께 배포되어야 합니다.  
  
 이러한 두 방법 간의 차이점은 [Using COM Types in Managed Code](http://msdn.microsoft.com/ko-kr/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)에서 보다 자세히 설명합니다.  
  
 Visual Studio를 사용하여 interop 형식을 포함하는 방법은 [연습: Microsoft Office 어셈블리의 형식 정보 포함](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) 및 [연습: 관리되는 어셈블리의 형식 포함](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)에서 확인할 수 있습니다.  
  
 interop 어셈블리를 명령줄 컴파일러에서 참조하고 형식 정보를 실행 파일에 포함하려면 [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md) 또는 [\/link](../Topic/-link%20\(Visual%20Basic\).md) 컴파일러 스위치를 사용하고 interop 어셈블리 이름을 지정합니다.  
  
> [!NOTE]
>  Visual C\+\+ 응용 프로그램은 형식 정보를 포함하지 못하지만 형식 정보를 포함하는 응용 프로그램 또는 추가 기능과 상호 작용할 수는 있습니다.  
  
 배포될 때 주 interop 어셈블리를 포함하는 응용 프로그램을 컴파일하려면 **\/reference** 컴파일러 스위치를 사용하고 interop 어셈블리 이름을 지정합니다.  
  
## 참고 항목  
 [.NET Framework에 COM 구성 요소 노출](../../../docs/framework/interop/exposing-com-components.md)   
 [언어 독립성 및 언어 독립적 구성 요소](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ko-kr/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [연습: Microsoft Office 어셈블리의 형식 정보 포함](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: 관리되는 어셈블리의 형식 포함](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [형식 라이브러리를 어셈블리로 가져오기](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
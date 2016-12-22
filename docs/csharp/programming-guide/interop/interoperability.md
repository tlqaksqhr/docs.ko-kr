---
title: "상호 운용성(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 상호 운용성"
  - "COM interop"
  - "상호 운용성"
  - "플랫폼 호출, C#을 사용하여 API 액세스"
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 상호 운용성(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

상호 운용성을 활용하면 기존의 비관리 코드를 유지하고 활용할 수 있습니다.  CLR\(공용 언어 런타임\)의 제어 하에 실행되는 코드를 *관리 코드*라고 하며 CLR 외부에서 실행되는 코드를 *비관리 코드*라고 합니다.  비관리 코드의 예로는 COM, COM\+, C\+\+ 구성 요소, ActiveX 구성 요소 및 Microsoft Win32 API가 있습니다.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]에서는 플랫폼 호출 서비스, <xref:System.Runtime.InteropServices> 네임스페이스, C\+\+ 상호 운용성 및 COM 상호 운용성\(COM interop\)을 통해 비관리 코드와의 상호 운용성을 제공합니다.  
  
## 단원 내용  
 [상호 운용성 개요](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 C\# 관리 코드와 비관리 코드 간의 상호 운영에 사용되는 메서드를 설명합니다.  
  
 [방법: Visual C\# 기능을 사용하여 Office Interop 개체에 액세스](../Topic/How%20to:%20Access%20Office%20Interop%20Objects%20by%20Using%20Visual%20C%23%20Features%20\(C%23%20Programming%20Guide\).md)  
 Office 프로그래밍을 쉽게 수행하기 위해 Visual C\# 2010에 도입된 기능을 설명합니다.  
  
 [방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 매개 변수가 있는 COM 속성에 액세스하기 위해 인덱싱된 속성을 사용하는 방법을 설명합니다.  
  
 [방법: 플랫폼 호출을 사용하여 웨이브 파일 재생](../Topic/How%20to:%20Use%20Platform%20Invoke%20to%20Play%20a%20Wave%20File%20\(C%23%20Programming%20Guide\).md)  
 플랫폼 호출 서비스를 사용하여 Windows 운영 체제에서 .wav 사운드 파일을 재생하는 방법을 설명합니다.  
  
 [연습: Office 프로그래밍](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 Excel 통합 문서 및 통합 문서에 대 한 링크를 포함 하는 Word 문서를 만드는 방법을 보여 줍니다.  
  
 [COM 클래스 예제](../../../csharp/programming-guide/interop/example-com-class.md)  
 C\# 클래스를 COM 개체로 노출하는 방법을 보여 줍니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [연습: Office 프로그래밍](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
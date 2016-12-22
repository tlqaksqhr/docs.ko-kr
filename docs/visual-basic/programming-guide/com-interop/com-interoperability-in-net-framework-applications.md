---
title: "COM Interoperability in .NET Framework Applications (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "interoperability, COM and .NET framework objects"
  - "COM interop"
  - "shared components"
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# COM Interoperability in .NET Framework Applications (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

COM 개체와 .NET Framework 개체를 동일한 응용 프로그램에서 사용하려면 이들 개체가 메모리에 존재하는 방식에서 생기는 차이점을 처리해야 합니다.  .NET Framework 개체는 관리되는 메모리, 즉 공용 언어 런타임에서 제어하는 메모리에 있으며 필요에 따라 이 런타임에 의해 이동될 수도 있습니다.  COM 개체는 관리되지 않는 메모리에 있으며 다른 메모리 위치로 이동될 수 없습니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]와 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]에는 이러한 관리되는 구성 요소와 관리되지 않는 구성 요소의 상호 작용을 제어하는 도구가 있습니다.  관리 코드에 대한 자세한 내용은 [공용 언어 런타임](../Topic/Common%20Language%20Runtime%20\(CLR\).md)을 참조하십시오.  
  
 .NET 응용 프로그램에서 COM 개체를 사용하는 것 외에도 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]을 사용하여 COM을 통해 비관리 코드에서 액세스할 수 있는 개체를 개발해야 할 수도 있습니다.  
  
 이 페이지에 있는 링크는 COM 개체와 .NET Framework 개체 간 상호 작용에 대한 자세한 내용을 보여 줍니다.  
  
## 관련 단원  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 COM 개체, ActiveX 컨트롤, Win32 DLL, 관리되는 개체 및 COM 개체 상속을 비롯하여 Visual Basic에서의 COM 상호 운용성에 대해 설명하는 항목으로 이동하는 링크를 제공합니다.  
  
 [COM Interop Wrapper Error](/visual-cpp/misc/com-interop-wrapper-error)  
 프로젝트 시스템에서 특정 구성 요소에 대한 COM 상호 운용성 래퍼를 만들 수 없는 경우에 발생하는 결과와 선택할 수 있는 옵션에 대해 설명합니다.  
  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)  
 관리 코드와 비관리 코드 간의 몇 가지 상호 작용 문제에 대해 간단하게 설명하고 추가 정보를 볼 수 있는 링크를 제공합니다.  
  
 [COM 래퍼](../Topic/COM%20Wrappers.md)  
 관리 코드에서 COM 메서드를 호출할 수 있는 런타임 호출 가능 래퍼와 COM 클라이언트에서 .NET 개체 메서드를 호출할 수 있는 COM 호출 가능 래퍼에 대해 설명합니다.  
  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ko-kr/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 래퍼, 예외, 상속, 스레딩, 이벤트, 변환 및 마샬링과 관련된 COM 상호 운용성에 대해 설명하는 항목으로 이동하는 링크를 제공합니다.  
  
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)  
 COM 형식 라이브러리에 있는 형식 정의를 공용 언어 런타임 어셈블리에 있는 동일한 기능의 정의로 변환하는 데 사용할 수 있는 도구에 대해 설명합니다.
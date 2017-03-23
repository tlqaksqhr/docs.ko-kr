---
title: ".NET Framework 응용 프로그램 (Visual Basic)의 COM 상호 운용성 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 308ee8e495efa9368ef55d781f6b6dc314db51ac
ms.lasthandoff: 03/13/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>.NET Framework 응용 프로그램의 COM 상호 운용성(Visual Basic)
동일한 응용 프로그램에서 COM 개체 및.NET Framework 개체를 사용 하려는 경우는 개체가 메모리에 존재 하는 방법의 차이 해결 해야 합니다. .NET Framework 개체가 관리 되는 메모리에 있는-공용 언어 런타임에 의해 제어 하는 메모리-필요에 따라 런타임에 의해 이동 될 수도 있습니다. COM 개체는 관리 되지 않는 메모리에 있으며 다른 메모리 위치로 이동 하는 클래스가 아닙니다. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]고 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 이러한 상호 작용을 제어 하는 도구를 코드와 비관리 구성 요소를 제공 합니다. 관리 되는 코드에 대 한 자세한 내용은 참조 [공용 언어 런타임](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482)합니다.  
  
 .NET 응용 프로그램에서 COM 개체를 사용 하는 것 외에도 할 수 있습니다 사용 하 여 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] COM. 통해 비관리 코드에서 액세스할 수 있는 개체를 개발 하려면  
  
 이 페이지에 있는 링크 COM 및.NET Framework 개체 간의 상호 작용에 자세히 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 Visual basic에서 COM 개체, ActiveX 컨트롤, Win32 Dll, 관리 되는 개체 및 COM 개체의 상속을 포함 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.  
  
 [COM Interop 래퍼 오류](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 프로젝트 시스템에서 특정 구성 요소에 대 한 COM 상호 운용성 래퍼를 만들 수 없는 경우에 결과 및 옵션을 설명 합니다.  
  
 [비관리 코드와의 상호 운용](https://msdn.microsoft.com/library/sd10k43k)  
 간략하게 몇 가지 관리 및 비관리 코드 간의 상호 작용 문제를 설명 하 고 추가 정보에 대 한 링크를 제공 합니다.  
  
 [COM 래퍼](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 COM 메서드를 호출 하는 관리 되는 코드를 허용 하는 런타임 호출 가능 래퍼 및 COM 클라이언트에서.NET 개체 메서드를 호출할 수 있도록 하는 COM 호출 가능 래퍼에 설명 합니다.  
  
 [고급 COM 상호 운용성](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 래퍼, 예외, 상속, 스레딩, 이벤트, 변환 및 마샬링 관련 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.  
  
 [Tlbimp.exe (형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 COM 형식 라이브러리에 있는 형식 정의 공용 언어 런타임 어셈블리의 동등한 정의로 변환 하는 데 사용할 수 도구에 설명 합니다.

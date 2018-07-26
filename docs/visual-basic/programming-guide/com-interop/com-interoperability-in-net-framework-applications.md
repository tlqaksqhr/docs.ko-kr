---
title: .NET Framework 응용 프로그램의 COM 상호 운용성(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244666"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>.NET Framework 응용 프로그램의 COM 상호 운용성(Visual Basic)
동일한 응용 프로그램에서 COM 개체 및.NET Framework 개체를 사용 하려는 경우에 개체가 메모리에 존재 하는 방법의 차이 해결 해야 합니다. .NET Framework 개체를 관리 되는 메모리에 위치한-공용 언어 런타임에 의해 제어 하는 메모리-필요에 따라 런타임에 의해 이동 될 수도 있습니다. COM 개체는 관리 되지 않는 메모리에 있으며 다른 메모리 위치로 이동 되지 않습니다. Visual Studio 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 이러한 상호 작용을 제어 하는 도구 관리 코드와 비관리 구성 요소를 제공 합니다. 관리 코드에 대 한 자세한 내용은 참조 하세요. [공용 언어 런타임](../../../standard/clr.md)합니다.  
  
 .NET 응용 프로그램에서 COM 개체를 사용 하는 것 외에도 수도 있습니다 Visual Basic COM. 통해 비관리 코드에서 액세스할 수 있는 개체를 개발 하는 데  
  
 이 페이지의 링크 COM 및.NET Framework 개체 간의 상호 작용에 자세히 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 Visual basic에서 COM 개체, ActiveX 컨트롤, Win32 Dll, 관리 되는 개체 및 COM 개체의 상속을 포함 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.  
  
 [COM Interop 래퍼 오류](/cpp/misc/com-interop-wrapper-error)  
 프로젝트 시스템에서 특정 구성 요소에 대 한 COM 상호 운용성 래퍼를 만들 수 없는 경우 결과 및 옵션을 설명 합니다.  
  
 [비관리 코드와의 상호 운용](../../../framework/interop/index.md)  
 간단 하 게 관리 및 비관리 코드 간의 상호 작용 문제 중 일부를 설명 하 고 추가 연구에 대 한 링크를 제공 합니다.  
  
 [COM 래퍼](../../../framework/interop/com-wrappers.md)  
 COM 메서드를 호출 하는 관리 되는 코드를 허용 하는 런타임 호출 가능 래퍼 및 COM 클라이언트가.NET 개체 메서드를 호출 하도록 허용 하는 COM 호출 가능 래퍼에 설명 합니다.  
  
 [고급 COM 상호 운용성](../../../framework/interop/index.md)  
 래퍼, 예외, 상속, 스레딩, 이벤트, 변환 및 마샬링 관련 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.  
  
 [Tlbimp.exe(형식 라이브러리 가져오기)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 COM 형식 라이브러리에 있는 형식 정의 공용 언어 런타임 어셈블리의 동등한 정의로 변환 하 여 도구를 설명 합니다.

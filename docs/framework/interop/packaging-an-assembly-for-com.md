---
title: "COM에서 사용할 어셈블리의 패키징"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 73866ddc1e8199dfad188179dc668bc31ab3c93d
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="packaging-an-assembly-for-com"></a>COM에서 사용할 어셈블리의 패키징
COM 개발자는 응용 프로그램에 통합하려는 관리 형식에 대한 다음 정보를 활용할 수 있습니다.  
  
-   COM 응용 프로그램에서 사용할 수 있는 형식의 목록  
  
     일부 관리 형식은 COM에 표시되지 않습니다. 일부는 표시되지만 만들 수 없고, 일부는 표시되지도 않고 작성할 수도 없습니다. 어셈블리는 표시되지 않은 형식, 표시되는 형식, 만들 수 없는 형식 및 만들 수 있는 형식의 조합으로 구성됩니다. 완성도를 위해 COM에 공개하려는 어셈블리에서 형식을 식별합니다. 해당 형식이 .NET Framework에 공개된 형식의 하위 집합인 경우 특히 해당됩니다.  
  
     자세한 내용은 [상호 운용할 .NET 형식의 정규화](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)를 참조하세요.  
  
-   버전 관리 지침  
  
     클래스 인터페이스(COM interop 생성 인터페이스)를 구현하는 관리 클래스에는 버전 관리 제한 사항이 적용됩니다.  
  
     클래스 인터페이스를 사용하는 데 대한 지침은 [클래스 인터페이스 소개](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)를 참조하세요.  
  
-   배포 지침  
  
     게시자가 서명한 강력한 이름의 어셈블리는 전역 어셈블리 캐시에 설치할 수 있습니다. 서명되지 않은 어셈블리는 사용자 컴퓨터에 전용 어셈블리로 설치해야 합니다.  
  
     자세한 내용은 [어셈블리 보안 고려 사항](../../../docs/framework/app-domains/assembly-security-considerations.md)을 참조하세요.  
  
-   형식 라이브러리 포함  
  
     COM 응용 프로그램에서 사용할 때 대부분의 형식에는 형식 라이브러리가 필요합니다. 사용자가 형식 라이브러리를 생성하거나 COM 개발자가 이 작업을 수행할 수 있습니다. [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 형식 라이브러리를 생성하기 위해 다음 옵션을 제공합니다.  
  
    -   [형식 라이브러리 내보내기](#cpconpackagingassemblyforcomanchor1)  
  
    -   [TypeLibConverter 클래스](#cpconpackagingassemblyforcomanchor2)  
  
    -   [어셈블리 등록 도구](#cpconpackagingassemblyforcomanchor3)  
  
    -   [.NET 서비스 설치 도구](#cpconpackagingassemblyforcomanchor4)  
  
     선택하는 메커니즘에 관계없이 사용자가 제공하는 어셈블리에 정의된 공용 형식만 생성된 형식 라이브러리에 포함됩니다.  
  
     형식 라이브러리를 개별 파일로 패키지하거나 .NET 기반 응용 프로그램에서 Win32 리소스 파일로 포함할 수 있습니다. Microsoft Visual Basic 6.0에서는 이 작업을 자동으로 수행합니다. 그러나 [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)]를 사용하는 경우 형식 라이브러리를 직접 포함시켜야 합니다. 자세한 내용은 [방법: .NET 응용 프로그램에 Win32 리소스로 형식 라이브러리 포함](http://msdn.microsoft.com/en-us/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)을 참조하세요.  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## <a name="type-library-exporter"></a>형식 라이브러리 내보내기  
 [형식 라이브러리 내보내기(Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)는 어셈블리에 포함된 클래스와 인터페이스를 COM 형식 라이브러리로 변환하는 명령줄 도구입니다. 클래스의 형식 정보를 사용할 수 있으면 COM 클라이언트가 .NET 클래스의 인스턴스를 만들고 COM 개체인 것처럼 인스턴스의 메서드를 호출할 수 있습니다. Tlbexp.exe는 한 번에 전체 어셈블리를 변환합니다. Tlbexp.exe를 사용하여 어셈블리에 정의된 형식의 하위 집합에 대한 형식 정보를 생성할 수는 없습니다.  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## <a name="typelibconverter-class"></a>TypeLibConverter 클래스  
 **System.Runtime.Interop** 네임스페이스에 있는 <xref:System.Runtime.InteropServices.TypeLibConverter> 클래스는 어셈블리에 포함된 클래스와 인터페이스를 COM 형식 라이브러리로 변환합니다. 이 API는 이전 섹션에 설명된 형식 라이브러리 내보내기와 동일한 형식 정보를 생성합니다.  
  
 **TypeLibConverter 클래스**는 <xref:System.Runtime.InteropServices.ITypeLibConverter>를 구현합니다.  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## <a name="assembly-registration-tool"></a>어셈블리 등록 도구  
 [어셈블리 등록 도구(Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)를 사용하면 **/tlb:** 옵션을 적용할 때 형식 라이브러리를 생성하고 등록할 수 있습니다. COM 클라이언트를 사용하려면 형식 라이브러리가 Windows 레지스트리에 설치되어 있어야 합니다. 이 옵션이 없으면 Regasm.exe는 형식 라이브러리가 아니라 어셈블리에 형식만 등록합니다. 어셈블리에 형식을 등록하고 형식 라이브러리를 등록하는 것은 별개의 작업입니다.  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## <a name="net-services-installation-tool"></a>.NET 서비스 설치 도구  
 [.NET 서비스 설치 도구(Regsvcs.exe)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)는 Windows 2000 구성 요소 서비스를 관리 클래스에 추가하고 여러 작업을 단일 도구에 결합합니다. 어셈블리를 로드하고 등록하는 외에도 Regsvcs.exe는 형식 라이브러리를 생성하고 등록하며 기존 COM+ 1.0 응용 프로그램에 설치할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 <xref:System.Runtime.InteropServices.ITypeLibConverter>   
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [상호 운용할 .NET 형식의 정규화](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [클래스 인터페이스 소개](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [어셈블리 보안 고려 사항](../../../docs/framework/app-domains/assembly-security-considerations.md)   
 [Tlbexp.exe(형식 라이브러리 내보내기)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)   
 [COM에 어셈블리 등록](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [방법: 응용 프로그램에 Win32 리소스로 형식 라이브러리 포함](http://msdn.microsoft.com/en-us/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)


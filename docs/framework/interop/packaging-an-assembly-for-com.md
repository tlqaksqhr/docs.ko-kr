---
title: "COM에서 사용할 어셈블리의 패키징 | Microsoft Docs"
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
  - ".NET 서비스 설치 도구"
  - "어셈블리 등록 도구"
  - "COM interop, COM 구성 요소 게시"
  - "COM interop, 어셈블리 패키징"
  - ".NET Framework 구성 요소를 COM에 노출"
  - "비관리 코드와의 상호 운용, .NET Framework 구성 요소 게시"
  - "비관리 코드와의 상호 운용, 어셈블리 패키징"
  - "COM의 어셈블리 패키징"
  - "Reqasm.exe"
  - "Reqsvcs.exe"
  - "Tlbexp.exe"
  - "형식 라이브러리 내보내기"
  - "TypeLibConverter 클래스"
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# COM에서 사용할 어셈블리의 패키징
다음은 COM 개발자가 참조할 수 있는 내용으로서, 응용 프로그램에 통합하려는 관리되는 형식에 대한 유용한 정보를 제공합니다.  
  
-   COM 응용 프로그램에 사용할 수 있는 형식 목록  
  
     관리되는 형식은 COM에 표시되지 않는 형식, COM에는 표시되지만 COM에서 만들 수 없는 형식, COM에 표시되고 동시에 만들 수 있는 형식 등, 다양하며  어셈블리는 표시되지 않는 형식, 표시되는 형식, 만들 수 없는 형식 및 만들 수 있는 형식 등의 가능한 모든 조합으로 구성됩니다.  따라서, 응용 프로그램에 통합할 관리되는 형식을 확실하게 선택하기 위해서는 어셈블리에서 COM에 노출하려는 형식을 식별해야 하며, 이 절차는 해당 형식이 .NET Framework에 노출된 형식의 하위 집합인 경우에는 특히 중요합니다.  
  
     자세한 내용은 [상호 운용할 .NET 형식의 정규화](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)를 참조하십시오.  
  
-   버전 관리 지침  
  
     클래스 인터페이스\(COM interop에서 생성된 인터페이스\)를 구현하는 관리되는 클래스는 버전 관리 제한의 영향을 받습니다.  
  
     클래스 인터페이스 사용에 대한 지침은 [클래스 인터페이스 소개](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)를 참조하십시오.  
  
-   배포 지침  
  
     강력한 이름 및 게시자가 서명한 어셈블리는 전역 어셈블리 캐시에 설치될 수 있지만  서명되지 않은 어셈블리는 사용자의 컴퓨터에 전용 어셈블리로 설치되어야 합니다.  
  
     자세한 내용은 [어셈블리 보안 고려 사항](../../../docs/framework/app-domains/assembly-security-considerations.md)을 참조하십시오.  
  
-   형식 라이브러리 포함 여부  
  
     COM 응용 프로그램에서 형식을 사용할 때는 형식 라이브러리가 일반적으로 필요하므로  사용자는 형식 라이브러리를 직접 생성하거나 COM 개발자가 이 작업을 수행하도록 할 수 있습니다.  [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 형식 라이브러리를 생성하는 데 필요한 다음과 같을 옵션을 제공합니다.  
  
    -   [형식 라이브러리 내보내기](#cpconpackagingassemblyforcomanchor1)  
  
    -   [TypeLibConverter 클래스](#cpconpackagingassemblyforcomanchor2)  
  
    -   [어셈블리 등록 도구](#cpconpackagingassemblyforcomanchor3)  
  
    -   [.NET 서비스 설치 도구](#cpconpackagingassemblyforcomanchor4)  
  
     이 중에서 선택하는 메커니즘에 상관 없이, 생성되는 형식 라이브러리에는 어셈블리에 정의된 공용 형식만 포함됩니다.  
  
     형식 라이브러리는 별도의 파일로 패키징하거나 .NET 기반 응용 프로그램 내에 Win32 리소스 파일로 포함시킬 수 있습니다.  Microsoft Visual Basic 6.0에서는 이 작업이 자동으로 수행되었지만, [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)]를 사용할 때는 사용자가 직접 형식 라이브러리를 포함시켜야 합니다.  자세한 내용은 [방법: .NET 기반 응용 프로그램에 Win32 리소스로 형식 라이브러리 포함](http://msdn.microsoft.com/ko-kr/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)을 참조하십시오.  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## 형식 라이브러리 내보내기  
 [형식 라이브러리 내보내기\(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)는 어셈블리에 포함된 클래스 및 인터페이스를 COM 형식 라이브러리로 변환하는 명령줄 도구입니다.  클래스의 형식 정보를 사용할 수 있으면, COM 클라이언트에서는 COM 개체에 대해서와 마찬가지로 .NET 클래스의 인스턴스를 만들고 해당 인스턴스에 대해 메서드를 호출할 수 있습니다.  Tlbexp.exe는 어셈블리 전체를 한 번에 변환합니다.  Tlbexp.exe를 사용하여 어셈블리에 정의된 형식의 하위 집합에 대한 형식 정보를 생성할 수는 없습니다.  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## TypeLibConverter 클래스  
 **System.Runtime.Interop** 네임스페이스에 있는 <xref:System.Runtime.InteropServices.TypeLibConverter> 클래스는 어셈블리에 포함된 클래스와 인터페이스를 COM 형식 라이브러리로 변환합니다.  이 API는 이전 단원에 설명된 형식 라이브러리 내보내기와 동일한 형식 정보를 만듭니다.  
  
 **TypeLibConverter class**는 [ITypeLibConverter 인터페이스](frlrfSystemRuntimeInteropServicesITypeLibConverterClassTopic)를 구현합니다.  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## 어셈블리 등록 도구  
 [어셈블리 등록 도구\(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)에서 **\/tlb:** 옵션을 사용하면 형식 라이브러리가 생성되고 등록됩니다.  COM 클라이언트에서는 형식 라이브러리가 Windows 레지스트리에 설치되어야 하는데  이 옵션을 사용하지 않으면 Regasm.exe에서 형식 라이브러리를 등록하지 않고 어셈블리의 형식만 등록합니다.  어셈블리의 형식을 등록하는 것과 형식 라이브러리를 등록하는 것은 서로 다른 작업입니다.  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## .NET 서비스 설치 도구  
 [.NET 서비스 설치 도구\(Regsvcs.exe\)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)는 관리되는 클래스를 Windows 2000 구성 요소 서비스에 추가하며 여러 작업을 하나의 도구에 결합시킵니다.  Regsvs.exe는 어셈블리를 로드하고 등록하는 것 이외에도 형식 라이브러리를 기존 COM\+ 1.0 응용 프로그램에 생성, 등록 및 설치합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 <xref:System.Runtime.InteropServices.ITypeLibConverter>   
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [상호 운용할 .NET 형식의 정규화](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/ko-kr/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [어셈블리 보안 고려 사항](../../../docs/framework/app-domains/assembly-security-considerations.md)   
 [Tlbexp.exe\(형식 라이브러리 내보내기\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)   
 [COM에 어셈블리 등록](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [How to: Embed Type Libraries as Win32 Resources in Applications](http://msdn.microsoft.com/ko-kr/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)
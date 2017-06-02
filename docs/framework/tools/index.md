---
title: ".NET Framework 도구 | Microsoft Docs"
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
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
caps.latest.revision: 65
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: baaf365a21661b377f8151e5d97ac16542aa2c36
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="net-framework-tools"></a>.NET Framework 도구
.NET Framework 도구를 사용하면 .NET Framework를 대상으로 하는 응용 프로그램 및 구성 요소를 보다 쉽게 만들고 배포하고 관리할 수 있습니다.  
  
 이 단원에서 설명하는 대부분의 .NET Framework 도구는 Visual Studio와 함께 자동으로 설치됩니다. 설치에 대한 자세한 내용은 [Visual Studio 다운로드](http://go.microsoft.com/fwlink/?LinkID=325532)를 참조하세요.  
  
 어셈블리 캐시 뷰어(Shfusion.dll)를 제외한 모든 도구는 명령줄에서 실행할 수 있습니다. Shfusion.dll에 액세스하려면 파일 탐색기를 사용해야 합니다.  
  
 명령줄 도구를 실행하는 가장 좋은 방법은 Visual Studio의 개발자 명령 프롬프트를 사용하는 것입니다. 이러한 유틸리티를 사용하면 설치 폴더로 이동하지 않아도 도구를 쉽게 실행할 수 있습니다. 자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.  
  
> [!NOTE]
>  일부 도구는 32비트 컴퓨터 또는 64비트 컴퓨터 전용입니다. 컴퓨터에 적절한 버전의 도구를 실행하세요.  
  
## <a name="in-this-section"></a>단원 내용  
 [Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 모듈 또는 리소스 파일로부터 어셈블리 매니페스트가 있는 파일을 생성합니다.  
  
 [Aximp.exe(Windows Forms ActiveX 컨트롤 가져오기)](../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)  
 ActiveX 컨트롤용 COM 형식 라이브러리의 형식 정의를 Windows Forms 컨트롤로 변환합니다.  
  
 [Caspol.exe(코드 액세스 보안 정책 도구)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)  
 컴퓨터 정책 수준, 사용자 정책 수준 및 엔터프라이즈 정책 수준의 보안 정책을 보고 구성할 수 있도록 합니다. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이상 버전에서 [\<legacyCasPolicy> 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)를 `true`로 설정하지 않으면 이 도구는 CAS(코드 액세스 보안) 정책에 영향을 주지 않습니다. 자세한 내용은 [보안 변경 내용](../../../docs/framework/security/security-changes.md)을 참조하세요.  
  
 [Cert2spc.exe(SPC 테스트 도구)](../../../docs/framework/tools/cert2spc-exe-software-publisher-certificate-test-tool.md)  
 하나 이상의 X.509 인증서에서 SPC(소프트웨어 게시 인증서)를 만듭니다. 이 도구는 테스트 전용입니다.  
  
 [Certmgr.exe(인증서 관리자 도구)](../../../docs/framework/tools/certmgr-exe-certificate-manager-tool.md)  
 인증서, CTL(인증서 신뢰 목록) 및 CRL(인증서 해지 목록)을 관리합니다.  
  
 [Clrver.exe(CLR 버전 도구)](../../../docs/framework/tools/clrver-exe-clr-version-tool.md)  
 컴퓨터에서 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.  
  
 [CorFlags.exe(CorFlags 변환 도구)](../../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md)  
 PE(이식 가능한 실행) 이미지 헤더의 CorFlags 섹션을 구성할 수 있도록 합니다.  
  
 [Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)  
 .NET Framework에서 런타임에 어셈블리를 찾지 못하는 이유를 진단하는 데 도움이 되는 어셈블리 바인딩에 대한 정보를 표시합니다.  
  
 [Gacutil.exe(전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 전역 어셈블리 캐시와 다운로드 캐시의 내용을 보거나 조작할 수 있도록 합니다.  
  
 [Ilasm.exe(IL 어셈블러)](../../../docs/framework/tools/ilasm-exe-il-assembler.md)  
 IL(Intermediate Language)로 PE(이식 가능한 실행) 파일을 생성합니다. 이렇게 생성된 실행 파일을 실행하여 IL이 예상대로 실행되는지 여부를 확인할 수 있습니다.  
  
 [Ildasm.exe(IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)  
 IL(Intermediate Language) 코드가 들어 있는 PE(이식 가능한 실행) 파일을 사용하여 IL 어셈블러(Ilasm.exe)에 입력할 수 있는 텍스트 파일을 만듭니다.  
  
 [Installutil.exe(설치 관리자 도구)](../../../docs/framework/tools/installutil-exe-installer-tool.md)  
 특정 어셈블리에서 설치 관리자 구성 요소를 실행하는 방법으로 서버 리소스를 설치하고 제거할 수 있도록 합니다. <xref:System.Configuration.Install> 네임스페이스의 클래스에서 작동합니다. 특정 어셈블리에서 설치 관리자 구성 요소를 실행하는 방법으로 서버 리소스를 설치하고 제거할 수 있도록 합니다. <xref:System.Configuration.Install> 네임스페이스의 클래스에서 작동합니다.  
  
 [Lc.exe(라이선스 컴파일러)](../../../docs/framework/tools/lc-exe-license-compiler.md)  
 라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함할 수 있는 .licenses 파일을 생성합니다. 라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함할 수 있는 .licenses 파일을 생성합니다.  
  
 [Mage.exe(매니페스트 생성 및 편집 도구)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 응용 프로그램 및 배포 매니페스트를 만들고, 편집하고, 서명할 수 있도록 합니다. Mage.exe는 명령줄 도구로서 일괄 처리 스크립트뿐 아니라 ASP.NET 응용 프로그램을 비롯한 Windows 기반 응용 프로그램에서도 실행할 수 있습니다.  
  
 [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
 명령줄 도구인 Mage.exe와 동일한 기능을 지원하지만 Windows 기반 UI(사용자 인터페이스)를 사용합니다. 명령줄 도구인 Mage.exe와 동일한 기능을 지원하지만 Windows 기반 UI(사용자 인터페이스)를 사용합니다.  
  
 [MDbg.exe(.NET Framework 명령줄 디버거)](../../../docs/framework/tools/mdbg-exe.md)  
 도구 공급업체 및 응용 프로그램 개발자가 .NET Framework 공용 언어 런타임을 대상으로 하는 프로그램에서 버그를 쉽게 찾아서 수정할 수 있도록 도와줍니다. 이 도구에는 디버깅 서비스를 제공하기 위해 런타임 디버깅 API가 사용됩니다.  
  
 [Mgmtclassgen.exe(강력하게 형식화된 관리 클래스 생성기)](../../../docs/framework/tools/mgmtclassgen-exe.md)  
 지정된 WMI(Windows Management Instrumentation) 클래스에 대한 초기 바인딩 관리되는 클래스를 생성할 수 있도록 합니다.  
  
 [Mpgo.exe(관리되는 프로필 기반 최적화 도구)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)  
 일반 최종 사용자 시나리오를 사용하여 네이티브 이미지 어셈블리를 조정하도록 설정합니다. Mpgo.exe는 응용 프로그램 개발자가 선택한 교육 시나리오를 사용하여 네이티브 이미지 응용 프로그램 어셈블리(.NET Framework 어셈블리는 아님)에 대한 프로필 데이터를 생성하고 사용할 수 있도록 허용합니다.  
  
 [Ngen.exe(네이티브 이미지 생성기)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)  
 컴파일된 프로세서별 컴퓨터 코드가 포함된 파일인 네이티브 이미지를 사용하여 관리되는 응용 프로그램의 성능을 향상시킵니다. 런타임은 JIT(Just-In-Time) 컴파일러를 사용하지 않고 캐시의 네이티브 이미지를 사용하여 원본 어셈블리를 컴파일할 수 있습니다.  
  
 [Peverify.exe(PEVerify 도구)](../../../docs/framework/tools/peverify-exe-peverify-tool.md)  
 MSIL(Microsoft Intermediate Language) 코드 및 관련 메타데이터가 형식 안전성 요구 사항을 충족하는지 여부를 쉽게 확인할 수 있도록 합니다. MSIL(Microsoft Intermediate Language) 코드 및 관련 메타데이터가 형식 안전성 요구 사항을 충족하는지 여부를 쉽게 확인할 수 있도록 합니다.  
  
 [Regasm.exe(어셈블리 등록 도구)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 어셈블리 내의 메타데이터를 읽고 레지스트리에 필요한 항목을 추가합니다. 이렇게 하면 COM 클라이언트를 .NET Framework 클래스로 표시할 수 있습니다.  
  
 [Regsvcs.exe(.NET 서비스 설치 도구)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)  
 어셈블리를 로드 및 등록하고, 형식 라이브러리를 생성하여 지정된 COM+ 버전 1.0 응용 프로그램에 설치하며, 프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.  
  
 [Resgen.exe(리소스 파일 생성기)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 텍스트 파일(.txt 또는 .restext)과 XML 기반 리소스 형식 파일(.resx)을 런타임 이진 실행 파일에 포함시키거나 위성 어셈블리로 컴파일할 수 있는 공용 언어 런타임 이진 파일(.resources)로 변환합니다.  
  
 [SecAnnotate.exe(.NET Security Annotator 도구)](../../../docs/framework/tools/secannotate-exe-net-security-annotator-tool.md)  
 어셈블리의 SecurityCritical 및 SecuritySafeCritical 부분을 식별합니다. 어셈블리의 `SecurityCritical` 및 `SecuritySafeCritical` 부분을 식별합니다.  
  
 [SignTool.exe(서명 도구)](../../../docs/framework/tools/signtool-exe.md)  
 파일에 디지털 서명을 하고, 파일의 서명을 확인하고, 파일에 타임스탬프를 기록합니다.  
  
 [Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 강력한 이름을 사용하여 어셈블리를 만들 수 있도록 합니다. 이 도구는 키 관리, 서명 생성 및 서명 확인을 위한 옵션을 제공합니다.  
  
 [SOS.dll(SOS 디버깅 확장)](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md)  
 내부 공용 언어 런타임 환경에 대한 정보를 제공하여 관리되는 프로그램을 WinDbg.exe 디버거와 Visual Studio에서 쉽게 디버깅할 수 있도록 합니다.  
  
 [SqlMetal.exe(코드 생성 도구)](../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 .NET Framework의 LINQ to SQL 구성 요소에 대한 코드와 매핑을 생성합니다.  
  
 [Storeadm.exe(격리된 저장소 도구)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)  
 사용자의 저장소를 나열하고 삭제할 수 있는 옵션을 제공함으로써 격리된 저장소를 관리합니다.  
  
 [Tlbexp.exe(형식 라이브러리 내보내기)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)  
 공용 언어 런타임 어셈블리에 정의된 형식을 설명하는 형식 라이브러리를 생성합니다.  
  
 [Tlbimp.exe(형식 라이브러리 가져오기)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 COM 형식 라이브러리에 있는 형식 정의를 공용 언어 런타임 어셈블리에 있는 동일한 기능의 정의로 변환합니다.  
  
 [Winmdexp.exe(Windows 런타임 메타데이터 내보내기 도구)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)  
 .winmdobj 파일로 컴파일된 .NET Framework 어셈블리를 Windows 런타임 메타데이터 및 구현 정보가 둘 다 포함된 .winmd 파일로 패키지된 Windows 런타임 구성 요소에 내보냅니다.  
  
 [Winres.exe(Windows Forms 리소스 편집기)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 Windows Forms에 사용되는 UI(사용자 인터페이스) 리소스(.resx 또는 .resources 파일)를 쉽게 지역화할 수 있도록 합니다. 문자열을 번역한 다음 지역화(번역)된 문자열에 적합하도록 컨트롤의 크기를 조정하거나 컨트롤을 이동하고 숨길 수 있습니다.  
  
## <a name="related-sections"></a>관련 단원  
 [도구](http://msdn.microsoft.com/library/f533241c-317c-445e-88ca-c80c8d078fca)  
 isXPS 규칙 도구(isXPS.exe) 및 성능 프로파일링 도구와 같은 도구가 포함되어 있습니다.  
  
 [Windows Communication Foundation 도구](../../../docs/framework/wcf/tools.md)  
 WCF(Windows Communication Foundation) 응용 프로그램을 보다 쉽게 만들고 배포하고 관리할 수 있도록 지원하는 도구가 포함되어 있습니다.

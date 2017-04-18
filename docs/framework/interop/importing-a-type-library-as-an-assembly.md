---
title: "형식 라이브러리를 어셈블리로 가져오기 | Microsoft Docs"
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
  - "COM interop, COM 구성 요소 게시"
  - "COM interop, 형식 라이브러리 가져오기"
  - "사용자 지정 래퍼"
  - ".NET Framework에 COM 구성 요소 게시"
  - "형식 라이브러리 가져오기"
  - "비관리 코드와의 상호 운용, COM 구성 요소 게시"
  - "비관리 코드와의 상호 운용, 형식 라이브러리 가져오기"
  - "메타데이터"
  - "형식 라이브러리"
  - "형식 라이브러리 가져오기"
  - "형식 메타데이터"
  - "TypeLibConverter 클래스, 형식 라이브러리를 어셈블리로 가져오기"
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 형식 라이브러리를 어셈블리로 가져오기
COM 형식 정의는 일반적으로 형식 라이브러리에 위치하는 반면  CLS 규격 컴파일러는 형식 메타데이터를 어셈블리에 생성합니다.  이들 두 형식 정보의 소스는 많이 다릅니다.  이 항목에서는 형식 라이브러리에서 메타데이터를 생성하는 방법에 대해 설명합니다.  결과로 생성되는 어셈블리를 interop 어셈블리라고 하며, 이 어셈블리에 포함된 형식 정보를 통해 .NET Framework 응용 프로그램에서 COM 형식을 사용할 수 있습니다.  
  
 이 형식 정보는 두 가지 방법으로 응용 프로그램에서 사용하도록 할 수 있습니다.  
  
-   디자인 타임 전용 interop 어셈블리 사용. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 및 이후 버전에서는 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다.  컴파일러는 응용 프로그램에서 사용하는 형식 정보만 포함합니다.  응용 프로그램과 함께 interop 어셈블리를 배포할 필요가 없습니다.  이것이 권장되는 방법입니다.  
  
-   interop 어셈블리 배포. interop 어셈블리에 대한 표준 참조를 만들 수 있습니다.  이 경우 interop 어셈블리가 응용 프로그램과 함께 배포되어야 합니다.  이 방법을 채택하고 전용 COM 구성 요소를 사용하지 않는 경우 관리 코드에 통합할 COM 구성 요소의 작성자가 게시한 PIA\(주 interop 어셈블리\)를 항상 참조합니다.  주 interop 어셈블리의 생성과 사용에 대한 자세한 내용은 [주 Interop 어셈블리](http://msdn.microsoft.com/ko-kr/b977a8be-59a0-40a0-a806-b11ffba5c080)를 참조하십시오.  
  
 디자인 타임 전용 interop 어셈블리를 사용하면 COM 구성 요소 작성자가 게시한 주 interop 어셈블리의 형식 정보를 포함할 수 있습니다.  그러나 응용 프로그램과 함께 주 interop 어셈블리를 배포할 필요가 없습니다.  
  
 디자인 타임 전용 interop 어셈블리를 사용하면 대부분의 응용 프로그램에서 COM 구성 요소의 일부 기능만 사용하게 되므로 응용 프로그램의 크기가 줄어듭니다.  형식 정보를 포함하면 컴파일러의 효율성이 매우 높아집니다. 응용 프로그램에서 COM 인터페이스의 일부 메서드만 사용할 경우 컴파일러는 사용되지 않는 메서드는 포함하지 않습니다.  포함된 형식 정보가 있는 응용 프로그램끼리 상호 작용하거나 포함된 형식 정보가 있는 응용 프로그램이 주 interop 어셈블리를 사용하는 응용 프로그램과 상호 작용하면 공용 언어 런타임에서는 동일 형식 규칙을 사용하여 동일한 이름의 두 형식이 동일한 COM 형식을 나타내는지 확인합니다.  그러나 COM 개체를 사용하기 위해 이러한 규칙을 알고 있어야 하는 것은 아닙니다.  이러한 규칙에 대해 관심이 있으면 [동일 형식 및 포함된 Interop 형식](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md)을 참조하십시오.  
  
## 메타데이터 생성  
 COM 형식 라이브러리는 확장명이 .tlb인 독립 실행형 파일일 수 있습니다\(예: Loanlib.tlb\).  일부 형식 라이브러리는 .dll 또는 .exe 파일의 리소스 섹션에 포함되고,  기타 형식 라이브러리 정보의 소스는 .olb 및 .ocx 파일입니다.  
  
 대상 COM 형식의 구현이 포함된 형식 라이브러리를 찾고 나면 형식 메타데이터가 들어 있는 interop 어셈블리를 생성하기 위한 다음과 같은 옵션이 있습니다.  
  
-   Visual Studio  
  
     Visual Studio에서는 형식 라이브러리의 COM 형식을 어셈블리의 메타데이터로 자동 변환합니다.  자세한 내용은 [방법: 형식 라이브러리에 참조 추가](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) 및 [연습: Microsoft Office 어셈블리의 형식 정보 포함](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
-   [형식 라이브러리 가져오기\(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     형식 라이브러리 가져오기에서는 결과 interop 파일의 메타데이터를 조정하고, 기존 형식 라이브러리에서 형식을 가져오고, interop 어셈블리와 네임스페이스를 만들 수 있는 명령줄 옵션을 제공합니다.  자세한 내용은 [방법: 형식 라이브러리에서 Interop 어셈블리 생성](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)을 참조하십시오.  
  
-   <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=fullName> 클래스  
  
     이 클래스에서는 형식 라이브러리의 coclass 및 인터페이스를 어셈블리 내의 메타데이터로 변환하는 메서드를 제공합니다.  이 클래스는 Tlbimp.exe와 동일한 메타데이터를 생성합니다.  그러나 Tlbimp.exe와는 달리 <xref:System.Runtime.InteropServices.TypeLibConverter> 클래스는 메모리 내에 있는 형식 라이브러리를 메타데이터로 변환할 수 있습니다.  
  
-   사용자 지정 래퍼  
  
     형식 라이브러리가 없거나 올바르지 않은 경우에는 관리되는 소스 코드에 클래스 또는 인터페이스의 중복된 정의를 만들 수 있습니다.  그런 다음, 런타임을 목적으로 하는 컴파일러를 사용하여 이 소스 코드를 컴파일하여 어셈블리의 메타데이터를 생성할 수 있습니다.  
  
     COM 형식을 수동으로 정의하려면 다음 항목에 대해 알고 있어야 합니다.  
  
    -   정의할 coclass 및 인터페이스에 대한 정확한 설명  
  
    -   적절한 .NET Framework 클래스 정의를 생성할 수 있는 컴파일러\(예: C\# 컴파일러\)  
  
    -   형식 라이브러리에서 어셈블리로의 변환 규칙에 대한 지식  
  
     사용자 지정 래퍼 작성은 고급 기술입니다.  사용자 지정 래퍼를 생성하는 방법에 대한 자세한 내용은 [표준 래퍼 사용자 지정](http://msdn.microsoft.com/ko-kr/c40d089b-6a3c-41b5-a20d-d760c215e49d)을 참조하십시오.  
  
 COM interop 가져오기 프로세스에 대한 자세한 내용은 [형식 라이브러리를 어셈블리로 변환 요약](http://msdn.microsoft.com/ko-kr/bf3f90c5-4770-4ab8-895c-3ba1055cc958)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 [.NET Framework에 COM 구성 요소 노출](../../../docs/framework/interop/exposing-com-components.md)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/ko-kr/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/ko-kr/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ko-kr/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Interop 프로젝트 컴파일](../../../docs/framework/interop/compiling-an-interop-project.md)   
 [Interop 응용 프로그램 배포](../../../docs/framework/interop/deploying-an-interop-application.md)   
 [방법: 형식 라이브러리에 참조 추가](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)   
 [방법: 형식 라이브러리에서 Interop 어셈블리 생성](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)   
 [연습: Microsoft Office 어셈블리의 형식 정보 포함](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)
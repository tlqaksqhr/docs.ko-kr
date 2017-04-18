---
title: ".NET Framework에 COM 구성 요소 노출 | Microsoft Docs"
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
  - ".NET Framework에 COM 구성 요소 게시"
  - "비관리 코드와의 상호 운용, COM 구성 요소 게시"
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# .NET Framework에 COM 구성 요소 노출
이 단원에서는 관리 코드에 기존 COM 구성 요소를 노출하는 프로세스를 요약하여 설명합니다.  .NET Framework와 통합되는 COM 서버를 작성하는 방법에 대한 자세한 내용은 [상호 운용을 위한 디자인 고려 사항](http://msdn.microsoft.com/ko-kr/b59637f6-fe35-40d6-ae72-901e7a707689)을 참조하십시오.  
  
 관리 코드에서의 기존 COM 구성 요소는 중간 계층 비즈니스 응용 프로그램 또는 격리된 기능으로서, 중요한 리소스입니다.  가장 이상적인 구성 요소는 주 interop 어셈블리를 갖고 COM의 프로그래밍 기준을 따릅니다.  
  
#### .NET Framework에 COM 구성 요소를 노출하려면  
  
1.  [형식 라이브러리를 어셈블리로 가져오기](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
  
     공용 언어 런타임에서는 COM 형식을 비롯한 모든 형식에 대한 메타데이터가 필요합니다.  메타데이터로 가져온 COM 형식을 포함하는 어셈블리를 얻는 방법에는 여러 가지가 있습니다.  
  
2.  [관리 코드에서 COM 형식 만들기](http://msdn.microsoft.com/ko-kr/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
  
     관리되는 형식에서 하는 것과 마찬가지로, COM 형식을 검사하거나 인스턴스를 활성화하거나 COM 개체에 대해 메서드를 호출할 수 있습니다.  
  
3.  [interop 프로젝트 컴파일](../../../docs/framework/interop/compiling-an-interop-project.md)  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# 및 C\+\+ 등의 CLS\(공용 언어 사양\) 규격 언어에서 사용할 수 있는 여러 컴파일러를 제공합니다.  
  
4.  [interop 응용 프로그램 배포](../../../docs/framework/interop/deploying-an-interop-application.md)  
  
     Interop 응용 프로그램은 전역 어셈블리 캐시에 [강력한 이름](../../../docs/framework/app-domains/strong-named-assemblies.md)의 서명된 어셈블리로 배포하는 것이 가장 좋습니다.  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../../../docs/framework/interop/index.md)   
 [Design Considerations for Interoperation](http://msdn.microsoft.com/ko-kr/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [COM Interop 샘플: .NET 클라이언트 및 COM 서버](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [언어 독립성 및 언어 독립적 구성 요소](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
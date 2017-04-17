---
title: "방법: COM에서 .NET 형식 참조 | Microsoft Docs"
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
  - "COM interop, 형식 라이브러리 가져오기"
  - "COM interop, .NET 형식 참조"
  - "형식 라이브러리 가져오기"
  - "비관리 코드와의 상호 운용, 형식 라이브러리 가져오기"
  - "비관리 코드와의 상호 운용, .NET 형식 참조"
  - ".NET 형식 참조"
  - "형식 라이브러리"
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: COM에서 .NET 형식 참조
클라이언트 및 서버 코드에서 COM과 .NET Framework 간의 차이는 거의 표시되지 않습니다.  이 때문에 Microsoft Visual Basic 클라이언트에서는 개체 메서드나 구문, 속성 필드 등을 다른 COM 개체와 마찬가지로 표시하는 개체 브라우저에서 .NET 개체를 볼 수 있습니다.  
  
 COM 형식 라이브러리에 메타데이터를 내보내는 데 동일한 도구를 사용하지만, C\+\+ 클라이언트의 경우에는 형식 라이브러리를 가져오는 프로세스가 조금 더 복잡합니다.  관리되지 않는 C\+\+ 클라이언트에서 .NET 개체 멤버를 참조하려면 **\#import** 지시문을 사용하여 TLB 파일\(Tlbexp.exe를 사용하여 만든 파일\)을 참조해야 합니다.  C\+\+에서 형식 라이브러리를 참조할 때는 **raw\_interfaces\_only** 옵션을 지정하거나 기본 클래스 라이브러리의 정의인 Mscorlib.tlb를 가져와야 합니다.  
  
### 라이브러리를 가져오려면  
  
-   **\#import** 지시문에서 **raw\_interfaces\_only** 옵션을 지정합니다.  예를 들면 다음과 같습니다.  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     또는  
  
-   Mscorlib.tlb에 대해 \#import 지시문을 포함합니다.  예를 들면 다음과 같습니다.  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## 참고 항목  
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [COM에 어셈블리 등록](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/ko-kr/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/ko-kr/fb63564c-c1b9-4655-a094-a235625882ce)
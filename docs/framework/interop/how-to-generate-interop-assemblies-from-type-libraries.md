---
title: "방법: 형식 라이브러리에서 Interop 어셈블리 생성 | Microsoft Docs"
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
  - "형식 라이브러리 가져오기"
  - "interop 어셈블리, 생성"
  - "형식 라이브러리"
  - "형식 라이브러리 가져오기"
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 형식 라이브러리에서 Interop 어셈블리 생성
[형식 라이브러리 가져오기\(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)는 COM 형식 라이브러리에 포함된 coclass 및 인터페이스를 메타데이터로 변환하는 명령줄 도구로서,  이 도구는 형식 정보에 대한 interop 어셈블리 및 네임스페이스를 자동으로 만듭니다.  클래스에 대한 메타데이터가 만들어지면, 관리되는 클라이언트에서는 COM 형식에 대한 인스턴스를 .NET 인스턴스와 동일한 방법으로 만들고 해당 메서드를 호출할 수 있습니다.  Tlbimp.exe는 모든 형식 라이브러리를 메타데이터로 한 번에 변환하며 형식 라이브러리에 정의된 형식의 하위 집합에 대해서는 형식 정보를 생성하지 않습니다.  
  
### 형식 라이브러리에서 interop 어셈블리를 생성하려면  
  
1.  다음 명령을 사용합니다.  
  
     **tlbimp** \<*type\-library\-file*\>  
  
     **\/out:** 스위치를 추가하면 LOANLib.dll과 같이 변경된 이름으로 interop 어셈블리를 생성합니다.  interop 어셈블리 이름을 변경하면 원래 COM DLL과의 구별 및 중복 이름으로 인해 발생할 수 있는 문제 방지에 도움이 될 수 있습니다.  
  
## 예제  
 다음 명령은 `Loanlib` 네임스페이스에 Loanlib.dll 어셈블리를 생성합니다.  
  
```  
tlbimp Loanlib.dll  
```  
  
 다음 명령은 변경된 이름\(LOANLib.dll\)으로 interop 어셈블리를 생성합니다.  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## 참고 항목  
 [형식 라이브러리를 어셈블리로 가져오기](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [.NET Framework에 COM 구성 요소 노출](../../../docs/framework/interop/exposing-com-components.md)
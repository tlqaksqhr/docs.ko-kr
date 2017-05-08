---
title: "dllMainReturnsFalse MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), DllMain returns false"
  - "DllMainReturnsFalse MDA"
  - "DllMain function"
  - "MDAs (managed debugging assistants), DllMain returns false"
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# dllMainReturnsFalse MDA
DLL\_PROCESS\_ATTACH라는 이유로 호출된 사용자 어셈블리의 관리되는 `DllMain` 함수가 FALSE를 반환하면 `dllMainReturnsFalse` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
## 증상  
 `DllMain` 함수가 제대로 실행되지 않았음을 나타내는 FALSE를 반환했습니다.  일반적으로 `DllMain` 함수에는 중요한 초기화 코드가 포함되기 때문에 이로 인해 알 수 없는 문제가 발생할 수 있습니다.  
  
## 원인  
 `DllMain` 함수는 로드 시 DLL 초기화를 위해 DLL\_PROCESS\_ATTACH라는 이유로 호출됩니다.  이 함수가 FALSE를 반환하면 DLL 초기화가 실패했음을 나타냅니다.  
  
## 해결  
 실패한 DLL의 `DllMain` 함수 코드를 분석하여 초기화 실패의 원인을 식별합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  `DllMain`의 반환 값에 대한 데이터만 보고합니다.  
  
## Output  
 DLL\_PROCESS\_ATTACH라는 이유로 호출된 `DllMain` 함수가 FALSE를 반환했음을 나타내는 메시지입니다.  `DllMain`이 관리 코드에서 구현되는 경우에만 이 MDA가 활성화됩니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
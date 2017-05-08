---
title: "콜백 함수 | Microsoft Docs"
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
  - "콜백 함수"
  - "플랫폼 호출, 관리되지 않는 함수 호출"
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 콜백 함수
콜백 함수는 관리되는 응용 프로그램 내의 코드로서, 관리되지 않는 DLL 함수가 작업을 완료할 수 있도록 도와 줍니다.  콜백 함수에 대한 호출은 관리되는 응용 프로그램에서 DLL 함수에 간접적으로 전달되어 관리되는 구현에 다시 전달됩니다.  플랫폼 호출로 호출되는 DLL 함수 중 일부는 관리 코드의 콜백 함수가 있어야 제대로 실행됩니다.  
  
 대부분의 DLL 함수를 관리 코드에서 호출할 때는 해당 함수에 대한 관리되는 정의를 만든 다음 함수를 호출하면 되므로  프로세스가 비교적 간단합니다.  
  
 그러나, 콜백 함수를 필요로 하는 DLL 함수를 사용할 때는 몇 가지 추가 작업이 필요합니다.  먼저, 함수에 대한 설명서를 통해, 해당 함수에 콜백 함수가 필요한지 여부를 확인한 다음  관리되는 응용 프로그램에서 콜백 함수를 만들어야 합니다.  그런 다음, DLL 함수를 호출할 때, 콜백 함수에 대한 포인터를 인수로 전달합니다.  다음 예제에서는 이러한 단계를 요약하여 보여 줍니다.  
  
 ![플랫폼 호출 콜백](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
콜백 함수 및 구현  
  
 콜백 함수는 반복적으로 수행되는 작업에 유용합니다.  또한 Win32 API에서 **EnumFontFamilies**, **EnumPrinters**, **EnumWindows** 등의 열거형 함수에도 사용됩니다.  **EnumWindows** 함수는 컴퓨터의 모든 기존 창을 열거하면서 각 창에 대해 작업을 수행하는 콜백 함수를 호출합니다.  자세한 내용과 예제를 보려면 [방법: 콜백 함수 구현](../../../docs/framework/interop/how-to-implement-callback-functions.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: 콜백 함수 구현](../../../docs/framework/interop/how-to-implement-callback-functions.md)   
 [DLL 함수 호출](../../../docs/framework/interop/calling-a-dll-function.md)